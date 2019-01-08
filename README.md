# CS 2400, Lab 2, Git/GitHub

## Version Control

Version control is the management of changes of projects (code) overtime. It is essential in team projects. As changes are made to a project, these changes need to be tracked.  The collection of the project and their changes overtime is called a repository (repo).

## Repository (Repo)

A repository includes a chronological record of all the changes made to a project. The repositories need to be stored on a server to be shared between team members. Services like GitHub are used to store repositories. Alternatively, an organization can set up their own servers to maintain their repositories.

## Git

What is Git?

Git is a free and open source tool (collection of commands) that is used for version control. It is the most commonly used version control system in the industry. It allows for easy management of individual and team projects. It will allow multiple people to work on the same project without worrying about their changes being overwritten (lost).

## Lab Assignment

Record your answers to each of the following excersises. Submit your answers to your TA.

1. Open a terminal window and find out what version of git is installed on our system.

    ```sh
    git --version
    ```
    Record the output of the command in your answer sheet (Q1).

2. Git includes a comprehensive help system. You can invoke command help by issuing the following command

    ```sh
    git <command> --help
    ```
    replace ```<command>``` with any git command. Try the following:

    ```sh
    git add --help
    ```

    What happens when you type ```git --help```? Recored your answer (Q2).


**Creating and maintaining a repository**

3. Create a subdirectory under your ```2400``` directory called ```git-lab```.

    ```sh
    cd 2400
    mkdir git-lab
    cd git-lab
    ```
    We will use the directory ```git-lab``` as our local repository. Issue the command:

    ```sh
    ls -a
    ```
    ```-a``` option allows you to see hidden files and directories (files and directories names that start with a period). You should see two entries ```.``` and ```..```. These are relative names for the current directory and the parent directory.

    Make your current directory ```git-lab``` a repo by issuing the following command:

    ```sh
    git init
    ```

    This will create a hidden subdirectory called ```.git```. This is the directory where all changes will be tracked for this repository. Do not modify or delete this directory or you will loose all your tracking information.

    Git has three areas: Working directory, staging area, and committed area.
    * Working directory

        Any changes you make to your files will be in this area.

    * Staging area

        Place files that are ready to be committed.

    * Committed area (commits)

        Once files are committed, they are tracked by the git system and a snapshot of your repository is created. Each snapshot is identified by a *hash* (string).

    Let's create the first file. Normally in a repo we start by creating a README.md. Open an editor and create the file, type your name and description of the lab, and save it in your ```git-lab``` directory.

    One of the common commands we use is to check the status of workflow. The command is:

    ```sh
    git status
    ```

    Type the above command inside the ```git-lab``` directory and record the output of this command as your answer to Q3.

    You now have an untracked file in your working area. Let's track the file by staging it. Issue the command:

    ```sh
    git add README.md
    ```

    Check the status of your project and record the ouput of the command as your answer to Q4.

    Did you notice the different file name colors in the two status command? You file is now ready to be committed. Issue the commit command:

    ```sh
    git commit -m "Initial commit"
    ```

    Messages in the commit command is very important. It describes what has happened since the last commit. It is specially helpful when working with teammates on the same project.

    Issue the status command again and record your output as your answer to Q5.


