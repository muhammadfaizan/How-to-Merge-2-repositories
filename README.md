# How to Merge 2 repositories

You never know if you need to combine two projects into one. If you ever want to, it should be fairly simple and straightforward to do it.
Use Cases:

    If there are two similar libraries and both of the maintainers come together to combine it.
    And sometimes, you don’t have a choice but to have a single repository for the project.

I have used Repo A and Repo B and Repo C for demonstrating the purpose.

    Repo A
    Repo B
    Repo C: This is the Repo C where I want to merge Repo A and Repo B.

## Steps to merge git repositories

I assume you are in the directory, where you want to merge the repositories, for me, it is **Repo C**.

    $ git remote add -f repo-a git@github.com:vaibhavmule/repo-a.git

This command will add a remote URL of *repo-a*.

    git merge repo-a/master

Now the merging starts, it is as simple as merging any branch. This command will merge all the files and folders from *repo-a/master*.

    fatal: refusing to merge unrelated histories

Oops, in the real-world scenarios, it is not as simple as you think, you have to add `—allow-unrelated-histories` to actually getting it to work.

    git merge repo-a/master --allow-unrelated-histories

By this time, you have successfully merged the master branch of repo-a to repo-c, for the reward you are ready to grab a coffee.

Wait, you might have got merge conflicts, resolve that and get your coffee.
## Repeat same steps for Repo B,

    git remote add -f repo-b git@github.com:vaibhavmule/repo-b.git
    git merge repo-b/master --allow-unrelated-histories

By this time, I was smarter and I knew that I’m going to get an error: `fatal: refusing to merge unrelated histories`, so added allow-unrelated-histories beforehand.

I’m aware that I’m gonna get some merge conflicts, so, I resolved it.

You should `git log` in your terminal, you will be able see commit history as expected.

### Screenshot of commits of Repo C
[![N|Solid](https://raw.githubusercontent.com/muhammadfaizan/How-to-Merge-2-repositories/master/1*dHyElvtz0JT_Wo95lDlSqQ.png)](https://nodesource.com/products/nsolid)


**DISCLAIMER: To Read full post from source: [How to merge two or multiple git repositories into one](https://medium.com/altcampus/how-to-merge-two-or-multiple-git-repositories-into-one-9f8a5209913f)**
