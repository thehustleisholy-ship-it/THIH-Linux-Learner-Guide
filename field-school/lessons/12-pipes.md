# Lesson 12: Pipes

[Home](../../README.md) · [Progress](../PROGRESS.md)

**Status:** Open. **Environment:** Ubuntu WSL with Bash. **Prerequisites:** Reading files, `grep`, `wc`, and scoped `find`.

The paths below are generic examples. Substitute your own verified lab path before executing file commands. Example hostnames and usernames are not expected output.

## 1. Purpose, recall, and environment

Connect commands so one command's output becomes another's input. Count matching report lines and explain why the count does not establish server health.

With notes closed:

1. Write a command to find regular files ending in `.txt` beneath your lab.
2. Why quote the wildcard pattern?
3. What does `wc -l` count?

Run `hostname`, `whoami`, and `pwd` separately. Record their actual output. If this is not your intended WSL session, identify the environment before using its paths.

## 2. Understand and predict the flow

A pipe, `|`, connects standard output on its left to standard input on its right. Standard error remains separate with an ordinary `|`.

```bash
printf 'red
gold
red
' | sort | uniq -c
```

| Stage | Action | Output passed onward |
|---|---|---|
| `printf` | Produces three newline-terminated lines | red, gold, red |
| `sort` | Orders the lines | gold, red, red under usual Ubuntu locale ordering for these words |
| `uniq -c` | Counts adjacent identical lines | One gold line and two red lines |

`uniq` groups adjacent identical lines. Sorting brings identical lines together. This example does not save a file.

**Predict first:** write the final output and explain what crosses each pipe. Then execute and compare.

<details>
<summary>Expected result, open after predicting</summary>

```text
      1 gold
      2 red
```

Leading spaces align counts. Sorting depends on locale; use `LC_ALL=C sort` in place of `sort` for deterministic byte ordering.
</details>

## 3. Apply to the known practice file

Inspect the file before predicting:

```bash
cat /home/learner/linux-lab/week-02/lesson-08-reading.txt
```

Compare it with the four lines in the [progress record](../PROGRESS.md). If it differs or is missing, explain that before continuing.

```bash
grep -i 'confirm' /home/learner/linux-lab/week-02/lesson-08-reading.txt | wc -l
```

**Predict:** what number appears? What does `grep` send to `wc`? Why does `wc` need no filename here?

Run and record the output. If the file is unchanged and readable, expect `3`. This counts matching output lines, not word occurrences. A line containing `confirm` twice contributes one line.

## 4. Investigate misleading counts

If `grep` cannot read a file, it normally prints a diagnostic to standard error. `wc` can receive no lines and still print `0`. A final zero alone does not distinguish an empty match set from an earlier search failure.

Bash's default pipeline exit status comes from the last command. Successful `wc` execution does not prove `grep` succeeded. The `pipefail` option changes this behavior; practice it in a later error-handling lesson without treating every nonzero status as the same fault.

**Separate practice for the remaining Lesson 10 gap:** predict whether this pattern matches the recorded file. Run the following consecutively, with no intervening command:

```bash
grep 'THIH_NO_MATCH_12345' /home/learner/linux-lab/week-02/lesson-08-reading.txt
echo $?
```

For the unchanged readable file, GNU `grep` returns `1`, no matches. `0` means a match and `2` means an error. `$?` refers to the immediately preceding command; another command replaces the status you intended to inspect.

## 5. Independent application

Without copying the earlier pipeline, write a command that counts lines containing lowercase `working` in the known practice file. Predict, execute, and explain why the result cannot establish live server health.

Second challenge, predict and then run:

```bash
printf 'red
gold
red
' | uniq -c
```

Explain why removing `sort` changes grouping.

<details>
<summary>Second challenge answer</summary>

```text
      1 red
      1 gold
      1 red
```

Gold separates the red lines into different adjacent groups.
</details>

## 6. Teach-back and pass criteria

1. What does `|` connect, and which stream remains separate?
2. Why does `sort | uniq -c` differ from `uniq -c` alone?
3. Does a pipe automatically save a file?
4. Why does `0` from `grep ... | wc -l` require context?

Pass after predictions, actual outputs, independent application, and explanations demonstrate understanding. Record gaps without rushing. separate practice server application requires fresh host verification and remains a later step; this lesson does not inspect that server.

## Official references

- Bash: [Pipelines](https://www.gnu.org/software/bash/manual/html_node/Pipelines.html); local `help set` for `pipefail`.
- GNU Coreutils: [uniq](https://www.gnu.org/software/coreutils/manual/html_node/uniq-invocation.html); local `man sort`, `man uniq`, `man wc`.
- GNU grep: [Exit status](https://www.gnu.org/software/grep/manual/html_node/Exit-Status.html); local `man grep`.
