<!-- markdownlint-disable MD013 -->
<!--
About this prompt (these notes are not part of the prompt):
- SHOWN ON SLIDE 9 ONLY. Don't run it, and don't demonstrate anything about it during the talk.
- RECONSTRUCTED, NOT THE ORIGINAL. Frank didn't keep the prompt that he used in December 2025. This version is rebuilt from his description of it, so label it "Reconstructed: not the original prompt" on the slide.
- It was the first step in making the style guide: Frank gave a strong reasoning model (ChatGPT Pro at the time) a folder of PowerShell that he wrote himself and was proud of.
- The second step was Frank's own editing: he reworked the forensic report into instructions for humans and coding agents. That step had no prompt.
- The third step is 03-reconstructed-gap-filling-prompt.md.
- Short version for the slide: "Act as a forensic analyst. All the PowerShell in this folder was written by one person. Document their 'forensic footprint' in enough detail that another analyst could tell whether a new script was written by them."
-->

# Reconstructed Prompt: Forensic Analysis of a PowerShell Author

Act as a forensic code analyst. Every PowerShell file in the attached folder was written by the same person.

Document this author's "forensic footprint": how they write PowerShell. Cover naming and casing, formatting and layout, comments and comment-based help, parameter and function design, error handling, output, compatibility choices, and anything else that is consistent across the files.

Write the report in enough detail that I can hand it to another forensic analyst, who can use it to decide whether a new PowerShell script was written by this same person. Give an example from the files for each finding.
