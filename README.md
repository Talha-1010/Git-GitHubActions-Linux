# Git-GitHubActions-Linux

### Here you will learn some important commands and features of Git , Github Actions and Linux that will help you in development. 

## Git

### Introduction:

Git is open-source software and distributed version control system. It helps developers easily handle different versions of a source code. With it, you can know who did what, when, and why. Nowadays, Git has become a must-have tool for any developer, and knowing Git commands is essential for developers to use Git to its full potential. There are hundreds of Git commands, but only a few significant commands are used regularly.

Here you will learn the most helpful Git commands that will take you to the next level in development:

#### #1 git init

The git init command lets us create a new Git repository. This is the first command to start a new project in a GitHub repository. Go to the directory that contains your project files and run the git init command. A hidden .git subdirectory will be added to it.

##### Usage

`$ git init`

You can also provide a repository name with the git init command.

`$ git init <your repository name>`


#### #2 git clone

git clone creates a local working copy of the source code from a remote repository. When you clone a repository, the code will be automatically downloaded to your machine.

This command will add the original location as a remote location so you can pull changes from it and push changes to it if you have permission.

##### Usage

`$ git clone <git-repo-url>`


#### #3 git branch

git branch lets us add a new branch to an existing branch, view all existing branches, and delete a branch.

##### Usage

Create a new branch locally:

`$ git branch <branch-name>`

List all the local and remote branches:

`$ git branch -a`

View all branches and see which branch you’re currently working on:

`$ git branch or $ git branch --list`

Delete a branch:

`$ git branch -d <branch-name>`

Rename a branch:

`git branch -m <branch-name> <new-branch-name>`

#### #4 git checkout

The git checkout command allows us to switch to an existing branch or create and switch to a new branch. To achieve this, the branch you want to switch to should be present in your local system and the changes in your current branch should be committed or stashed before you make the switch. You can also use this command for checking out the files.

##### Usage

Switch to an existing branch:

`git checkout <branch-name>`

Create and switch to a new branch:

`git checkout -b <new-branch-name>`


#### #5 git add

The git adds command adds your changes in a file to the staging area where you can compare your local version and the version on the remote repository.

Before you commit your new or modified file, it should be added to the staging area by using the git add command.

##### Usage

Add specific files:

`$ git add <file-name-1> <file-name-2>`

Add all new, modified, and deleted files:

`$ git add -A`

Add modified and deleted files:

`$ git add -u`


## Flow Diagram
<img width="604" alt="githubflow" src="https://user-images.githubusercontent.com/61515279/218255242-29745406-14d6-40b7-aa98-2b8f5a7754cf.PNG">


## Linux

### Introduction:

Linux is famous for its powerful commands. To use Linux effectively, all users should know how to use terminal commands. Although the OS has a GUI, many functionalities work faster when run as commands through the terminal.

This guide showcases some of the useful Linux commands all users should know.

#### #1 pwd command

The pwd command (print working directory) is a shell builtin command that prints the current location. The output shows an absolute directory path, starting with the root directory (/).

The general syntax is:
`pwd <options>`

To see how the command works, run the following in the terminal:
`pwd`

#### #2 mkdir command

The mkdir (make directory) command creates a new directory in the provided location. Use the command in the following format:

`mkdir <directory name>`

Provide a path to create a directory in the given location, or use a space or comma-separated list to create multiple directories simultaneously.

#### #3 chmod command

Use the chmod (change mode) command to change file and directory permissions. The command requires setting the permission code and the file or directory to which the permissions apply.

For example:
`chmod <permission> <file or directory>`

The permission is a number code consisting of three numbers:

- The first number is the permission of the current user (owner).
- The second number is the permission for the group.
- The third number is permissions for everyone else.

For example, to change the file permissions for a test.txt file so anyone can read, write, and execute, run:

 `chmod 777 file.txt`

#### #4 whatis command

The whatis command is a quick way to determine what a command does. Add it as a prefix to any command, for example:

`whatis cat`

The output will show a one-line description for the cat command from the documentation.


#### #5 vim command

Vim (Vi improved) is a Linux text editor that runs in the terminal. To make a new file or open an existing one in Vim, run:

`vim <filename>`

Press I to enter insert mode and enter some text. To save changes and exit Vim, press Esc, write :wq, and hit Enter.

