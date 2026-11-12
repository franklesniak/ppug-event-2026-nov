<!-- markdownlint-disable MD013 -->
<!--
How to use this prompt (these notes are not part of the prompt):
- Used in Act 1 of the talk (chat, before any coding agent appears). Its output is shown live on slide 7, in the problem segment.
- Run it before the talk in chatgpt.com, in a new chat with no attachments. Don't generate anything live.
- Use the same chat assistant and model for 04-prompt-with-style-guide.md, so the only difference between the two outputs is the style guide.
- Turn off memory and any custom instructions that mention PowerShell style; they would change this result.
- Collapse the chat history sidebar before the talk; past chats can show client names.
- Record the date and the model name, for the slide label.
- The task text is identical in 01 and 04. The only difference is the first paragraph of 04, which points to the style guide.
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
