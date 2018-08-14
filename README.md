git-rinfo — status overview of all repos in a given directory
=============================================================

Useful for quickly checking a bunch of cloned repositories to find ones which
are up-to-date with the remote and can be deleted locally.

Usage
-----

    cd ~/repos
    ./git-rinfo

Output
------

    ## bsc-thesis
         22 ignored
        remote origin
            FATAL: R any bsc-thesis nst DENIED by fallthru
            (or you mis-spelled the reponame)
            fatal: Could not read from remote repository.
            Please make sure you have the correct access rights
            and the repository exists.

    ## intrace
            clean
        remote origin
            git@github.com:Fusl/intrace.git
            up to date

    ## project_1
          3 untracked
         14 ignored
        remote origin
            git@github.com:johndoe/project_1.git
            local out of date

    ## studip-fuse.n-st
            clean
        remote niko
            git@github.com:N-Coder/studip-fuse.git
            next fetch will store in remotes/niko
            local out of date
            up to date
        remote origin
            git@github.com:n-st/studip-fuse.git
            up to date

    ## wireless-regdb
          2  M
          4 untracked
          2 ignored
        remote origin
            git://git.kernel.org/pub/scm/linux/kernel/git/sforshee/wireless-regdb.git
            local out of date

Notes:

* Error messages during `git remote update` are passed through. (see `bsc-thesis`)
* If there are multiple branches, their states are aggregated, i.e. each state
  (up to date, out of date, …) is only printed once). The actual branch names
  are omitted. (see `studip-fuse.n-st`)
