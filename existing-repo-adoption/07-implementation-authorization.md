<!-- markdownlint-disable MD013 -->
<!--
How to use this prompt (these notes are not part of the prompt):
- Used in Demo 2, in the ROMSorter-BF-Part2 Codex session, after the agent returns the preflight report for 05-adoption-prompt.md.
- Send it in the SAME message as your answers: paste 06-questions-and-answers.md first, then everything below the heading of this file.
- Prompt 05 says that the agent implements only after you answer its open questions and explicitly authorize the implementation scope. Your answers in 06 approve individual items; this text is the explicit authorization.
- Check before the talk that 06 still matches the questions on screen in Part 2; the agent's questions can differ from the anticipated ones.
-->

# Authorization to Implement the Template Adoption

My answers to your questions are above. I authorize you to implement the template adoption within this scope:

- The module set, structural changes, and layout alignment that my answers approve.
- The protected-file actions that my answers approve, and no others.
- Line-ending normalization as a separately reviewed change that is line-ending-only: no content, encoding, or PowerShell behavior changes.
- Installing a supported Python tool environment, if the adoption tooling needs one.

Keep the final implementation uncommitted for inspection. Do not push, merge, rebase, or change repository settings. Record deferred manual actions and follow-up work in `_TODO-repo-init.md`.

If you reach a decision that my answers don't cover, stop and ask me instead of guessing.
