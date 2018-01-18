# Basics of Github (with Pictures)

This is an introduction to using git on the command line and GitHub.

* [What is git? (and what is GitHub?)](https://github.com/leoneckert/basics-of-github-with-pictures/#what-is-git-and-what-is-github)
* [Make a GitHub account](https://github.com/leoneckert/basics-of-github-with-pictures/#make-a-github-account)
* [Work on your own project](https://github.com/leoneckert/basics-of-github-with-pictures/#work-on-your-own-project)
* [Use/Extend on someone else's project](https://github.com/leoneckert/basics-of-github-with-pictures/#useextend-on-someone-elses-project)
* [Simple collaboration](https://github.com/leoneckert/basics-of-github-with-pictures/#simple-collaboration)
* How to NOT expose sensitive/personal data: .gitignore
* Everything broke? Go back to an old version of you project

## What is git? (and what is GitHub?)

Benefits. Go back in time, try out stuff without fear of loosing changes! (extend)

All this has something to do with saving our work, specifically code related things we produce. Let's start by looking at the most "normal" way of saving files. Every time we save, we overwrite the old version of the file we are working on,  a bit like this:

![overwriting](https://github.com/leoneckert/basics-of-github-with-pictures/blob/master/imgs/saving.gif)

Git, and let's don't even think of GitHub yet, is a framework that we can use on our computer for a different kind of saving behaviour: version control. It means that aside from saving our file and overwriting what it was saved as before, we also save all the versions before, too. In other words, all the changes done to the file are being tracked over time. This also allows to go back to older versions of a file or to branch of in different directions to try out thing (e.g. "hey, I think I should restructure my code and use arrays instead of the thousands of variables I am using!"). Version control is a bit like this (just that in the drawing it looks like a new copy is added on every save, which would take a lot of memory space. In reality, only the actual changes to the file are saved):

![version control](https://github.com/leoneckert/basics-of-github-with-pictures/blob/master/imgs/vc.gif)

Let's imagine our working environment as our Desktop - the files of a project we are currently working on - and a git repository (repo for short) - that is the place where the changes on the project's files are being tracked. The git repo, at any given point, is either up-to-date with our changes on the files, or behind. To bring them to the latest version, we **commit** our changes. On our computer we can have multiple different such repos for different project. I am thinking of a shelves in my computer, one for each project. When we work on a project and commit changes, we are adding new files to the corresponding shelf ;-)

![version control](https://github.com/leoneckert/basics-of-github-with-pictures/blob/master/imgs/git.gif)

So, git is a framework that we use locally, on our computer, to keep track of changes on our files on a per project basis - one project, one repo. Let's get to GitHub. GitHub is a website, a space online/remote from our own computers where we can back up our repos. When you make a GitHub account, you are given a space on their database when you can keep copies of those git shelves that are on your computer. Just like the git repo in relation to our working files, the GitHub version of the project, at any given time, is either up-to-date with the latest version of our local repo, or behind. To update it (after commiting changes to the local repo), we **push** the local repo to GitHub. 

![version control](https://github.com/leoneckert/basics-of-github-with-pictures/blob/master/imgs/github.jpg)

GitHub is great for many reasons. First of all, it makes our local git repos visual and easily explorable. Apart from that it's amazing to share code as well as being able to use code that other people share. You can also work off other people's code and make your own project out of it. Beyond that, GitHub is the place through which collaborating on code project becomes possible, as different people making changes to a project locally can push their changes to the same shared project on GitHub. GitHub is a huge place where every user has their own little library of repos and can wander around to look at other people's work. 

image here

## Make a GitHub account

That part is easy, you can follow the steps [here](https://github.com/join?source=header-home). If you are a student I recommend getting the [Student Developer Pack](https://education.github.com/pack) which gives you some benefits.

## Work on your own project

What's a project? At the very least I would say a project is a folder. Whatever is in that folder and makes up the project is relative. Since that is the case, we can turn any folder on our computer into git repos, that means we can declare "I want to track changes on files in this folder from now on.". 

image here

The things we want to do are 1) declare a folder to be a git repo 2) repeatedly commit the changes we make to files to the that local repo and back up the repo to a project on our github account. 

image here

To declare a folder to be a git repo, open your command line and navigate to the folder. Then use the follwing command:
```
git init
```

image here

... as you can see it says that a git repo has been created and seems to prove that fact by pointing to the `.git` file in that folder. Files starting with a dot are not normally visible in the Finder, you can see them when you type `ls -a` on your command line. The `git init` command added this file to the folder in which from now on changes are being tracked whenever we commit them. 

Now, after adding some lines of code to our project files and/or deleting some others, we can commit the changes to our local git repo. To do that however, we first need to make clear the changes of which files we want to commit. We do that using the `git add` command in one of the following ways
```
git add [file or folder name]
```
this will let us commit changes, but only the ones made in a specific file or files in a folder. To commit simply all changes made to any file in this project use
```
git add -A
```
Personally that is what I use most of the times, in combination with a .gitignore mechanism (explained below) that allows to list files and folders that should simply be never tracked at all.

image here (different git add scenarios)

After having selected which files to commit changes of, we can commit the changes. This always happens with a little commit message in which we explain briefly what changes were done, e.g.
```
git commit -m "🚀 added a great new function!"
```

After the commit, local repo and files are up-to-date. 

image here

#### Pushing changes to remote GitHub repo

At this point we are working on a project and commit changes to a local git repo. Let's give this project a presence online, on GitHub, too. First we need to create the project, "build a shelf", on GitHub. Click the "+" in the top right corner in you account

image here

and click "New repository". After giving it a name and clicking "Create repository", we are given information we need to connect our local repo to that project, it's this line right here:

image here

In our project, on the command line, we can declare the remote repository by entering:
```
git remote add origin https://github.com/my-username-is-username/hallo.git
```
note, `origin` here is the name we give that remote repository.

Great, from now on, to bring out GitHub repo on the latest version, we push our local repo with
```
git push origin master
```
`git push` is the command, `origin` is the name of the remote repo we want to push to, `master` is the "branch" we want to push (branches will be explained in the next workshop). 

image here

After that, we can refresh the project's page on GitHub and see our latest changes. Right now our working files, the local git repo and the remote GitHub repo are all at the same version. 

From now on we can keep working on our project and stay in that "add, commit, push" cycle to make sure our changes are tracked and synced to GitHub.

image here

#### Excercise:

Let's do this:

- create a new project folder
- initialize a local git repo and commit some changes to it
- create a project on GitHub and associate your local project with it
- keep making changes to your project while keeping both local and remote repo updated


## Use/Extend on someone else's project

On GitHub you can not just looks at other people's code and learn from it, but also download it, run it and use it in your own projects (always credit them if you build something cool (which I know you will!)!). There is two common ways do do this. I recommend to "clone" someone's repo if you just want to run it on you computer without tweaking and changing much about it and "fork" someone's repo if you are planning to extent it and build your own, crazy project on top of it. 

#### Clone a repo to run it on your computer

If you find a repo on GitHub that you want to run, find the "Clone or download" button at the top right of the repo and get the link (note, you have the options of HTTPS and ssh here. While I want to cover this in a later session (and you can feel free to ask me about it now), for today, let's always select HTTPS when we are given the option)

image here screenshot

then on our command line we navigate to a folder where we want to place the repo at and enter
```
git clone https://github.com/leoneckert/basics-of-github-with-pictures.git
```
if you now type
```
ls
```
you will see you have successfully clones someone else repo and can use it. 

Assuming whoever is the repo's owner made changes nd updates to the code, you can bring your local clone to the latest version by navigating into its project folder on the command line and entering:
```
git pull
```
...to "pull" the latest changes that the owner recently pushed. Yay!

#### Fork a repo to "make it your own"

When creating our own repo, it all started on our computer where we turned a folder into a git repo and then pushed it to GitHub. When we find someone else's project that we want to add something to, it starts on GitHub where we fork the project. You will find the "Fork" button when you look close enough! 

image here screenshot

After you clicked it, you will see that you suddenly have a copy of the project on your own account/profile! Fro there you clone it to your computer as you just learned above:
```
git clone https://github.com/my-username-is-username/basics-of-github-with-pictures.git
```
not the user in the url string is now you! Since you cloned this from your own account, you will be able to push your local changes to it as it pleases you without needing to worry about the original repo that you initially forked from! AMAZING! From here on, remember it's the same old add-push-commit oops I mean add-commit-push as always. 


## Simple collaboration

Moving on..... collaboration! But we will keep it simple for now. You know how to make a repo yourself ✅  You know how to clone someone else's repo ✅  - that means you are ready to collaborate. In a repo you own, you can define collaborators in the repo settings

image screenshot

... what adding someone here means is that that person can, after cloning the project, push changes back to it! That means two people can both push to the same repo and pull to get the latest changes.