#### #6 nano command

GNU nano (Nano's another editor) is a keyboard-oriented Linux text editor. Make a new file or open an existing one in nano with:

`nano <filename>`

The editor automatically opens, allowing you to append text or code to the file. To save and close, press CTRL+X, then Y, and confirm with Enter.


## Github Actions

### Introduction:

GitHub Actions makes it easy to automate all your software workflows, now with world-class CI/CD. Build, test, and deploy your code right from GitHub. Make code reviews, branch management, and issue triaging work the way you want.

### The components of GitHub Actions

You can configure a GitHub Actions workflow to be triggered when an event occurs in your repository, such as a pull request being opened or an issue being created. Your workflow contains one or more jobs which can run in sequential order or in parallel. Each job will run inside its own virtual machine runner, or inside a container, and has one or more steps that either run a script that you define or run an action, which is a reusable extension that can simplify your workflow.

<img width="437" alt="Components" src="https://user-images.githubusercontent.com/61515279/218275439-e6fcd99a-62f1-45f3-9edb-e43137dc6739.PNG">

#### Workflows

A workflow is a configurable automated process that will run one or more jobs.They will run when triggered by an event in your repository, or they can be triggered manually, or at a defined schedule.

Workflows are defined in the .github/workflows directory in a repository, and a repository can have multiple workflows, each of which can perform a different set of tasks. For example, you can have one workflow to build and test pull requests, another workflow to deploy your application every time a release is created, and still another workflow that adds a label every time someone opens a new issue.

#### Events

An event is a specific activity in a repository that triggers a workflow run.

#### Jobs

A job is a set of steps in a workflow that execute on the same runner. Each step is either a shell script that will be executed, or an action that will be run.

#### Actions

An action is a custom application for the GitHub Actions platform that performs a complex but frequently repeated task. Use an action to help reduce the amount of repetitive code that you write in your workflow files. An action can pull your git repository from GitHub, set up the correct toolchain for your build environment, or set up the authentication to your cloud provider.

You can write your own actions, or you can find actions to use in your workflows in the GitHub Marketplace.

#### Runners

A runner is a ***server*** that runs your workflows when they're triggered. Each runner can run a single job at a time. GitHub provides Ubuntu Linux, Microsoft Windows, and macOS runners to run your workflows; each workflow run executes in a fresh, newly-provisioned virtual machine. GitHub also offers larger runners, which are available in larger configurations.


### Create an example workflow

In this workflow, GitHub Actions checks out the pushed code, installs the bats testing framework, and runs a basic command to output the bats version: `bats -v`

1. In your repository, create the .github/workflows/ directory to store your workflow files.

2. In the `.github/workflows/` directory, create a new file called `learn-github-actions.yml` and add the following code.

```
name: learn-github-actions
run-name: ${{ github.actor }} is learning GitHub Actions
on: [push]
jobs:
  check-bats-version:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
        with:
          node-version: '14'
      - run: npm install -g bats
      - run: bats -v
```

3. Commit these changes and push them to your GitHub repository.

Your new GitHub Actions workflow file is now installed in your repository and will run automatically each time someone pushes a change to the repository.



### Understanding the workflow file
Here you will learn the most helpful Git commands that will take you to the next level in development:

#### #1 name:workflow-name

#### Usage

`name: learn-github-actions`

The name of the workflow as it will appear in the "Actions" tab of the GitHub repository.

#### #2 on:event-name

#### Usage

`on: [push]`

Specifies the trigger for this workflow. This example uses the push event, so a workflow run is triggered every time someone pushes a change to the repository or merges a pull request.


#### #3 jobs:

Groups together all the jobs that run in the learn-github-actions workflow.


##### #4 check-bats-version:

Defines a job named check-bats-version. The child keys will define properties of the job.

##### #5 runs-on: operating-system

##### Usage

`runs-on: ubuntu-latest`

Configures the job to run on the latest version of an Ubuntu Linux runner. This means that the job will execute on a fresh virtual machine hosted by GitHub.


##### #6 steps:

Groups together all the steps that run in the check-bats-version job. Each item nested under this section is a separate action or shell script.

##### #7 run: command

#### Usage
`- run: npm install -g bats`

The run keyword tells the job to execute a command on the runner. In this case, you are using npm to install the bats software testing package.




















