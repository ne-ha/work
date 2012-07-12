* **How to convert existing git repository to use git-flow?**  

  Run *git flow init* from the repository folder just like as you would do for new repository

* **Can I still do manual branches and merges when I use git-flow?**  
  Of course you can. `git-flow` does not forbid you to keep using vanilla Git commands!
  
  So if you want to merge `master` into `develop` for whatever reason you want
  to, you can safely do so without breaking `git-flow` compatibility.  Do you
  want to manually merge a feature branch X into another feature branch Y?  Not
  a problem.  As long as you do it conciously and realize what this means for
  finishing those branches later on.
  
* **Why does git-describe not work for me?**  
  When finishing release and hotfix branches, that branch's HEAD is first
  merged into `master` and then into `develop`.  It is not the resulting new
  merge commit from `master` that is merged back into `develop`.  This means
  that a linear path from the new `develop` branch to the new `master` commit
  is not created.  Even worse, a linear path is created from the new `develop`
  branch to the *previous* `master` commit.  Although unintended, this is
  simply an effect of using the current branching rules.
  
  When using `git-describe` in these cases, you can get very confusing and
  misleading results, since `git-describe` scans the current commits linear
  history for the most recent tag it finds, which will always be the *previous*
  tag.

  If your project uses Maven, then [buildversion-plugin](https://github.com/code54/buildversion-plugin) may be your ticket.

  I will change this behaviour in the next version of the branching model
  explicitly and I will include this behavioural change in the first version of
  the Python rewrite.

  For more references to this problem, see:
  
  - Issue [#49](http://github.com/nvie/gitflow/issues/49)
  - These
  	[two](http://groups.google.com/group/gitflow-users/browse\_thread/thread/9920a7df3d1c4908/0bb18a0bf7275ad6#0bb18a0bf7275ad6)
  	[discussions](http://groups.google.com/group/gitflow-users/browse\_thread/thread/19efac724bb6418a)
	on the [git-flow-users](http://groups.google.com/group/gitflow-users)
	mailinglist.
  - Explanation and more references at [buildversion-plugin's README](https://github.com/code54/buildversion-plugin#about-git-describe)

* **Can I use it with Windows?**  
  There have been reports of Windows users using `git-flow`.
  <del>Un</del>fortunately, I have no Windows environment to test it on, but
  this [issue](http://github.com/nvie/gitflow/issues/issue/25) should be
  helpful in setting it up.

* **How does it integrate with Gerrit?**  
  ?

* **What is the 'support' branch?**  
  It's an experimental feature that is currently being worked on. When you try using it you'll get warnings telling you not to use it in production. It is essentially allows you to fork master, but once it's forked it stays forked. It has been speculated (on the blog) that this is if you have a client that has a very specific request which you wouldn't every want to use outside of that one client's version of the project. I imagine we will hear more about it when it's ready.