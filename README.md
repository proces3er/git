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

