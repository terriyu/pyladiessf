pyladiessf
==========

A git playground for PyLadiesSF.

This file describes two typical workflows, one with many branches and one with only the master branch.  To get started we will practice with the single master branch workflow, then we'll add the steps for branched workflow.

It is assumed that you have installed git on your computer and you have a GitHub account.

Clone the project
-----------------

First visit the [demonstration project repository](https://github.com/stevepiercy/pyladiessf) and click the Fork button in the upper-right corner.  This will create a copy of the repository under your account on GitHub.  Sweet!

Now in your shell:

    # change directory into wherever you keep your projects
    cd ~/projects
    
    # clone your GitHub repo to a local repo on your computer
    git clone git@github.com:YOURUSERNAME/pyladiessf.git
    
    # add a remote repository that we will call "upstream" to denote its purpose
    git remote add upstream git@github.com:stevepiercy/pyladiessf.git
    
    # fetch the latest changes from the upstream repository into your local repo
    git fetch upstream

Git workflow on GitHub: single master branch
--------------------------------------------

This workflow is typically used for minor changes and documentation.

    # fetch the latest changes from the upstream repository
    git fetch upstream
    
    # merge the fetched changes with your local repository
    git merge upstream/master
    
    # add and edit some files, write tests, make your code pass tests,
    # write documentation for your code
    # you know, be a responsible open source contributor
    # now commit those changes with a descriptive message
    git commit -a -m "commit_message"
    
    # push your changes from your local repo to your GitHub repo
    git push
    
Now switch back to the GitHub website and visit your pyladiessf repository.  You should see all the latest changes that you pushed from your computer to your repo.

Now let's submit a pull request to the upstream project.  Click the button Pull Request.  You will be redirected to the upstream repo, and an issue will be generated.  This notifies by email the repo owner that a change is waiting to be merged.

Git workflow on GitHub: create a new branch
-------------------------------------------

This workflow is typically used for major changes.  Branches allow you to continue your work without affecting other developers.  When your work is ready to be merged into the master branch, you can submit a pull request.

This workflow is exactly the same as the previous, but with a couple of minor changes

    # fetch the latest changes from the upstream repository
    git fetch upstream
    
    # merge the fetched changes with your local repository
    git merge upstream/master
    
    # create a new branch for your major changes
    git checkout -b MYBRANCHNAME
    
    # add and edit some files, write tests, make your code pass tests,
    # write documentation for your code
    # you know, be a responsible open source contributor
    # now commit those changes with a descriptive message
    git commit -a -m "commit_message"
    
    # push your changes from your local repo to your GitHub repo
    git push
    
    # on the first push only (-u allows the tracking of "MYBRANCH"):
    git push -u origin MYBRANCH
    # on subsequent pushes:
    git push
