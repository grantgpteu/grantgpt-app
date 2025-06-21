# techContext.md

## Technologies Used

### Frontend
*   **Next.js:** React framework for building the web application, supporting server-side rendering (SSR) and static site generation.
*   **React:** JavaScript library for building user interfaces.
*   **TypeScript:** Superset of JavaScript that adds static typing, improving code quality and maintainability.
*   **Tailwind CSS:** A utility-first CSS framework for rapidly building custom designs.
*   **Headless UI:** Unstyled, accessible UI components that integrate well with Tailwind CSS.
*   **Radix UI:** A collection of unstyled, accessible UI components for building high-quality design systems.
*   **Dnd-kit:** A modular and extensible drag and drop toolkit for React.
*   **Formik & Yup:** For form management and validation.
*   **SWR:** React Hooks for data fetching.
*   **PostHog:** For product analytics.
*   **Sentry:** For error monitoring.

### Backend
*   **Python:** Primary programming language for the backend.
*   **FastAPI:** Modern, fast (high-performance) web framework for building APIs with Python 3.7+ based on standard Python type hints.
*   **SQLAlchemy:** Python SQL toolkit and Object Relational Mapper (ORM) that gives developers the full power of SQL.
*   **Alembic:** Lightweight database migration tool for SQLAlchemy.
*   **Vespa / Elasticsearch:** Document indexing and search engine (specific choice may vary based on deployment).
*   **Redis:** In-memory data structure store, used as a database, cache, and message broker.
*   **PyTorch:** Machine learning framework, likely used for custom embedding models or other ML components.
*   **Hugging Face Transformers:** Library for state-of-the-art Natural Language Processing (NLP).

### Infrastructure & Deployment
*   **Docker:** Containerization platform for packaging applications and their dependencies.
*   **Docker Compose:** Tool for defining and running multi-container Docker applications.
*   **Kubernetes:** Open-source system for automating deployment, scaling, and management of containerized applications.
*   **Nginx:** Web server and reverse proxy.

### Future Integration
*   **Supabase:** Open-source Firebase alternative, specifically for user authentication (Supabase Auth).

## Development Setup

### Local Development
*   **Docker Compose:** The primary method for local development, spinning up all necessary services (backend, frontend, database, Redis, document index).
*   **Environment Variables:** Configuration is managed via `.env` files, which are Git-ignored to prevent sensitive information from being committed.
*   **Pre-commit Hooks:** Uses `pre-commit` for linting and formatting checks (`ruff` for Python, `prettier` for frontend).

### Code Structure
*   **`web/`:** Contains the Next.js frontend application.
*   **`backend/`:** Contains the Python backend application, including API endpoints, business logic, database models, and connectors.
*   **`deployment/`:** Contains Dockerfiles, Docker Compose configurations, and Kubernetes manifests for deployment.
*   **`memory-bank/`:** Documentation and context for the project.

## Technical Constraints

*   **Python Version:** Backend requires a specific Python version (e.g., 3.9+).
*   **Node.js Version:** Frontend requires a specific Node.js version.
*   **Database Compatibility:** Postgres is the required relational database.
*   **LLM Integration:** Flexibility to use various LLMs, but specific configurations are needed for each.
*   **Supabase Auth Integration:** Must adhere to the `@supabase/ssr` guidelines for Next.js SSR to ensure proper session management and avoid deprecated patterns.

## Dependencies

*   **Frontend (`web/package.json`):**
    *   `next`, `react`, `react-dom`
    *   `@supabase/ssr` (future dependency for auth)
    *   UI libraries: `@headlessui/react`, `@radix-ui/*`, `lucide-react`
    *   Data fetching: `swr`
    *   Styling: `tailwindcss`, `autoprefixer`, `postcss`
*   **Backend (`backend/pyproject.toml` and `backend/requirements/*.txt`):**
    *   `fastapi`, `uvicorn`
    *   `sqlalchemy`, `psycopg2` (Postgres driver)
    *   `alembic`
    *   `pydantic`
    *   `torch`, `transformers`
    *   `redis`
    *   Various connector-specific dependencies.

## Tool Usage Patterns

*   **Git:** For version control, branching, merging, and rebasing. Strict adherence to `origin` vs. `upstream` remotes.
*   **Docker:** For building and running containers.
*   **npm/yarn:** For managing frontend dependencies.
*   **pip/poetry:** For managing backend Python dependencies.
*   **Prettier:** For frontend code formatting.
*   **Ruff:** For backend Python linting and formatting.
*   **MyPy:** For static type checking in Python.
