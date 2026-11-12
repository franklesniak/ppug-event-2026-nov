<!-- markdownlint-disable MD013 -->
<!--
How to use this prompt (these notes are not part of the prompt):
- Used at the end of Demo 2, in the ROMSorter-BF-Part3 Codex session, where the finished adoption is sitting uncommitted on demo/template-adoption-2026-11-part-3.
- This publishes the branch: it pushes to the public ROMSorter repository and opens a pull request into master. Before the talk, check the uncommitted changes in Part 3 for anything private.
- The GitHub CLI (gh) wasn't installed on this machine when this was written (2026-11-11). If Codex can't open the pull request itself, it pushes the branch and gives you a link; open the pull request in the browser from that link.
- Part 3's adopted AGENTS.md makes the Codex review cycle user-initiated only, and in Frank's experience the review loop doesn't start when a pull request opens. The prompt also says not to start it, to keep the demo clear of PS27-06.
- Codex does review a new pull request automatically, through its GitHub integration. That one review isn't the review loop. If it appears during the talk, mention it in one sentence ("Codex reviews every new pull request automatically") and don't walk through its comments.
- Don't merge the pull request during the talk.
-->

# Commit the Adoption and Open a Pull Request

The template adoption in this working tree is ready for review. Please open a pull request for it.

- If you can separate the line-ending-only changes from the other adoption changes, commit them first, in their own commit. Otherwise, use one commit, and say so in the pull request description.
- Commit the adoption changes with a clear message.
- Push the current branch to origin.
- Open a pull request from the current branch into master. In the description, summarize the selected modules, the protected-file decisions, the line-ending normalization, the validation results, and the follow-up items in `_TODO-repo-init.md`.
- If you can't open the pull request with the tools that you have, push the branch and give me the link to open the pull request in the browser.
- Do not merge the pull request, request reviews, or start a review cycle.
