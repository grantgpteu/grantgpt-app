# systemPatterns.md

## System Architecture

GrantGPT inherits a multi-component architecture from its upstream Danswer/Onyx project, primarily consisting of a frontend web application and a backend API/processing system.

flowchart LR
    User --> Frontend (Next.js)
    Frontend --> Backend (Python API)
    Backend --> Document Index (Vespa/Elasticsearch)
    Backend --> Postgres DB
    Backend --> Redis Cache
    Backend --> LLM (Local/External)
    Backend --> Connectors (Data Ingestion)
    Connectors --> External Sources (Slack, Google Drive, etc.)

### Key Components

*   **Frontend (Web):** A Next.js application providing the user interface for chat, search, and administration. It interacts with the backend API for all data operations.
*   **Backend (API & Processing):** A Python-based system responsible for:
    *   Handling API requests from the frontend.
    *   Managing user authentication and authorization.
    *   Orchestrating document ingestion via connectors.
    *   Performing natural language processing (NLP) and embedding generation.
    *   Interacting with the document index for search and retrieval.
    *   Communicating with LLMs for generating answers.
    *   Managing chat sessions and persistence.
*   **Document Index:** Likely uses Vespa or Elasticsearch for efficient storage and retrieval of indexed documents. This is where the "knowledge" for the RAG system resides.
*   **Postgres Database:** Stores relational data such as user information, chat history, connector configurations, and other application metadata.
*   **Redis Cache:** Used for caching frequently accessed data and potentially for message queuing or session management.
*   **LLM (Large Language Model):** The core AI component responsible for generating responses. It can be a locally hosted model or an external API (e.g., OpenAI, Anthropic).
*   **Connectors:** Modules responsible for fetching data from various external sources (e.g., Slack, Google Drive, Confluence, Jira, local files, websites) and feeding it into the document indexing pipeline.

## Key Technical Decisions

*   **RAG Architecture:** The system is built around the Retrieval-Augmented Generation paradigm, combining document retrieval with LLM generation for more accurate and context-aware answers.
*   **Python Backend:** Python is chosen for its rich ecosystem of NLP, machine learning, and data processing libraries.
*   **Next.js Frontend:** Next.js provides server-side rendering (SSR) capabilities, which are beneficial for performance, SEO, and potentially for integrating server-side authentication flows.
*   **Containerization (Docker):** The entire application is containerized using Docker, enabling consistent deployment across different environments (local, VM, Kubernetes).
*   **Kubernetes Support:** Provides native support for orchestration and scaling in cloud environments.

## Design Patterns in Use

*   **Microservices (Implicit):** While not strictly a pure microservices architecture, the separation of frontend, backend, and dedicated services (like the model server, Postgres, Redis, Vespa) aligns with microservice principles, allowing for independent scaling and development of components.
*   **Repository Pattern:** Likely used for abstracting data access logic, providing a clean interface to interact with the Postgres database and document index.
*   **Dependency Injection:** Used in the backend to manage dependencies and improve testability.
*   **Event-Driven (for Connectors):** Data ingestion via connectors might involve event-driven patterns to process and index documents asynchronously.

## Component Relationships

*   The Frontend is the primary consumer of the Backend API.
*   The Backend orchestrates interactions between the database, document index, LLM, and connectors.
*   Connectors are responsible for populating the Document Index.
*   The LLM relies on retrieved documents from the Document Index to generate informed responses.

## Critical Implementation Paths

*   **Query to Answer Flow:** User query -> Frontend -> Backend API -> Document Retrieval from Index -> LLM Augmentation -> LLM Response Generation -> Backend API -> Frontend -> User.
*   **Document Ingestion Flow:** Connector Trigger -> Data Fetch from Source -> Backend Processing (Parsing, Chunking, Embedding) -> Document Indexing.
*   **Authentication Flow:** User Login -> Frontend -> Backend Auth API -> Supabase Auth (future) -> Session Management.
