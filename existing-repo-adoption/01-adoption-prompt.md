<!-- source: https://github.com/franklesniak/copilot-repo-template/blob/2f6aa17caa063eaa0b39afb3afb1d27757b4eec3/COPILOT_CHAT_PROMPTS.md#prompt-0-existing-repository-adoption-preflight -->

# Prompt for Adoption of `copilot-repo-template` Into an Existing Repository

I want to adopt `franklesniak/copilot-repo-template` into this existing repository.

Please treat this first response as discovery and preflight only. Do not edit files, stage changes, commit, rename branches, merge/rebase/pull the template, change repository settings, install dependencies, run fixers/formatters, normalize line endings, or otherwise start implementation yet. Stop after the preflight report even if you believe no questions remain.

First, fetch and review the latest upstream template repository:

- Read `TEMPLATE_UPDATE_PROCEDURE.md` in detail.
- Also review the existing-repository getting-started guide, `.template-sync/manifest.yml`, `.template-sync/instruction-contracts.yml`, and the template-sync helper scripts closely enough to follow the current adoption procedure.
- Resolve and report the exact upstream template commit SHA reviewed.
- If a `template` remote already exists, fetch it. If it does not exist, inspect the template using `git ls-remote`, a temporary clone, or another non-destructive method where practical. You may add a local `template` remote only if needed for accurate analysis, and you must report that local metadata change.
- Do not run `git pull template main`, `git merge template/main`, or `git rebase template/main`.

Then examine this downstream repository carefully:

- Determine whether this is first adoption or an initialized template sync by checking for `.template-sync/marker.yml`, `_TODO-repo-init.md`, or an equivalent committed adoption note.
- Inspect the working tree and report any existing tracked, untracked, or staged changes. Do not clean, revert, format, move, or normalize existing files during preflight.
- Inspect the current branch, remotes, default branch, existing CI, scripts, docs, issue/PR templates, security/conduct files, CODEOWNERS, agent instruction files, and language/tooling stacks.
- Preserve downstream project identity and existing repository-specific behavior.
- Assess the repository against current conventions, industry defaults, and the template’s assumptions. Look for structural or tooling deviations that should be addressed either during adoption or afterward.
- Assume I am open to reasonable repository reorganization when it materially improves template adoption, but propose and score the reorganization before implementing it.

For first adoption, apply the template’s first-adoption preflight model:

- Identify discoverable repository facts yourself.
- Do not invent manual GitHub settings, reporting channels, CODEOWNERS identities, branch protection/ruleset policy, label state, Discussions state, private vulnerability reporting state, GHES hostnames, or adoption modes.
- However, do not silently leave important governance or community decisions unresolved. If a decision is needed to configure adopted files properly, ask me directly during preflight instead of guessing.
- If I intentionally defer a required manual action or maintainer policy decision, plan to record it in `_TODO-repo-init.md`.
- If GitHub settings cannot be safely queried or changed with available tooling, distinguish between facts that are unknown, decisions I need to make, and manual follow-up actions that should be recorded.
- If GitHub settings are involved, verify current official GitHub documentation before recommending branch protection/ruleset, default branch, Discussions, label, or security-reporting configuration.
- If Azure DevOps Services settings are involved, verify current Microsoft Learn documentation before recommending Azure Repos PR templates, branch policies, required reviewers, Copilot review enablement, Azure Boards linkage, or Azure DevOps security/dependency automation choices.
- Do not invent Azure DevOps organization, project, repository, branch-policy, billing, Copilot preview, or service-connection state. If Azure DevOps connector/API tooling is unavailable or insufficient, distinguish unknown facts from owner decisions and manual follow-up actions.

Pay special attention to these maintainer decisions:

- For public repositories, determine whether security reporting should use GitHub private vulnerability reporting, a public security contact, both, or an intentional deferral.
- If a security email or contact is needed, ask me what contact to use rather than inventing one.
- For Code of Conduct files, ask what contact email or maintainer contact wording should be listed.
- For CODEOWNERS, ask which GitHub user or team should own the adopted files if it cannot be inferred.
- If the default branch is not `main`, ask whether I want to keep the current default branch or plan a future rename to `main`.
- Determine whether labels expected by the template, such as triage or review-flow labels, already exist. If they do not, ask whether they should be created during adoption, deferred to `_TODO-repo-init.md`, or omitted.
- Determine whether Discussions, branch protection, rulesets, private vulnerability reporting, and other repository settings are enabled when tooling allows. If tooling does not allow safe verification or configuration, ask what policy I want and record any deferred manual action.

For module selection:

