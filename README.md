# Git-Pre-Commit-and-IntelliJ-Settings
A repository for git, pre-commit, and IntelliJ IDE settings (sourced code is all open-source and/or under Creative Commons, MIT, Apache 2.0, and other "free" licences) with agnostic instructions for Linux, Mac, and Windows operating systems.

>   Copyright 2020 Kelly Holtzman
>
>   Licensed under the Apache License, Version 2.0 (the "License");
>   you may not use this file except in compliance with the License.
>   You may obtain a copy of the License at
>
>       http://www.apache.org/licenses/LICENSE-2.0
>
>   Unless required by applicable law or agreed to in writing, software
>   distributed under the License is distributed on an "AS IS" BASIS,
>   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
>   See the License for the specific language governing permissions and
>   limitations under the License.

***

##### It will be much easier to follow below if you're familiar with git terminology (i.e.: branching, pulling, fetching, local and remote repositories). [Freshen up on git basics](https://www.atlassian.com/git "Git Workflow and Commands").

***

## Git and GitHub Integration:
#### Option 1: [Get GitHub Desktop](https://desktop.github.com/ "GitHub Desktop Download") 
Login using your GitHub credentials as prompted. Follow prompts to checkout your remotes, manage your local repos, and stage changes using GitHub Desktop (changes will appear even when you change files using an IDE, for example). 

>If you're using an IDE and GitHub Desktop, you'll need to start a repo and then tell the IDE where to find it (see section **"IntelliJ Installation and Git Integration"** for example).

#### Option 2: [Download git](https://gist.github.com/derhuerst/1b15ff4652a867391f03 "Git Download")
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

>If you don't want to use git in IntelliJ or want more control over git, you can also navigate to the repository on the command line and use git commands there. For example, the ability to create new branches in IntelliJ isn't super straight-forward whereas new branches from the command line are as simple as: `git checkout -b <new branch name>`.

***

## IntelliJ and Python Integration:

You can use IntelliJ for Python programming without also needing to download PyCharm.
1. [Download Python](https://www.python.org/downloads/ "Python Download") (similar to section **"Git and GitHub Integration"**)
1. Get the Python Community Plugin in IntelliJ by going to `Settings (or Preferences) -> Plugins -> MarketPlace` and searching for the **Python Community plugin**. Install it.
1. IntelliJ may ask you to specify the python configuration. Give it the location of where you downloaded python (typically somewhere like `/usr/local/bin/python`).

> You should now see the option to create python files when creating a new file, and see syntax highlighting when opening a python file.

If you want to take your Python developing game further, you should consider using a formatter for your code:
1. [Install and Configure Black in IntelliJ](https://black.readthedocs.io/en/stable/editor_integration.html "Black Download and Integration Instructions"). (You'll need to have Python downloaded)
1. You can use Black manually by doing `Tools -> External Tools -> black`, or have the IDE do it for you when saving the file using the File Watchers plugin [instructions in the same link above](https://black.readthedocs.io/en/stable/editor_integration.html "Black Download and Integration Instructions").

***

## IntelliJ, Java, and Kotlin Integration:

IntelliJ is already set up to create, format, and highlight the syntax of JVM languages such as Java, Kotlin, Clojure, and Groovy. JetBrains created both IntelliJ and Kotlin - the IDE and the language work very well together.

> IntelliJ's built-in formatters may be run manually using a combination of `ctrl-alt-l` (line formatting) and `ctrl-alt-o` (optimize imports); we can also set IntelliJ to do these automatically: instructions in section **"Save Actions"**.

IntelliJ formatting alone is quite weak, so you should consider using more opinionated formatters:

#### Google-Java-Format Plugin
1. Navigate to `Settings (or Preferences) -> Plugins -> MarketPlace` and install the **Google-Java-Format plugin**.
1. Navigate to `Settings (or Preferences) -> Other Settings -> google-java-format Settings` and select **Enable google-java-format** and change the code style to **Android Open Source Project (ASOP) Style**.

#### Kotlin/Ktlint Formatting
1. Navigate to `Settings (or Preferences) -> Plugins -> MarketPlace` and install the **Kotlin** plugin, if not already installed.
1. Navigate to `Settings (or Preferences) -> Editor -> Code Style -> Kotlin` and follow the [recommended option #3 for Ktlint formatting](https://github.com/pinterest/ktlint#-with-intellij-idea).

> There is more we can do with Ktlint, see section **"Git Pre-Commit Hooks"**.

#### Save Actions
1. Navigate to `Settings (or Preferences) -> Plugins -> MarketPlace` and install the **Save Actions** plugin.
1. Navigate to `Settings (or Preferences) -> Other Settings -> Save Actions` and select the following:
* The first three check boxes under **General**
* Check the _Optimize imports_, _Reformat file_, and _Rearrange..._ check boxes under **Formatting actions**
* Check everything under **Java inspection and quick fix**. Two check boxes conflict with each other: _Add class qualifier to static member access_ and 
_Add class qualifier to static member access outside declaring class_: choose _**Add class qualifier to static member access**_.

> IntelliJ is already to save your files when you close them and every 15 seconds you're idle. The above actions will execute when when saving.

***

## Git Pre-Commit Hooks:

We can also enforce and perform formatting when commiting - these are referred to as **git hooks**. 

>Git hooks are very recommended for large projects for more than few reasons: for example it reduces differences when several people modify the same file, everyone is forced to submit code that is formatted the same, and the code is visibly similar through the entire project. _Git hooks also behave as a last line of defence when not everyone has the same IDE formatting settings, if any._

>You can tell git to what hooks to use manually and give out a bunch of instructions like the above... but there is no guarantee that anyone will use them! 

We can commit the git hooks used so that everyone on the project must use them, and we can control the versions used with a configuration file (this repository has a `.pre-commit-config.yaml` file with all the options shared above) using [Pre-Commit](https://pre-commit.com/ "Pre-Commit Git Hook(s)"):
1. To use the configuration in this repository, you'll need to **have Python downloaded** (see section **"IntelliJ and Python Integration"**)
1. Follow the [pre-commit download and installation instructions](https://pre-commit.com/ "Pre-Commit Download and Installation") using this repo's [.pre-commit-config.yaml](https://github.com/holtzmak/Git-Pre-Commit-and-IntelliJ-Settings/blob/feature/repository-settings/.pre-commit-config.yaml).

#### About Using Pre-Commit Git Hooks

Pre-commit git hooks are just that: they check your files before you commit. If there is a problem with your file, it will warn you and reformat the file if it can. **You must re-stage and re-commit your file if the pre-commit hook fails**, it will stop you from committing if there is a problem but let you commit if there are none.

#### Regarding the Ktlint Pre-Commit Git Hook

At the time of writing, the ktlint pre-commit hook does not reformat your files on it's own. 
1. There is a missing flag `-F` (for reformat) in the pre-commit hook to force it to reformat your code. **If the ktlint pre-commit hook fails, you can manually fix the problems it flags or you can do `ktlint -F <your files>` to run to formatter.**
1. There is a bug with the optimization of imports from the command line, and `ktlint -F <your files>` won't work. Your IDE can resolve import optimization on it's own: use the instructions in section **"IntelliJ, Java, and Kotlin Integration"** to do optimization.

***
