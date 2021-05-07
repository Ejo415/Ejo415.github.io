---
layout: post
title:      "GitHub and YOU"
date:       2021-05-07 20:06:50 +0000
permalink:  github_and_you
---


Ok last week we touched on the basics of Git, THIS we're gonna get into the basics of GitHub and its workflow.

GitHub is a hosting platform for your Git repositories, it allows you to actualy see them online and share them/collaborate with other developers. Ok so the first step is a doozy so hold on to something.

###### Basics

Make an account, ill give you a minute to recover.

Better? ok cool.

To link a repo to GitHub first thing you're gonna wanna do is hit the big ol green button that says "new". From there you'll be prompted to name the repo and the owner. Choose public or private for the repo (im not 100% if the amount of private repos you can have is limited without paying, it used to be apparently and I really have no clue where they stand now). If you're *CREATING* the repoistory in github choose the 3 check boxes for adding a readme, including a .gitignore and choosing a license, odds are you'll probably have already spun something up in your code editor so ignore those if you have.

From there just click "create repository" and next you'll be prompted with a few options depending if you're linking an already existing repo to GitHub or starting from scratch right then and there. Again, odds are you'll probably have started the project in some respect so *ASSUMING* you've already run `git init` and commited some things we'll go with option 2. Run `git remote add origin (whatever link github gives you to put here)` followed by `git push -u origin main` 

Congratulations. Your project is now linked to GitHub for all the world to see. 

###### Playing Nice With Others

Now we're on to the fun part of collaborating with others. If you want to add collaborators to your project you can do so in the security section of the specified repository. If any changes have been made by collaborators on a project and you wish to sync the GitHub version with the version on your machine enter `git pull origin main` (or instead of main, whatever branch you're working on) and if you want to push to another branch that isnt the main branch just type `git push -u origin (branch name)` Back on GitHub you can switch between branches using the dropdown on the lefthand side.

Ok now if you're working on a pre-existing or open source project and you want bring that code down to your machine first thing you'll want to do is fork the code by pressing the fork button on the repository page on GitHub (forking makes a copy of the repo and saves it to your own account so you can do whatever you want to it without it effecting the main version of it)

After the project is forked you want to clone it down. Hit the green code button and copy the link there, now go into your terminal and enter `git clone (link)` (please make sure you're not doing this while you're already cd'd into another repository) now cd into the new folder and open it in your code editor and you're good to go.

Ok, so, now that you've done some work in this forked and clones repository and made some commits. Its time to get your changes added to the original project.

If you go to YOUR version of the repository you should see a notification telling you that the your version is x number of commits ahead of the main version. There will be a button that says New Pull Request, hit that and provide a description of what is is youve done and hit submit. Provided that the project owner accepts your changes will now be merged onto original project and you'll have contributed something! Hooray.

On the flip side of this if its YOUR project getting PRs submitted to it Youll see the request, including the differences in the code base that have been made. And the option to reject, accept, accept with comment or submit feedback before accepting. 

Ok That was a little text heavy and im REALLY hoping all that made sense and wasnt just rambling nonsense. 

Until next week.




