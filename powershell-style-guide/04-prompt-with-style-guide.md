<!-- markdownlint-disable MD013 -->
<!--
How to use this prompt (these notes are not part of the prompt):
- Used in Act 1 of the talk (chat, before any coding agent appears). Its output is shown live on slide 10, in the style-guide segment.
- Run it before the talk in chatgpt.com, in a new chat, with the same model as 01-prompt-without-style-guide.md. Don't generate anything live.
- The prompt points the assistant to the style guide's raw URL, so web access must be on in that chat. The guide is about 150 KB, and a chat assistant may read only part of a long page. If the reply ignores rules from the later sections of the guide (for example, error handling or output streams), paste the contents of STYLE_GUIDE_CHAT.md from https://github.com/franklesniak/PSStyleGuide instead, and change the first paragraph to "Follow the PowerShell style guide above...". STYLE_GUIDE_CHAT.md is formatted for pasting into chat.
- Turn off memory and any custom instructions that mention PowerShell style.
- Collapse the chat history sidebar before the talk; past chats can show client names.
- Record the date and the model name, for the slide label.
- The task text is identical in 01 and 04. The only difference is the first paragraph below.
-->

# Prompt With the Style Guide

Read the PowerShell style guide at https://raw.githubusercontent.com/franklesniak/PSStyleGuide/refs/heads/main/STYLE_GUIDE.md, and follow its instructions for all the code that you write.

Write a PowerShell script that reports the files in a folder that are older than a given number of days, and their total size.

Requirements:

- The script takes the folder path and the number of days as parameters.
- It includes files in subfolders.
- A file is "older" when its last write time is more than the given number of days ago.
- It outputs the matching files and, at the end, their count and total size.
- It is read-only. It must not delete, move, rename, or change any file.

Reply with the complete script only.
