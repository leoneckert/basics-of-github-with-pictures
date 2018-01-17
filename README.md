# Basics of Github (with Pictures)

This is an introduction to using git on the command line and GitHub.

* [What is git? (and what is GitHub?)](https://github.com/leoneckert/basics-of-github-with-pictures/#what-is-git-and-what-is-github)
* Make a GitHub account
* Work on your own project
* Use/Extend on someone else's project
* Simple collaboration
* How to NOT expose sensitive/personal data: .gitignore

## What is git? (and what is GitHub?)

All this has something to do with saving our work, specifically code related things we produce. Let's start by looking at the most "normal" way of saving files. Every time we save, we overwrite the old version of the file we are working on,  a bit like this:

image here

Git, and let's don't even think of GitHub yet, is a framework that we can use on our computer for a different kind of saving behaviour: version control. It means that aside from saving our file and overwriting what it was saved as before, we also save all the versions before, too. In other words, all the changes done to the file are being tracked over time. This also allows to go back to older versions of a file or to branch of in different directions to try out thing (e.g. "hey, I think I should restructure my code and use arrays instead of the thousands of variables I am using!"). Version control is a bit like this (just that in the drawing it looks like a new copy is added on every save, which would take a lot of memory space. In reality, only the actual changes to the file are saved):

image here

Let's imagine our working environment as our Desktop - the files of a project we are currently working on - and a git repository (repo for short) - that is the place where the changes on the project's files are being tracked. The git repo, at any given point, is either up-to-date with our changes on the files, or behind. To bring them to the latest version, we **commit** our changes. On our computer we can have multiple different such repos for different project. I am thinking of a shelves in my computer, one for each project. When we work on a project and commit changes, we are adding new files to the corresponding shelf ;-)

image here


