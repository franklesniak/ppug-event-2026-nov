<!-- markdownlint-disable MD013 -->
# Getting Started with Coding Agents: Clean Handoffs of PowerShell Script Tasks

Prompts and supporting materials for Frank Lesniak's talk at the [Pacific PowerShell User Group](https://www.meetup.com/pacific-powershell-user-group/), on Wednesday, November 11, 2026 (virtual, 6 p.m. Pacific).

## About the talk

By now, you've heard of coding agents, but maybe you think they aren't very good at PowerShell. This session aims to change your mind. With the right setup, a coding agent can take on a script task and hand back code that follows a style guide and passes its tests.

The talk has two acts:

1. **Chat and a style guide.** The same request goes to a chat assistant twice: once with no style guide, and once with [PSStyleGuide](https://github.com/franklesniak/PSStyleGuide). The talk also shows how that style guide was made.
2. **Coding agents and a template.** [copilot-repo-template](https://github.com/franklesniak/copilot-repo-template) is added to an existing PowerShell repository, [ROMSorter](https://github.com/franklesniak/ROMSorter). Then a coding agent gets a task in that repository, and its work is reviewed: the diff, the Pester results, and the PSScriptAnalyzer results.

## What's in this repository

The prompts are numbered in the order the talk uses them. Each file starts with usage notes in an HTML comment; when you use a prompt, copy only the text below its heading.

| # | File | Where the talk uses it | What it does |
| --- | --- | --- | --- |
| 01 | [`01-prompt-without-style-guide.md`](powershell-style-guide/01-prompt-without-style-guide.md) | Act 1 | Asks a chat assistant for a small, read-only PowerShell script, with no style guide. |
| 02 | [`02-reconstructed-forensic-analysis-prompt.md`](powershell-style-guide/02-reconstructed-forensic-analysis-prompt.md) | Act 1 (shown on a slide only) | The first step in making the style guide: a forensic analysis of how one author writes PowerShell. **Reconstructed, not the original prompt.** |
| 03 | [`03-reconstructed-gap-filling-prompt.md`](powershell-style-guide/03-reconstructed-gap-filling-prompt.md) | Act 1 (shown on a slide only) | The last step: fill gaps in the style guide from the two community guides in its [acknowledgments](https://github.com/franklesniak/PSStyleGuide/blob/HEAD/ACKNOWLEDGMENTS.md). **Reconstructed, not the original prompt.** |
| 04 | [`04-prompt-with-style-guide.md`](powershell-style-guide/04-prompt-with-style-guide.md) | Act 1 | The same request as 01, told to follow PSStyleGuide. |
| 05 | [`05-adoption-prompt.md`](existing-repo-adoption/05-adoption-prompt.md) | Act 2, adoption | Starts the adoption of copilot-repo-template into an existing repository. The agent reviews both repositories, scores the module options, asks questions, and stops without changing anything. |
| 06 | [`06-questions-and-answers.md`](existing-repo-adoption/06-questions-and-answers.md) | Act 2, adoption | Answers prepared for the agent's questions. They are specific to ROMSorter. |
| 07 | [`07-implementation-authorization.md`](existing-repo-adoption/07-implementation-authorization.md) | Act 2, adoption | The explicit go-ahead to implement, sent in the same message as the answers. |
| 08 | [`08-open-pull-request.md`](existing-repo-adoption/08-open-pull-request.md) | Act 2, adoption | Commits the adoption, pushes it, and opens a pull request. |
| 09 | [`09-agent-task-prompt.md`](coding-agent-task/09-agent-task-prompt.md) | Act 2, handoff | The task handed to the coding agent in the adopted repository: a new script and its Pester tests. |

## Use these prompts in your own work

### Compare a chat assistant with and without a style guide

1. Run prompt 01 in a new chat, and prompt 04 in a second new chat. Use the same model for both, and turn off memory and custom instructions, so the style guide is the only difference.
2. Prompt 04 points the assistant to the style guide's raw URL, so the chat needs web access. The guide is long; if the reply ignores rules from its later sections, paste the contents of [`STYLE_GUIDE_CHAT.md`](https://github.com/franklesniak/PSStyleGuide/blob/HEAD/STYLE_GUIDE_CHAT.md) instead. That version is formatted for chat.
3. Compare the two scripts yourself. One run of each is an example, not a measurement.

### Add copilot-repo-template to your existing repository

1. **Install Python first.** The template's module selection and testing scripts use it, and so does pre-commit.
2. **Use the template's latest adoption prompt.** Prompt 05 is a copy of "Prompt 0: Existing Repository Adoption Preflight" from the template's [`COPILOT_CHAT_PROMPTS.md`](https://github.com/franklesniak/copilot-repo-template/blob/HEAD/COPILOT_CHAT_PROMPTS.md), taken at commit [`2f6aa17`](https://github.com/franklesniak/copilot-repo-template/blob/2f6aa17caa063eaa0b39afb3afb1d27757b4eec3/COPILOT_CHAT_PROMPTS.md#prompt-0-existing-repository-adoption-preflight). The template changes often, so start from its current version.
3. **Answer the agent's questions yourself.** Prompt 06 holds the answers for ROMSorter; use it as an example of the decisions involved, not as answers for your repository.
4. **Authorize the work explicitly.** Send your answers together with an authorization like prompt 07, and change its scope to match what you approved.
5. **Review before you commit.** Prompt 07 asks the agent to leave the result uncommitted. Read the changes, then commit them or open a pull request (prompt 08). The template's [existing-repository guide](https://github.com/franklesniak/copilot-repo-template/blob/HEAD/GETTING_STARTED_EXISTING_REPO.md) estimates 15 to 60 minutes for an adoption.

### Hand a coding agent a task

Prompt 09 is specific to ROMSorter's data, but its shape works for any task:

- Say what the new code does, with the parameters and the output that you expect.
- Say what the agent must not do (for example, change existing scripts or use the network).
- Say which tests to add, with made-up sample data, and which checks to run before it commits.

Then review the result the way you'd review a coworker's change: read the diff, run the tests, run the analyzer, and decide whether to keep it. The agent does the typing; you still decide.

## About ROMSorter

ROMSorter is a hobby project: PowerShell scripts that take public metadata lists about arcade games (names, file lists, and checksums) and build one catalog from them. It works with metadata only. It doesn't download or share any games.

## Related projects

- [copilot-repo-template](https://github.com/franklesniak/copilot-repo-template): a template repository with agent instructions, style guides, linting, tests, and CI, split into modules.
- [PSStyleGuide](https://github.com/franklesniak/PSStyleGuide): a PowerShell style guide written for humans and coding agents.
- [ROMSorter](https://github.com/franklesniak/ROMSorter): the existing repository used in the demos.

## About the speaker

Frank Lesniak. Links to his social media profiles are at [linktr.ee/franklesniak](https://linktr.ee/franklesniak).

## License

This repository is released under the [MIT License](LICENSE). Prompt 05 is copied from [copilot-repo-template](https://github.com/franklesniak/copilot-repo-template), which is also released under the MIT License.
