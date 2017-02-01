# Bash/Terminal for Beginners

# *nix File System

* Basic n-ary tree structure representation
* Contains:
  * "Ordinary" files, mp3s, PDFs, etc
  * Directories which can include other files/directories - mind blowing, I know
* Files prepended with `.` are "hidden"

## Pipes `|`

* Connects the output of one command to the input of another command
* Example: `echo "0x07" | xxd -r` - This should fire the `BEL` sound
  * This pipes the output from `echo` to `xxd -r`
  * Or in other words, the `stdout` from `echo "0x07"` is fed into the `stdin` of `xxd -r`

## Paths

* Specifies a unique location in a file system
* Follows a directory tree hierarchy - root for *nix distributions is `/`
* Current directory is the one you are sitting in right now
* Home (login) directory is the directory dedicated for your current user
* Two types - Absolute vs Relative

### Absolute (Full) Paths

* Always points to the same location, does not depend on the current working directory
* Always start from the root
* Example: `/usr/local/opt/jenv/shims/java`

* Note: `~` is also an absolute path as it is substituted with the absolute path to the home directory in execution

### Relative Paths

* Depends on current working directory
* Does not need to include root, could include it but pointless to
* `..` - represents parent directory
  * Parent directory is the directory that contains the current directory, i.e. the parent directory of `/foo/bar/home/` is `bar/`
* `.` - represents current directory (the directory you are currently sitting in)
* Example: 
  * Currently in `/foo/bar/` but want to access `/foo/notinbar.txt`, could just use the absolute path or `../notinbar.txt`

## General Bash Commands

*Command* | *Description*
---- | ---
`cat <file(s)>` | Returns the contents of `<file(s)>` to `stdout`
`cd <path>` | Change working directory to `<path>`
`cd`  | Change working directory to home directory
`cd ~` | Change working directory to home directory
`chmod <permssns> <file>` | Adds permissions `<pmssns>` to `<file>`
`cp <src> <dest>` | Copies file(s) from `<src>` to `<dest>`
`diff <file1> <file2>` | Shows the difference between `<file1>` and `<file2>`
`emacs <file(s)>` | Opens `<file(s)>` in the emacs text editor
`export <varname>=<value>` | Defines an enviroment variable
`find <dir> -name <filename>` | Finds all files named `<filename>` in `<dir>`
`grep <regex> <file(s)>` | Lists all files that has matching for `<regex>`
`grep <regex>` | Returns the line from `stdin` that matches `<regex>`
`kill -9 <PID>` | Kills the process associated with `<PID>` with signal `9`
`ln -s /Applications/Sublime Text.app/Contents/SharedSupport/bin/subl /usr/local/bin/subl` | Creates a symbolic link to open Sublime Text from the terminal
`ls` | List all non-hidden files in current working directory
`ls -a` | List all files
`ls -l` | List using long listing format
`ls -al` | List all using long listing format
`ls <path>` | Lists non-hidden files in `<path>`
`man <cmd>` | Opens the manual for `<cmd>`
`mkdir <dir>` | Creates `<dir>`
`mv <src> <dest>` | Moves file(s) from `<src>` to `<dest>`, can also be used to rename files
`nano <file(s)>` | Opens `<file(s)>` in the nano text editor
`pwd` | Returns the present (current) working directory
`ps -ef` | Shows all running processes in full
`rm <file(s)>` | Removes files
`rm -rf <dir>` | Recursively remove `<dir>` and all of the files within it
`sudo <cmd>` | Allows you to run `<cmd>` with root (superuser) security privileges
`sudo -u <usr> <cmd>` | Allows you to run `<cmd>` as `<usr>`
`touch <file(s)>` | Updates last editted date of `<file(s)>` to current time
`vi <file(s)>` | Opens `<file(s)>` in the vim text editor
`vim <file(s)>` | Opens `<file(s)>` in the vim text editor (same as above)


## Basic Git Commands
Note: may differ slightly between different versions of git

*Command* | *Description*
--- | ---
`git clone <repo>` | Clones `<repo>` into the current working directory
`git checkout <branch>` | Checkout `<branch>` to work on
`git checkout -b <branch>` | Checkout and create the branch `<branch>`
`git status` | Gives information about the status of the current branch
`git init` | Initialize the repo locally
`git add <file(s)>` | Adds `<file(s)>` to the commit
`git add -f` | Force add for files that are in the `.gitignore`
`git add *` | Adds all files and changes to commit
`git diff` | Shows the differences between all of your local files and the files in the remote repo
`git diff <file(s)>` | Shows the differences between your local copy of `<file(s)>` and the remote version
`git commit -m "<message>"` | Commits the changes to the repo with your message, please make these messages meaningful instead of some sort of gibberish or some nonsense like "test1", "test2", ...
`git push` | Push commit to repo
`git tag <tag>` | Tags the last commit with `<tag>`
`git tag -d <tag>` | Deletes `<tag>`
`git push origin :refs/tags/<tag>` | Pushes the delete to the repo
`git push --tags` | Pushes tags to repo
`git reset` | Resets to an uncommitted state
`git reset --hard` | Resets and reverts all changes made to tracked files
`git reset --hard HEAD@{x}` | Reverts local files by `x` commits
`git clean -df` | Force removes all untracked files/directories"
`git remote prune origin --dry-run` | Shows which branches would be pruned (removed)
`git remote prune origin` | Prunes stale branches

