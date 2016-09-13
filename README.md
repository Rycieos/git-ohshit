# git-ohshit
Git plugin to fix the stupid thing you just did

git-ohshit will attempt to "undo" the stupid thing you did. It will detect what
the last change was and run the correct git command to put the repo back the way
it was. Note that this is not a true undo; as git will never delete a commit,
just remove a reference to it. It will also only "undo" the very last thing that
was done in a repo by default; it will not fix things in the past, as such
things can get extremely complicated and this is meant to be a simple command;
along the lines of `sudo !!`. Calling with a subcommand can "undo" things
farther in the past, use with care!

Note: Doing a `git ohshit` after a `git ohshit` should simply undo the first.

This was a project to help me learn more about git. While it does work, note
that whatever you do with it should never be to rewrite public git history!

## Examples:
Did a `git commit --all`?  
Do a `git ohshit`!

Did a `git merge master`? (instead of `git merge dev`)  
Do a `git ohshit`!

## Install:
Simply download and stick `git-ohshit` anywhere in your path. Assuming ~/bin
exists and is in your $PATH:  
`cd ~/bin && wget https://raw.githubusercontent.com/Rycieos/git-ohshit/master/git-ohshit && chmod +x git-ohshit`

## FAQ:

Q: Why can't I use this to fix a `git add <file>`?  
A: Because those changes are not tracked, so they can't be easily discovered,
    and because there is an easy command for that: `git reset <file>`.

Q: Why does it print out whatever it is doing? That is annoying and I want to
    use this plugin for all my git stuff!  
A: Because this is meant as a learning plugin: it prints what it is doing so you
    learn what it does and can do it for yourself.

Q: Ugh, why sh instead of bash? Bash is way better!  
A: I agree, but for best portability, POSIX sh is needed. Also, knowing POSIX is
    a very important skill.
