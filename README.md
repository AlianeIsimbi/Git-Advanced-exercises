# Git-Advanced-exercises
## Part-1
### Challenge 1
#### Git logging to check the commits made, added the forth file since I had forgot to add it then did amend for update the commit message of the last commit
```
brian@AlianeI23 MINGW64 ~/Git-Advanced-exercises (main)
$ git log
commit 7c1a80142bf699757bb3e840469fbde9a995d54c (HEAD -> main)
Author: AlianeIsimbi <isimbialiane@gmail.com>
Date:   Thu Jul 24 10:49:29 2025 +0200

    chore: Create third and fourth files

commit ef8bdc346bdf125a601ed7f6876846cf52cb51b7
Author: AlianeIsimbi <isimbialiane@gmail.com>
Date:   Thu Jul 24 10:49:00 2025 +0200

brian@AlianeI23 MINGW64 ~/Git-Advanced-exercises (main)
$ git add test4.md 

brian@AlianeI23 MINGW64 ~/Git-Advanced-exercises (main)
$ git commit --ammend -m "chore:Creat third and forth files"
error: unknown option `ammend'
usage: git commit [-a | --interactive | --patch] [-s] [-v] [-u<mode>] [--amend]
                  [--dry-run] [(-c | -C | --squash) <commit> | --fixup [(amend|reword):]<commit>]
                  [-F <file> | -m <msg>] [--reset-author] [--allow-empty]
                  [--allow-empty-message] [--no-verify] [-e] [--author=<author>]
                  [--date=<date>] [--cleanup=<mode>] [--[no-]status]
                  [-i | -o] [--pathspec-from-file=<file> [--pathspec-file-nul]]
                  [(--trailer <token>[(=|:)<value>])...] [-S[<keyid>]]
                  [--] [<pathspec>...]

    -q, --[no-]quiet      suppress summary after successful commit
    -v, --[no-]verbose    show diff in commit message template

Commit message options
    -F, --[no-]file <file>
                          read message from file
    --[no-]author <author>
                          override author for commit
    --[no-]date <date>    override date for commit
    -m, --[no-]message <message>
                          commit message
    -c, --[no-]reedit-message <commit>
                          reuse and edit message from specified commit
    -C, --[no-]reuse-message <commit>
                          reuse message from specified commit
    --[no-]fixup [(amend|reword):]commit
                          use autosquash formatted message to fixup or amend/reword specified commit
    --[no-]squash <commit>
                          use autosquash formatted message to squash specified commit
    --[no-]reset-author   the commit is authored by me now (used with -C/-c/--amend)
    --trailer <trailer>   add custom trailer(s)
    -s, --[no-]signoff    add a Signed-off-by trailer
    -t, --[no-]template <file>
                          use specified template file
    -e, --[no-]edit       force edit of commit
    --[no-]cleanup <mode> how to strip spaces and #comments from message
    --[no-]status         include status in commit message template
    -S, --[no-]gpg-sign[=<key-id>]
                          GPG sign commit

Commit contents options
    -a, --[no-]all        commit all changed files
    -i, --[no-]include    add specified files to index for commit
    --[no-]interactive    interactively add files
    -p, --[no-]patch      interactively add changes
    -o, --[no-]only       commit only specified files
    -n, --no-verify       bypass pre-commit and commit-msg hooks
    --verify              opposite of --no-verify
    --[no-]dry-run        show what would be committed
    --[no-]short          show status concisely
    --[no-]branch         show branch information
    --[no-]ahead-behind   compute full ahead/behind values
    --[no-]porcelain      machine-readable output
    --[no-]long           show status in long format (default)
    -z, --[no-]null       terminate entries with NUL
    --[no-]amend          amend previous commit
    --no-post-rewrite     bypass post-rewrite hook
    --post-rewrite        opposite of --no-post-rewrite
    -u, --[no-]untracked-files[=<mode>]
                          show untracked files, optional modes: all, normal, no. (Default: all)
    --[no-]pathspec-from-file <file>
                          read pathspec from file
    --[no-]pathspec-file-nul
                          with --pathspec-from-file, pathspec elements are separated with NUL character


brian@AlianeI23 MINGW64 ~/Git-Advanced-exercises (main)
$ git commit --amend -m "chore:Creat third and forth files"
[main 5ffae04] chore:Creat third and forth files
 Date: Thu Jul 24 10:49:29 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md

brian@AlianeI23 MINGW64 ~/Git-Advanced-exercises (main)
$ git log --oneline
5ffae04 (HEAD -> main) chore:Creat third and forth files
ef8bdc3 chore: Create another file
9a0b926 chore: Create initial file
1a5e339 (origin/main, origin/HEAD) Initial commit

```
### Challenge 2
#### Changed the commit message of the "create another file" to "create second file" using git rebase and changing the pick to edit in the text editor
```
brian@AlianeI23 MINGW64 ~/Git-Advanced-exercises (main)
$ git rebase -i HEAD~2
Stopped at ef8bdc3...  chore: Create another file
You can amend the commit now, with

  git commit --amend 

