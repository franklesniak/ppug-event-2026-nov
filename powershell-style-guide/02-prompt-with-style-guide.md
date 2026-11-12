<!-- markdownlint-disable MD013 -->
<!--
How to use this prompt (these notes are not part of the prompt):
- Use a chat assistant that can read web pages, and make sure web access is turned on for the chat. The prompt points the assistant to the style guide's raw URL; nothing is attached.
- The style guide is about 150 KB. Some assistants read only part of a long page, or summarize it. If the reply ignores rules from the later sections of the guide (for example, error handling or output streams), the assistant probably didn't read the whole file. Then attach STYLE_GUIDE.md from https://github.com/franklesniak/PSStyleGuide instead, and change the first paragraph to "Follow the attached PowerShell style guide...".
- Copy everything below the heading into a new chat.
- Use the same chat assistant and model that you use for 01-prompt-without-style-guide.md.
- Start a new chat. Turn off memory and any custom instructions that mention PowerShell style.
- Use a chat where no client history is visible on screen.
- Record the date and the model name, for the slide label.
- The task text is identical in both prompt files. The only difference is the first paragraph below.
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
