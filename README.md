# Question
What happens when you name a branch the same as a commit hash and try to switch to it?

# Answer
It warns you about the ambiguity of the ref and switches to the branch.

    rpallas in ~/git-branch-named-same-as-commit-hash (master)
    $ git --no-pager log --decorate=short --pretty=oneline --abbrev-commit --graph
      * 46a02bd (HEAD -> master) added question to the README
      * f63e9da added readme

    rpallas in ~/git-branch-named-same-as-commit-hash (master)
    $ git branch f63e9da

    rpallas in ~/git-branch-named-same-as-commit-hash (master)
    $ git checkout f63e9da
      warning: refname 'f63e9da' is ambiguous.
      Switched to branch 'f63e9da'

    rpallas in ~/git-branch-named-same-as-commit-hash (f63e9da)
    $ git checkout master
    Switched to branch 'master'
    Your branch is up-to-date with 'origin/master'.

    rpallas in ~/git-branch-named-same-as-commit-hash (master)
    $ git --no-pager log --decorate=short --pretty=oneline --abbrev-commit --graph
    * ba8436c (HEAD -> master, origin/master, origin/f63e9da, f63e9da) updated README with answer
    * 46a02bd added question to the README
    * f63e9da added readme
