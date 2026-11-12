<!-- markdownlint-disable MD013 -->
<!--
How to use this prompt (these notes are not part of the prompt):
- Used in Demo 3, right after the adoption demo: the handoff of a task to a coding agent in the adopted ROMSorter repository.
- Before the talk: run it once in Window C (a copy of ROMSorter-BF-Part3 with the adoption committed on a local branch). That run is the one you review in Demo 3.
- During the talk: paste it live in Window B (another such copy), so the audience sees the agent receive the task. Don't wait for it; switch to Window C and review the earlier run of the same prompt.
- Keep this file here, outside the ROMSorter copies. Paste from it; don't copy it into Window B or Window C, or it shows up as an untracked file in the demo diff, and the agent may read it as repository content.
- Turn off the agent's web tools in Window B and Window C; the task needs no network. In Claude Code, for example, add a .claude/settings.local.json file to each copy with {"permissions": {"deny": ["WebFetch", "WebSearch"]}}. In Codex, use a sandbox mode without network access.
- Make sure that neither copy contains passwords, keys, or tokens.
- The column names come from Convert-MAMEDATToCsv.ps1 in ROMSorter.
- Copy everything below the heading into the agent.
-->

# Coding Agent Task: Summarize the MAME Database CSV

Add a new script at the repository root named Get-MAMEDatabaseSummary.ps1.

What it does:

- Reads a CSV file made by this project. Use a -Path parameter; the default is .\MAME_Database.csv.
- Groups the rows by one column, chosen with a -GroupBy parameter that accepts only MAME_Manufacturer, MAME_Year, or MAME_NumberOfPlayers.
- Returns one object per group with two properties, Value and Count, sorted by Count from high to low. A -Top parameter limits the number of results; the default is 10.
- Skips rows where MAME_IsBIOSROM or MAME_IsDeviceROM is True.

Rules:

- Do not change any existing script.
- Do not use the network.
- Follow this repository's instructions and PowerShell style guide.
- Add Pester tests in tests/PowerShell/ that use a new sample CSV with 12 rows in tests/fixtures/. Make up the rows. Do not copy real data files.
- Run the Pester tests and PSScriptAnalyzer with the repository settings, and fix any findings in the new files.
- Commit the change on the current branch with a clear message. Do not push.
