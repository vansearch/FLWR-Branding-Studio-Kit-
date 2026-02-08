---
description: Advanced Branding Strategy Workflow
---

# Brand Strategy Workflow

> **Trigger:** "Start branding project", "/branding-start", "Novo projeto de marca"

## Phase 1: Project Setup (Automated)
// turbo
1.  Run the setup script to create the environment.
    ```bash
    python3 scripts/setup_branding_project.py
    ```
2.  **User Action:** Ask the user for the Client Name and brief description.
3.  **System Action:** Verify if `client_intel/` has documents. If empty, ask user to upload transcripts/briefings.

## Phase 2: Interrogation Mode (Safety Lock)
1.  **Analyze Context:** Read `client_intel/` (using `grep_search` or `read_file` sparsely).
2.  **Count Words:** If total context < 500 words OR missing RACE elements (Role, Action, Context, Example):
    *   **STOP:** Do not generate strategy.
    *   **ACTION:** Ask 3 deep probing questions based on the missing pillars (e.g., "Who is the enemy of the brand?", "What is the internal conflict of the customer?").
    *   **REPEAT:** Loop until context is sufficient.

## Phase 3: Strategic Analysis (The Thinking)
1.  **Archetype Profiling:**
    *   Compare client data against the 12 Archetypes.
    *   Select Primary and Secondary archetypes.
    *   *Reality Check:* Quote specific evidence from `client_intel` that supports this choice.
2.  **Persona Building (Expandida):**
    *   Draft **5 Goal-Directed Personas** (não apenas demografia):
        *   Perfil demográfico
        *   Comportamento e estilo de vida
        *   Dores e frustrações específicas
        *   Objetivos e motivações
        *   Relação com a marca
        *   Citação representativa
    *   *Reality Check:* Ensure goals align with the product's actual solution.
3.  **Tone & Voice (Completo):**
    *   Define the 4 dimensions (Funny/Serious, etc.).
    *   Create a "Dictionary" of specific words.
    *   **NEW:** Add "Sonic Essence" (como a marca "soa")
    *   **NEW:** Add practical scenarios (e-mail, WhatsApp, social media examples)
4.  **Rational vs Emotional Benefits:**
    *   **NEW:** Create comparison table showing functional benefits vs emotional feelings
    *   Map each service/product feature to both rational and emotional outcomes
5.  **Strategic Conflict Check:**
    *   Review all user requirements against the established Strategy (Archetype/Tone).
    *   **Flag Contradictions:** If Client Request != Strategy Best Practice, create a "Warning Notes" section explaining *why* (using Color Psychology/Gestalt) and proposing a correction.

## Phase 4: Asset Generation (The Output)
> **CRITICAL:** Use the templates in `strategy_output/brand_assets_md/` (which were copied from `.agent/templates/`).

1.  **Fill Templates:** For each `.md` file in `strategy_output/brand_assets_md/`:
    *   READ the file to understand the structure.
    *   REWRITE the content using the *new* strategy (Phase 3).
    *   KEEP the Markdown formatting exactly as is (H1, H2, Lists).
2.  **Visual Strategy:**
    *   Add a section or new file for Visual Guidelines based on Color Psychology and Gestalt.
    *   Suggest color palettes with psychological justification (Eva Heller).

## Phase 5: Final Validation & Quality Check
1.  **Writing Quality Audit (Anti-Slop):**
    *   Review ALL generated copy for:
        *   ❌ Sequential adjectives ("calmo e tranquilo", "belo e incrível")
        *   ❌ Redundant constructions ("experiência premium de luxo")
        *   ❌ Reused structures between paragraphs
        *   ✅ Precision over decoration
        *   ✅ Natural flow (read aloud test)
        *   ✅ Traditional capitalization (first letter of sentence only)
2.  **Template Completeness:**
    *   Verify all templates filled, including new ones:
        *   09_racional_vs_emocional.md
        *   10_personas_detalhadas.md (5 personas, not just 1-2)
        *   11_projeto_voz_de_marca.md (with scenarios)
3.  **Review:** Ask user to review the generated Markdown files.
4.  **Figma Check:** Remind user these files are ready for Figma plugin import.

