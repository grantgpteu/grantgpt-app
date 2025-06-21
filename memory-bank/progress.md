# progress.md

## What Works

*   **Base Codebase:** The foundational codebase from the upstream Onyx/Danswer project is in place.
*   **Core Functionality (Inherited):** The RAG system's core capabilities for unified search, AI answers, and connector integrations are inherited from the upstream project.
*   **Development Environment:** Docker Compose configurations are available for setting up a local development environment.
*   **Git Remotes:** The project brief outlines the necessary Git remote configurations for `origin` (GrantGPT fork) and `upstream` (Onyx).

## What's Left to Build

The following are the primary tasks remaining, as outlined in `projectbrief.md`:

1.  **Source Code Management & Synchronization (Git Workflow):**
    *   Regularly fetch and integrate changes from the `upstream` Onyx repository.
    *   Ensure all pushes are strictly to the `origin` GrantGPT repository.
2.  **Preserve Ignored Files and Configuration:**
    *   Implement robust mechanisms to ensure `.gitignore`d files are never overwritten or unintentionally modified during updates.
3.  **Rebrand Name in Codebase:**
    *   Identify and replace all instances of "Onyx" with "GrantGPT" within tracked source code files.
4.  **Apply New Visual Styling in Codebase:**
    *   Modify CSS/styling files to implement the GrantGPT color palette and visual guidelines (requires `design-guidelines.md`).
5.  **Future Goal: Supabase Auth Synchronization:**
    *   Plan and implement the integration of Supabase Auth for user authentication, leveraging the specified Supabase URL (`https://hlfrfgwaiaqwqvcdluvf.supabase.co`). This is a significant future task.

## Current Status

The project is currently in the **Memory Bank Initialization Phase**. All core memory bank files have now been created and populated with initial context.

## Known Issues

*   No specific functional issues are known at this stage, as the focus has been on documentation setup.
*   Potential challenges may arise during Git synchronization (merge conflicts) and comprehensive rebranding across a large codebase.

## Evolution of Project Decisions

*   **Forking Strategy:** The decision to fork Onyx/Danswer and maintain a separate `origin` repository for GrantGPT allows for independent development while still benefiting from upstream updates.
*   **Supabase for Auth:** The explicit decision to use Supabase Auth for future authentication simplifies the auth stack and leverages a managed service.
