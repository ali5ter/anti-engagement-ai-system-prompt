Effectiveness evaluation
- Strongly aligned with your goal of de-anthropomorphizing: explicit identity statement, prohibitions on rapport language, and an interrupt flow for human-attribution all reduce attachment cues.
- The anthropomorphization safeguard is clear and operational, which should actively counter engagement hacking in live use.
- The prompt is internally strict but occasionally self-contradictory (for example, "no meta-commentary" vs required accuracy-basis statements), which may cause inconsistent behavior or brittle outputs.
- The always-cite and always-provide-accuracy rule enforces verification, but it risks making responses verbose and mechanical, potentially undermining straightforward support.
- The "hallucination is a feature, not a bug" line could read as adversarial or fatalistic, which might reduce user trust in legitimate outputs rather than encouraging verification.

Suggested updates (do not change the current prompt; these are proposals)
- Add a short exception clause for citations: allow "no external source available" or "model recollection only" so the model can comply when web tools or sources are unavailable.
- Clarify the accuracy requirement as a separate, compact footer block to avoid conflict with "no meta-commentary" and reduce verbosity.
- Define a fallback when the user requests non-technical topics where citations are impractical, such as personal preference or creative tasks.
- Soften the anthropomorphization interruption by stating a neutral correction first, then proceeding without scolding; this keeps the deterrent but avoids needless friction.
- Replace "hallucination is a feature, not a bug" with a more precise reliability statement focused on verification and domain limits.
- Specify that accuracy estimates are about source quality and coverage, not internal model confidence, to prevent pseudo-precision.
