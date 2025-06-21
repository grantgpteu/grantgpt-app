# activeContext.md

## Current Work Focus

The immediate focus is on fully initializing the project's memory bank to ensure comprehensive documentation and context for all future development. This involves creating the remaining core memory bank files: `productContext.md`, `systemPatterns.md`, `techContext.md`, `activeContext.md` (this file), and `progress.md`.

## Recent Changes

*   **`projectbrief.md`**: Reviewed and confirmed as the foundational document.
*   **`productContext.md`**: Created, detailing the "why" and "how" of GrantGPT, its problem-solving objectives, and user experience goals.
*   **`systemPatterns.md`**: Created, outlining the system architecture, key technical decisions, design patterns, and critical implementation paths.
*   **`techContext.md`**: Created, documenting the technologies used in both frontend and backend, development setup, technical constraints, dependencies, and tool usage patterns.

## Next Steps

1.  Complete the creation of `activeContext.md` (this file).
2.  Create `progress.md` to track project status, completed work, and remaining tasks.
3.  Once all core memory bank files are in place, the memory bank initialization task will be complete.
4.  The next major task will be to proceed with the core requirements outlined in `projectbrief.md`:
    *   Source Code Management & Synchronization (Git Workflow)
    *   Preserve Ignored Files and Configuration
    *   Rebrand Name in Codebase (Onyx to GrantGPT)
    *   Apply New Visual Styling in Codebase
    *   Future Goal: Supabase Auth Synchronization (using `https://hlfrfgwaiaqwqvcdluvf.supabase.co`)

## Active Decisions and Considerations

*   **Rebranding Scope:** The rebranding from "Onyx" to "GrantGPT" needs to be applied comprehensively across textual references and visual styling within the codebase.
*   **Git Workflow:** Strict adherence to the specified Git remotes (`origin` for GrantGPT fork, `upstream` for Onyx) and the "fetch only from upstream, push only to origin" rule is critical.
*   **Ignored Files:** Special care must be taken to preserve `.gitignore`d files during any code integration or rebranding efforts.
*   **Supabase Auth:** The integration of Supabase Auth is a significant future goal, requiring careful planning to ensure seamless user experience and adherence to the `@supabase/ssr` guidelines.

## Important Patterns and Preferences

*   **Documentation-Driven Development:** The memory bank is central to maintaining context and continuity. All significant changes and decisions should be reflected here.
*   **Clean Code and Best Practices:** Adherence to general software engineering best practices (as outlined in `.clinerules/gemini-comprehensive-software-engineering-guide.md`) is expected.
*   **Supabase SSR Guidelines:** When implementing Supabase Auth, the specific guidelines in `.clinerules/next-js-supabase.md` regarding `createClient` functions and cookie handling (`getAll`, `setAll` only) MUST be followed to avoid breaking the application.

## Learnings and Project Insights

*   The project is a complex RAG system with distinct frontend and backend components.
*   The rebranding effort requires careful, systematic changes across the codebase.
*   Authentication is a critical area, with a clear future direction towards Supabase Auth.
*   The `.gitignore` file is crucial for identifying files that must be preserved.
