# Field School: learn, apply, explain

[Home](../README.md) · [Progress](PROGRESS.md)

## What counts as learning?

Explain the concept in your own words, predict behavior, apply it to a changed task, verify the result, and recognize what remains unknown. Independence matters more than speed.

| Stage | Action | Evidence |
|---|---|---|
| Recall | Explain a previous skill with notes closed | Your own answer |
| Understand | Explain options, arguments, scope, and effect | Plain-English interpretation |
| Predict | State expected output before running | Written prediction |
| Execute | Run one bounded step on the intended host | Actual terminal output |
| Verify | Compare prediction and result | Difference explained |
| Apply | Solve a changed task without copying | Independently chosen command |
| Teach back | Explain the skill and its limits | Brief colleague-style explanation |

## Environment and evidence

Run `hostname`, `whoami`, and `pwd` separately at session start. They help identify the reported hostname, current effective username, and working directory. They do not by themselves authenticate a remote host.

Illustrative context: Ubuntu WSL, hostname `learning-wsl`, user `learner`. The separate practice server is a separate Ubuntu server, represented here as `learning-server`. Example identifiers are not proof of present availability or health.

Use the smallest suitable dataset or search boundary. Before running a command, explain whether it reads, writes, overwrites, deletes, or changes configuration. Investigate unexpected results before continuing.

Ask: What does this prove? What remains unknown? Which fresh check would reduce that uncertainty?

## Established sequence

| Lesson | Skill | State |
|---|---|---|
| 8 | Read with `head`, `tail`, and `less`; interpret context | Passed in supplied history |
| 9 | Count with `wc`; distinguish quantity from meaning | Passed in supplied history |
| 10 | Search contents with `grep`, `-i`, and `-n` | Passed in supplied history |
| 11 | Locate regular files with scoped `find -name` | Passed in supplied history |
| 12 | Connect commands with pipes | Open; guided lesson included |
| 13 | Redirection | Planned; lesson not yet authored |
| 14 | Review and independent application | Planned; lesson not yet authored |

This records the visible sequence, not a replacement for an unseen workbook or an invented remaining curriculum. Later guided modules can cover permissions, users, processes, services, logs, networking, storage, Git, and automation after prerequisites are established.

## Build publicly

Document a question, prediction, sanitized evidence, mistake, correction, and next check. Remove credentials, tokens, personal information, and private infrastructure details from published output.

Improve one lesson on a branch, check examples and links, commit a clear explanation, and review before merging. Preserve upstream credit and check reuse permissions before redistributing third-party content outside this fork.