Once you are satisfied with your changes, run

  git rebase --continue

brian@AlianeI23 MINGW64 ~/Git-Advanced-exercises (main|REBASE 1/2)
$ git commit --amend -m "chore: Create second file"
[detached HEAD c58ff27] chore: Create second file
 Date: Thu Jul 24 10:49:00 2025 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

brian@AlianeI23 MINGW64 ~/Git-Advanced-exercises (main|REBASE 1/2)
$ git rebase --continue
Stopped at 5ffae04...  chore:Creat third and forth files
You can amend the commit now, with

  git commit --amend

Once you are satisfied with your changes, run

  git rebase --continue

brian@AlianeI23 MINGW64 ~/Git-Advanced-exercises (main|REBASE 2/2)
$ git rebase --continue
Successfully rebased and updated refs/heads/main.

brian@AlianeI23 MINGW64 ~/Git-Advanced-exercises (main)
$ git log
commit e582244d5369d5b53f92b04af4d699ab2882d4ea (HEAD -> main)
Author: AlianeIsimbi <isimbialiane@gmail.com>
Date:   Thu Jul 24 10:49:29 2025 +0200

brian@AlianeI23 MINGW64 ~/Git-Advanced-exercises (main)
$ git log
commit e582244d5369d5b53f92b04af4d699ab2882d4ea (HEAD -> main)
Author: AlianeIsimbi <isimbialiane@gmail.com>
Date:   Thu Jul 24 10:49:29 2025 +0200

$ git log
commit e582244d5369d5b53f92b04af4d699ab2882d4ea (HEAD -> main)
Author: AlianeIsimbi <isimbialiane@gmail.com>
Date:   Thu Jul 24 10:49:29 2025 +0200

Author: AlianeIsimbi <isimbialiane@gmail.com>
Date:   Thu Jul 24 10:49:29 2025 +0200

Date:   Thu Jul 24 10:49:29 2025 +0200


    chore:Creat third and forth files

    chore:Creat third and forth files


commit c58ff27197890f1da08c2d16353f2f42fd590784
commit c58ff27197890f1da08c2d16353f2f42fd590784
Author: AlianeIsimbi <isimbialiane@gmail.com>
Date:   Thu Jul 24 10:49:00 2025 +0200

    chore: Create second file

commit 9a0b9267368ba727719dbbaa8564b8e04e3345c3
commit 9a0b9267368ba727719dbbaa8564b8e04e3345c3
Author: AlianeIsimbi <isimbialiane@gmail.com>
Author: AlianeIsimbi <isimbialiane@gmail.com>
Date:   Thu Jul 24 10:48:46 2025 +0200

    chore: Create initial file

commit 1a5e33970e1b58d82ab412c70a10aeded491b68c (origin/main, origin/HEAD)
Author: Aliane ISIMBI <117778528+AlianeIsimbi@users.noreply.github.com>
Date:   Thu Jul 24 10:45:09 2025 +0200

    Initial commit
```
### Challenge 3
#### Did git rebase and changed pick to squash in the text editor in order to squash the "create second file" with "create initial file"
```
brian@AlianeI23 MINGW64 ~/Git-Advanced-exercises (main)
$ git rebase -i HEAD~4
[detached HEAD 3018fb3] chore: Create initial file
 Date: Thu Jul 24 10:48:46 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.
```
### Challenge 4
#### splitted one commit by replacing pick with edit then using git reset to change the commit into two
```
brian@AlianeI23 MINGW64 ~/Git-Advanced-exercises (main)
$ git rebase -i HEAD~4
Stopped at a4a2940...  chore:Creat third and forth files
You can amend the commit now, with

  git commit --amend

Once you are satisfied with your changes, run

  git rebase --continue
brian@AlianeI23 MINGW64 ~/Git-Advanced-exercises (main|REBASE 2/4)
$ git reset HEAD~1

brian@AlianeI23 MINGW64 ~/Git-Advanced-exercises (main|REBASE 2/4)
$ git add test3.md

brian@AlianeI23 MINGW64 ~/Git-Advanced-exercises (main|REBASE 2/4)
$ git commit -m "chore:Create third file"
[detached HEAD d8c5916] chore:Create third file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

brian@AlianeI23 MINGW64 ~/Git-Advanced-exercises (main|REBASE 2/4)
$ git add test4.md

brian@AlianeI23 MINGW64 ~/Git-Advanced-exercises (main|REBASE 2/4)
$ git commit -m "chore:Create forth file"
[detached HEAD 7e72d17] chore:Create forth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md

brian@AlianeI23 MINGW64 ~/Git-Advanced-exercises (main|REBASE 2/4)
$ git rebase --continue
Successfully rebased and updated refs/heads/main.

```