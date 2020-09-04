# Basic-Git-Workflow-and-IntelliJ-Settings
A repository for git, pre-commit, and IDE settings (all open-source and/or under creative commons, MIT, etc. licences)

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

#### Option 1: Open or Import an existing project

Follow the wizard to select a local repo checked out by GitHub Desktop.

#### Option 2: Start a new project

Follow the wizard to start a new project. In GitHub Desktop, start a new repository in the same folder.

> By selecting the same local repository for both applications, IntelliJ can make changes to the project files and GitHub Desktop will track those changes.

### Option 2: Using IntelliJ with integrated Git Control
When first starting up the IDE, you'll be prompted to choose where your first project comes from, pick **Get from Version Control** then:

#### Option 1: Checkout from remote repository

Follow the wizard and specify the URL for your remote repository, and specify where the local repository should be.

#### Option 2: Checkout from GitHub

You can login directly to GitHub from IntelliJ, the same way you would using GitHub Desktop. You'll need to specify where the local repository should be.

>The same options you get in GitHub Desktop are availble in IntelliJ under the `VCS` toolbar (along the lines of where you would find `File`).
If you don't want to use git in IntelliJ or want more control over git, you can also navigate to the repository on the command line and use git commands there.

***

## IntelliJ and Python Integration:

You can use IntelliJ for Python programming without also needing to download PyCharm.
1. [Download python](https://www.python.org/downloads/) (similar to section **"Git and GitHub Integration"**)
1. Get the Python Community Plugin in IntelliJ by going to `Settings (or Preferences) -> Plugins -> MarketPlace` and searching for the **Python Community plugin**. Install it.
1. IntelliJ may ask you to specify the python configuration. Give it the location of where you downloaded python (typically somewhere like `/usr/local/bin/python`).

> You should now see the option to create python files when you right-click under your project structure and select `New -> Python`

If you want to take your Python developing game further, you should consider using a formatter for your code.
1. [Install and Configure Black in IntelliJ](https://black.readthedocs.io/en/stable/editor_integration.html). (You'll need to have Python downloaded)
2. You can use Black manually by doing `Tools -> External Tools -> black`, or have the IDE do it for you when saving the file using the File Watchers plugin (described in step 1. link).

***

## IntelliJ and Kotlin/Java Integration:

TODOs:
1. Add instructions for ktlint formatter use when auto-format fails https://ktlint.github.io/
1. Add instructions for IntelliJ settings:
  * Kotlin formatting options https://github.com/pinterest/ktlint#-with-intellij-idea
  * Plugins: Save Actions, Google Java Formatter

***

## Git Pre-Commit Hooks:

***
