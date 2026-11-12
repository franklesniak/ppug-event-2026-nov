<!-- markdownlint-disable MD013 -->
<!--
How to use this prompt (these notes are not part of the prompt):
- Copy everything below the heading into a new chat with no attachments.
- Use the same chat assistant and model that you use for 02-prompt-with-style-guide.md.
- Start a new chat. Turn off memory and any custom instructions that mention PowerShell style; they would change this result.
- Use a chat where no client history is visible on screen.
- Record the date and the model name, for the slide label.
- The task text is identical in both prompt files. The only difference is the first paragraph of 02, which points to the attached style guide.
-->

# Prompt Without the Style Guide

Write a PowerShell script that reports the files in a folder that are older than a given number of days, and their total size.

Requirements:

- The script takes the folder path and the number of days as parameters.
- It includes files in subfolders.
- A file is "older" when its last write time is more than the given number of days ago.
- It outputs the matching files and, at the end, their count and total size.
- It is read-only. It must not delete, move, rename, or change any file.

Reply with the complete script only.
