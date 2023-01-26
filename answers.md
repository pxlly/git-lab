2.17.1
user.name=Federico Olivares
user.email=fo170521@ohio.edu
NAME
       git-add - Add file contents to the index

SYNOPSIS
       git add [--verbose | -v] [--dry-run | -n] [--force | -f] [--interactive | -i] [--patch | -p]
                 [--edit | -e] [--[no-]all | --[no-]ignore-removal | [--update | -u]]
                 [--intent-to-add | -N] [--refresh] [--ignore-errors] [--ignore-missing] [--renormalize]
                 [--chmod=(+|-)x] [--] [<pathspec>...]

DESCRIPTION
       This command updates the index using the current content found in the
       working tree, to prepare the content staged for the next commit. It
       typically adds the current content of existing paths as a whole, but
       with some options it can also be used to add content with only part of
       the changes made to the working tree files applied, or remove paths
       that do not exist in the working tree anymore.

       The "index" holds a snapshot of the content of the working tree, and it
       is this snapshot that is taken as the contents of the next commit. Thus
       after making any changes to the working tree, and before running the
       commit command, you must use the add command to add any new or modified
       files to the index.

       This command can be performed multiple times before a commit. It only
       adds the content of the specified file(s) at the time the add command
       is run; if you want subsequent changes included in the next commit,
       then you must run git add again to add the new content to the index.

       The git status command can be used to obtain a summary of which files
       have changes that are staged for the next commit.

       The git add command will not add ignored files by default. If any
       ignored files were explicitly specified on the command line, git add
       will fail with a list of ignored files. Ignored files reached by
       directory recursion or filename globbing performed by Git (quote your
       globs before the shell) will be silently ignored. The git add command
       can be used to add ignored files with the -f (force) option.

       Please see git-commit(1) for alternative ways to add content to a
       commit.

OPTIONS
       <pathspec>...
           Files to add content from. Fileglobs (e.g.  *.c) can be given to
           add all matching files. Also a leading directory name (e.g.  dir to
           add dir/file1 and dir/file2) can be given to update the index to
           match the current state of the directory as a whole (e.g.
           specifying dir will record not just a file dir/file1 modified in
           the working tree, a file dir/file2 added to the working tree, but
           also a file dir/file3 removed from the working tree. Note that
           older versions of Git used to ignore removed files; use --no-all
           option if you want to add modified or new files but ignore removed
 Manual page git-add(1) line 1/365 18% (press h for help or q to quit)
No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

	new file:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	answers.md

aleavy@odd19:~/git-lab$ 
	new file:   README.md
	new file:   answers.md
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   answers.md

no changes added to commit (use "git add" and/or "git commit -a")
aleavy@odd19:~/git-lab$ 
commit 45ba98ef834e5edf0c9db65a6261aec2983947a9 (HEAD -> master)
Author: Federico Olivares <fo170521@ohio.edu>
Date:   Wed Jan 25 18:54:07 2023 -0500

    Initial commit
No change
To https://github.com/Fico207/git-lab.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/Fico207/git-lab.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
aleavy@odd19:~/git-lab$ 
aleavy@odd19:~/git-lab$ git pull
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
From https://github.com/Fico207/git-lab
   45ba98e..11caf70  main       -> origin/main
Updating 45ba98e..11caf70
Fast-forward
 README.md | 1 +
 1 file changed, 1 insertion(+)
aleavy@odd19:~/git-lab$ 
.  ..  .git  .gitignore  README.md
aleavy@odd19:~/2400/git-lab-2$ 
