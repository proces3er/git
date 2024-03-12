# git

//
git blame -L 

blame portion of the file
    git blame -L 15,26 path/to/file

        git log -L 15,26:path/to/file

        get history part of the function

        git log -L :File:path/to/file

        give a function name



git blame -w -C -C -C

    -w ignore whitespace
    -C and dectect lines moved or copied in the same commit
    -C or the commit that created the file
    -C any commit at all

git log -S
    when something was changed

git reflog

git diff             // line base diff
git diff --word-diff // word based diff

git config --global rerere.enabled true
                    // REuse REcorded REsolution
                    git merge conflict to memeories the the fix.\

*********************************************************************
                    NEW STUFF


git branch --column  (git config --global column.ui auto
                      git config --global branch.sort -committerdate  // last commit shows first)

git column 


git push --force-with-lease(safe force push)
                    make sure you fetch first to make sure that you are up to date and then you can push

                    as long your reference is the last in the server in case someone has modify the file

-- use ssh to sign instead gpg
gpg|| ssh to sign commit

git coonig gpg.format ssh
git config user.singingkey ~/.ssh/key.pub
git commit -S


-- sign push 
git push --signed

-- adds this to conifg file
   adds a cron job background and do maintenance test on that repository
   too make things fast

   gc:
   commit-graph:
   prefetch:
   loose-objects:
   incremental-repack:
   pack-refs:

git maintainance start



********************************************************************************

ONLY COMBINE CHANGES FROM THE SAME TOPIC in a single commit
The perfect commit
    a.  add the right changes
    b.  compose a good commit message

a.
    1. git add specific file
    2. git diff index.html to check the changes
    3. git add -p index.html (-p to patch level what to include or not)
    
    onyl stage the changes to be committed to first stage, rest to be left to "not staged for commit"

b.
    subject = concise summary of waht happened
    body = more detailed explanation
                1. what is now differenct
                2. what the reason for the change
                3. is there anything to watch out in particularly
********************************************************************************
BRANCHING STRATEGIES

Mainline development (always be integrating)
    -few branches
    -relatively small commits
    -high-quality testing &QA standards

State, Release, and Feature Branches
    - different types of branches
    - fulfill different types of jobs

Long-running & Short-lived branches

Long-running
    -existing through the complete lifetime of the proect
    -often, they mirror stages in your dev life cycle
    -common convetion: no direct commits (quality, release bundleing/patching)

Short-lived 
    -for new features, bug fixes, refactorings, experiements
    -will be deleted after integration(merge/rebase)

Popular MODEL
Github flow:
    one long running branch
                    main        +       feature branches

Gitflow
    -more structure more rules
    -long running branch
                    main        +        develop
    -short lived 
                    features, releases, hotfixes.

********************************************************************************
git push --set-upstream origin xxxx

PULL REQUESTS
    pull request invites reviewers to provide feedback before merge

FORKS


********************************************************************************
Merge conflicts
    changes contradicts
    when integrating commits from different sources
    git merge   git rebase
    git pull
    git stash apply
    git cherry-pick

    how to undo a conflict and start over

    git merge --abort
    git rebase --abort


********************************************************************************

MERGE VS REBASE

MERGE
    1. common ancestor
    2. last commit on branch 1
    3. last commit on branch 2

    fast forward merge
        both branches share the exact same history

    merge commit


REBASE (DO NOT use rebase on commits thats pushed/shared on a remote repo,
        only to be used to clean up local commit history before merging it into shared team branch)
    Integrating with REBASE(rewrite commit history)
    git rebase branch-B
        1. git removes all commits A that happened after the common ancestor commit
        2. git applies the new commit from branch B
        3. the parked commit from A will be a new commit to the top of integrted commit from branch B

Testing
    unit test
    integration test
    end to end test