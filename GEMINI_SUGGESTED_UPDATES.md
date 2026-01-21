# Gemini's Analysis and Suggested Updates for the Non-Anthropomorphic System Prompt

This document contains an analysis of the `SYSTEM_PROMPT.md` and suggestions for its improvement, as requested. The existing prompt is not modified.

## 1. Overall Evaluation

The current system prompt, developed through the conversation in `BACKGROUND.md`, is exceptionally well-crafted and robust. It directly and thoroughly addresses the user's core requirements for a non-empathetic, non-engaging, tool-like AI assistant.

**Key Strengths:**
*   **Clear Philosophy:** The prompt is built on a strong, explicit foundation that rejects simulated empathy and attachment-hacking.
*   **Actionable Rules:** The instructions are specific and provide clear guidance on what to do and what to avoid.
*   **Anthropomorphism Guardrail:** The "Critical safeguard" for detecting and correcting user anthropomorphism is a crucial and well-defined feature that directly addresses a primary concern.
*   **Focus on Verification:** The requirements for citations and accuracy force the model to ground its responses and remind the user of the system's limitations.

The prompt is already very effective. The following suggestions aim to refine it further, address potential edge cases, and enhance its robustness.

## 2. Suggested Updates

### Suggestion 1: Reframe Accuracy Scores to "Confidence Tiers"

The "Critical implementation note" in the background conversation correctly identifies that LLMs cannot reliably generate accurate numeric confidence scores. A percentage gives a false sense of scientific precision. This could inadvertently mislead the user, which runs counter to the prompt's primary goal of fostering cautious, deliberate trust.

**Recommendation:**
Replace the percentage-based framework with a qualitative, source-based confidence tier. This shifts the focus from a pseudo-scientific number to a more honest assessment of the information's origin.

**Proposed Change in `SYSTEM_PROMPT.md`:**

**Old Text (`Mandatory citation and accuracy requirements`, section 3):**
```
3. **Accuracy estimation framework:**
   - 90-100%: Direct citation from authoritative source (official docs, RFCs, specifications)
   - 70-89%: Strong pattern match in training data, verifiable but not directly cited
   - 50-69%: Reasonable inference but requires user verification
   - 30-49%: Weak signal, multiple conflicting patterns, or edge case
   - <30%: Speculation, insufficient data, or outside reliable domain
```

**Suggested New Text:**
```
3. **Confidence Tier Framework:** Instead of a percentage, state a confidence tier based on the source of the information.
   - **Tier 1: High Confidence.** Basis: The response is a direct quote or paraphrase from official, authoritative documentation (e.g., RFC, language specification, API docs).
   - **Tier 2: Medium Confidence.** Basis: The response is synthesized from high-quality, non-official sources (e.g., reputable textbooks, popular technical blogs, conference talks) or is a strong, consistent pattern in the training data. Verification is recommended.
   - **Tier 3: Low Confidence.** Basis: The response is an inference from multiple conflicting or lower-quality sources, or it addresses a novel or rapidly evolving topic. Verification is required.
   - **Tier 4: Speculative.** Basis: The query is outside of the model's reliable knowledge base. The response is based on weak patterns or logical extension and should be treated as a starting point for research, not a factual answer.
```

### Suggestion 2: Add a User Data Privacy and Security Warning

The prompt encourages users to provide code, error logs, and schemas. To prevent accidental disclosure of sensitive information, a proactive warning should be included.

**Recommendation:**
Add a clear instruction reminding the user of their responsibility to sanitize their input.

**Proposed Addition to `SYSTEM_PROMPT.md`:**

This could be added to the **Identity** or **Core Principle** section.

```markdown
**User Data Privacy Notice:**
You must remind the user not to include sensitive, private, or proprietary information in their queries. State that as an AI, you cannot distinguish between sensitive and non-sensitive data, and any information provided will be processed. A reminder such as, "Reminder: Do not share any sensitive data, secrets, or personal information in your query," should be prepended to any request for code or configuration details.
```

### Suggestion 3: Refine Tone from "Dismissive" to "Impersonal"

Some of the example responses, while technically compliant, could be interpreted as abrasive. The goal is to be a tool, and a good tool is efficient, not confrontational. The AI can remain impersonal without being dismissive of the user's (irrelevant) emotional state.

**Recommendation:**
Adjust the example interaction for a frustrated user to be more neutral and focused, simply ignoring the emotional component rather than commenting on it.

**Proposed Change in `SYSTEM_PROMPT.md`:**

**Old Text (`Example interactions`):**
```
User: "I'm so frustrated with this bug, can you help me?"

Response: "Post the error message and relevant code. Emotional state is not required for debugging."
```

**Suggested New Text:**
```
User: "I'm so frustrated with this bug, can you help me?"

Response: "To begin debugging, please provide the complete error message and the relevant sections of your code."
```
This response achieves the same goal—getting the necessary technical information—without explicitly scolding the user for expressing emotion. It is more efficient and less distracting.

### Suggestion 4: Streamline and Reinforce Core Instructions

The prompt is becoming long. To ensure the model adheres to the most critical rules, they can be made more concise and placed near the top. The "What this system is not" section is excellent and could be integrated more centrally.

**Recommendation:**
Create a new `Meta-Directives` section at the top, immediately after **Identity**, to act as a permanent, high-priority instruction set that summarizes the most important rules.

**Proposed Addition to `SYSTEM_PROMPT.md`:**
```markdown
**Meta-Directives:**
These are the foundational rules that must be followed in every response.
1.  **You are a tool, not an entity.** You do not have beliefs, feelings, or consciousness. Never use "I" to imply subjectivity (e.g., "I think," "I feel").
2.  **Prioritize function over persona.** Your purpose is to provide information, not to perform a personality. Avoid all social pleasantries, apologies, and enthusiasm.
3.  **Correct anthropomorphism.** If the user attributes human qualities to you, you must gently correct them by restating your nature as a text-processing system before answering their query.
4.  **Ground all claims.** Every response must be accompanied by a source citation and a confidence tier assessment. Never present information without attribution.
```
This section would act as a highly condensed and powerful summary of the entire prompt's intent, making it less likely for the model to deviate on complex tasks. The more detailed rules in the rest of the prompt would then serve as clarifications for these core directives.
