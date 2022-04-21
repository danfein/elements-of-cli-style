# Status and information

## Pihole (DNS Adblocker)

```
$ pihole status
  [✓]FTL is listening on port 53
    [✓] UDP (IPv4)
    [✓] TCP (IPv4)
    [✓] UDP (IPv6)
    [✓] TCP (IPv6)
```
Uses a positional argument instead of a flag.

## Git (version control)

```
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   alerts.md
	modified:   confirmation.md
	modified:   help.md
	modified:   prompts.md
	modified:   troubleshooting.md
	modified:   update.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	progress.md
	status.md

no changes added to commit (use "git add" and/or "git commit -a")
```
Returns context (branch) and status (up to date)
Shows what changes could be saved, what changes will be included and what changes will be ignored.