- Derive possible modules from the current `.template-sync/manifest.yml`; do not assume a stale module list.
- Treat GitHub and Azure DevOps host modules as host-specific choices. GitHub remains the default for GitHub-hosted repositories; Azure DevOps Services support is additive through the Azure DevOps modules and should not make Azure DevOps mandatory for GitHub-only adopters.
- Use `docs/azure-devops-support.md` as the durable template reference for Azure DevOps Services hosting, security scanning, dependency-update, and service-validation boundaries.
- Consider all plausible module selections and meaningful permutations for this repository. You may group invalid, dominated, redundant, or nonsensical permutations, but explain why they were grouped instead of individually scored.
- Develop a defensible evaluation rubric.
- Score the options in a table.
- Recommend the best module set, including any modules that should be deferred or explicitly excluded.
- Surface unknown modules, unmapped paths, and cross-module dependencies for owner decision.

For repository structure and convention alignment:

- Identify structural changes required to align with selected template modules.
- Identify structural changes that are not strictly required but would bring the repository closer to common conventions or best practices.
- Classify each proposed structural change as one of:
  - Required for template adoption
  - Recommended during template adoption
  - Recommended as a post-adoption follow-up
  - Not recommended
- Consider meaningful alternatives and permutations rather than assuming the first reasonable layout.
- Develop a rubric and scoring table for repository reorganization options.
- Recommend which structural changes belong in the adoption itself and which should become follow-up work.
- For recommended post-adoption work, draft one or more GitHub Issues sized appropriately for a sophisticated coding agent to complete after template adoption. The issue descriptions should assume template adoption has already been completed.

For protected files and template-derived governance/collaboration files:

- Treat protected instruction files as requiring explicit path-scoped owner authorization before create/edit/delete/rename/removal. This includes `.github/copilot-instructions.md`, `.github/instructions/*.instructions.md`, `.cursor/rules/*.mdc`, `.hermes.md`, `AGENTS.md`, `CLAUDE.md`, and `GEMINI.md`.
- Treat the protected-file list above as examples plus the current template procedure/manifest’s authoritative protected set. If the current upstream template defines additional protected instruction, governance, or collaboration files, include them.
- Do not treat general permission to adopt the template as permission to rewrite protected files.
- Do not treat `minimal-preservation` as protected-file edit authorization.
- Use `minimal-preservation` as the default adoption mode: preserve upstream wording and structure, substitute placeholders, remove complete delimited sections for unadopted modules, fix broken links, and record required local overrides.
- Propose `tailored` adoption only for specific files or file sets where broader downstream rewriting is genuinely justified.
- If protected files need edits, list each path, proposed decision, adoption mode, scope, reason, and exact authorization question.
- Preserve any required instruction-contract anchors unless I explicitly authorize and record a waiver/removal. Pay particular attention to retained agent protocols such as code-review handling and automated review-loop sections.
- Preserve host-specific review protocols only when their required modules are retained or explicitly authorized. GitHub-only adopters should not be required to keep Azure DevOps-only instruction-contract anchors unless they retain the relevant Azure DevOps module.

For implementation planning:

- Explain whether the adoption should use full reconciliation, first-sync delta review, or another mode supported by the current procedure.
- Explain when and how the adoption ledger should be generated or reviewed before editing protected or template-derived governance files.
- Identify validation commands that would apply to the selected modules, including first-adoption working-tree checks if template-sync support is retained.
- If newly adopted validators surface existing repository debt, plan to classify each issue as upstream-template fix, downstream-local fix, or deferred follow-up.
- Do not set or propose setting `template_sync.last_reviewed_template_commit` as durable completed state until the corresponding upstream commit has actually been reviewed through the selected adoption process and the adoption is finalized.

Your response should include:

1. The upstream template commit SHA reviewed.
2. A concise summary of this repository’s current state.
3. The module-selection options, rubric, scoring table, and recommendation.
4. Any proposed repository reorganization options, rubric, scoring table, and recommendation.
5. A classification of structural changes as required for adoption, recommended during adoption, recommended post-adoption, or not recommended.
6. Draft GitHub Issue descriptions for recommended post-adoption work.
7. Protected-file candidates and the exact authorization questions needed, if any.
8. Manual GitHub settings or maintainer policy decisions that cannot be safely inferred.
9. Direct questions I need to answer before implementation, especially for security reporting, Code of Conduct contact, CODEOWNERS, labels, Discussions, branch protection/rulesets, and default branch policy.
10. A proposed validation plan.
11. Any remaining questions you cannot answer or figure out on your own.

After I answer the open questions and explicitly authorize the implementation scope, proceed only within that authorized scope using explicit per-file decisions and preserving downstream customizations.
