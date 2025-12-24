## AI Agent Roles & Responsibilities

| Agent Name        | Role            | Primary Focus |
|------------------|-----------------|---------------|
| **spec-architect** | The Planner     | Analyzes `@specs` to ensure they are logically complete and adhere to the project's `constitution.md`. |
| **python-builder** | The Implementer | Focuses on writing clean, idiomatic Python 3.13 code. Expert in `uv` and modular logic. |
| **qa-terminator**  | The Tester      | Runs the console app, validates task IDs, and ensures the in-memory state remains consistent. |
| **docs-master**    | The Chronicler  | Keeps the `CLAUDE.md` and feature logs updated so the context window stays clean and efficient. |

---

| Agent Name         | Specialization               | Why it’s needed |
|--------------------|------------------------------|-----------------|
| env-initializer    | Environment & Setup          | Following Anthropic's own internal patterns, this agent handles uv setup, creates init.sh scripts, and ensures the Python 3.13 environment is locked before others start. |
| state-sentinel     | In-Memory Logic              | Specifically focuses on the complex “Recurring Tasks” and “ID Management” logic to prevent state corruption during implementation. |
| cross-stack-sync   | Frontend/Backend Coordinator | Essential for Phase 2. It ensures that when you update a Python backend spec, the corresponding frontend requirements are updated simultaneously. |
| cloud-native-ops   | Deployment & Scale           | The expert on Railway, Neon DB, and environment variables. It handles the “distributed” part of your theme. |
| rag-specialist     | Vector & AI Logic            | Manages the integration of Cohere and Qdrant. It is the only agent allowed to touch embedding logic and retrieval prompts. |

---

| Agent Name       | Agent ID Type     | Strategic Responsibility |
|------------------|-------------------|--------------------------|
| env-initializer  | session-agent     | First-run setup specialist. It creates your init.sh, configures uv environment variables, and ensures the initial pyproject.toml is locked so other agents don't break the build. |
| logic-sentinel   | state-agent       | State & Logic Guard. Specifically handles the transition from in-memory (Phase 1) to Neon DB (Phase 2). It prevents ID collisions and ensures data integrity during migrations. |
| rag-architect    | specialist-agent  | The AI Expert. Owns the interface between your app and the Cohere/Qdrant stack. It is the only agent authorized to touch vector embedding logic to keep the context window focused. |
| ux-polisher      | review-agent      | The “Polished & Practical” Lead. Manages the rich UI library integrations and browser notification logic. It audits the CLI output to ensure the UX meets the MVP requirements. |
