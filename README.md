# Basic-Git-Workflow-and-IntelliJ-Settings
A repository for git, pre-commit, and IDE settings (all open-source and/or under creative commons licences)

***

##### It will be much easier to follow below if you're familiar with git terminology (i.e.: branching, pulling, fetching, local and remote repositories). [Freshen up on git basics](https://www.atlassian.com/git).

***

## Git and GitHub Integration:
#### Option 1: [Get GitHub Desktop](https://desktop.github.com/ "GitHub Desktop Download") 
Login using your GitHub credentials as prompted. Follow prompts to checkout your remotes, manage your local repos, and stage changes using GitHub Desktop (changes will appear even when you change files using an IDE, for example). 

>If you're using an IDE and GitHub Desktop, you'll need to start a repo and then tell the IDE where to find it (see section **"IntelliJ Installation and Git Integration"** for example).

#### Option 2: [Download git](https://gist.github.com/derhuerst/1b15ff4652a867391f03)
You'll need to download git if you plan on using it from the command-line or from your IDE (some IDEs have plugins you can use over this download).

> Using git in your IDE is different from using git in GitHub Desktop; your IDE can likely generate .gitignores, has a staging area for you, can show your branches, and can even checkout pull requests for you to review. You may like to separate your IDE and the git control, so it is not necessary to have your IDE set up to do this.

***

## IntelliJ Installation and Git Integration:
#### [Grab the community (free) edition](https://www.jetbrains.com/idea/download/#section=windows "IntelliJ IDEA Download")

### Option 1: Using GitHub Desktop and IntelliJ
When first starting up the IDE, you'll be prompted to choose where your first project comes from:

#### Option 1: Open an existing project

Follow the wizard to select a local repo checked out by GitHub Desktop.

#### Option 2: Start a new project

Follow the wizard to start a new project. In GitHub Desktop, start a new repository in the same folder.

> By selecting the same local repository for both applications, IntelliJ can make changes to the project files and GitHub Desktop will track those changes.

***

TODOs:
1. Add instructions for downloading python
1. Add instructions for black formatter integration (both File Watcher Action and manual formatting) https://black.readthedocs.io/en/stable/editor_integration.html
1. Add instructions for ktlint formatter use when auto-format fails https://ktlint.github.io/
1. Add instructions for IntelliJ settings:
  * Kotlin formatting options https://github.com/pinterest/ktlint#-with-intellij-idea
  * Plugins: Save Actions, File Watchers, Google Java Formatter, Python (to avoid needing PyCharm as well) 
1. Add explanation on how pre-commits work
1. Add explanation on how to make this repos a sub-module in future repositories

***
