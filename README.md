# CS 2400, Lab 2, Git/GitHub
### Prepared by: Nasseef Abukamail (abukamai@ohio.edu)

## Version Control

Version control is the management of changes of projects (code) overtime. It is essential in team projects. As changes are made to a project, these changes need to be tracked.  The collection of the project and their changes overtime is called a repository (repo).

## Repository (Repo)

A repository includes a chronological record of all the changes made to a project. The repositories need to be stored on a server to be shared between team members. Services like GitHub are used to store repositories. Alternatively, an organization can set up their own servers to maintain their repositories.

## Git

Git is a free and open source tool (collection of commands) that is used for version control. It is the most commonly used version control system in the industry. It allows for easy management of individual and team projects. It will allow multiple people to work on the same project without worrying about their changes being overwritten (lost).

## Lab Assignment
---

   ### Record your answers, where indicated, in a file called ```answers.md```.

1. Create the project directory. Open a terminal window and issue the commands:

    ```
    cd ~/2400
    mkdir git-lab
    cd git-lab
    ```

2. Create two empty (Markdown files) ```README.md``` and ```answers.md```. Markdown is similar to html but much simpler. Search online for a quick reference. Record all your answers for this lab in ```answers.md``.

    ```sh
    touch README.md
    touch answers.md
    ```


3. In a terminal window find out what version of git is installed on the system.

    ```sh
    git --version
    ```
    Record the output of the command as **Answer 1**.

4. Git needs to know your information (name and email). Issue the commands:

    ```sh
    git config --global user.name "Your name"
    git config --global user.email "Your email"
    ```
    You can verify the changes by issuing the command:

    ```sh
    git config --list
    ```

    Record the output of this command as **Answer 2**.

5. Git includes a comprehensive help system. You can invoke help by issuing the following command

    ```
    git <command> --help
    ```
    replace ```<command>``` with any git command. Try the following:

    ```
    git add --help
    ```

    What happens when you type ```git --help```? Record your answer as **Answer 3**.

---
**Creating and maintaining a repository**

---

4. In a terminal window go to the ```git-lab``` directory.

    ```
    cd ~/2400/git-lab
    ```
    We will use the directory ```git-lab``` as our local repository. Issue the command:

    ```
    ls -a
    ```
    ```-a``` option allows you to see hidden files and directories (files and directories names that start with a period). In addition to the two files you created in step 2, you should see two hidden entries ```.``` and ```..```. These are relative names for the current directory and the parent directory.

    **Make ```git-lab``` a repo by issuing the following command:**

    ```sh
    git init
    ```

    This will create a hidden subdirectory called ```.git```. This is the directory where all changes will be tracked for this repository. Do not modify or delete this directory or you will loose all your tracking information.

    **Workflow**

    Locally, Git has three areas: ```Working``` directory, ```staging``` area, and ```committed``` area.
    * **Working directory**

        Any changes you make to your files (including adding new files) will be in this area. Newly created files will be considered ```untracked```.

    * **Staging area**

        Files will be ```tracked``` and changes will be ready to be committed.

    * **Committed area (commits)**

        Once files are committed, they are tracked by the git system and a snapshot of your repository is created. Each snapshot is identified by a *hash* string.

    Let's modify the first file. Normally in a repo we start by creating a README.md file (created in step 2). Edit the README.md file and type your full name and save it.

    One of the common commands we use is to check the status of our repo. The command is:

    ```sh
    git status
    ```

    Type the above command inside the ```git-lab``` directory and record the output of this command as **Answer 4**.

    You now have an untracked file in your working area. Let's track the file by staging it. Issue the command:

    ```sh
    git add README.md
    ```

    Check the status of your project and record the output of the command as your answer to **Answer 5**.

    Did you notice the different file name colors in the two status command? Add the second file ```answers.md`` to the staging area.

    Check the status again and record your output as **Answer 6**.

    You files are now ready to be committed. Issue the commit command:

    ```sh
    git commit -m "Initial commit"
    ```

    Messages in the commit command is very important. It describes what has happened since the last commit. It is specially helpful when working with teammates on the same project.

    Issue the status command again and record your output as **Answer 7**.

    The above workflow outlines the steps that you usually take to create a commit (snapshot) of your repository at any given time.

5. View the repository history (commits). Issue the ```log``` command.

    ```sh
    git log
    ```

    The output should include your commits' information including:
    * Hash value (```0c6112a...```).
    * ```HEAD->master```: a pointer to a repository called ```master```. ```master``` is your main repository ```branch``` name. More on branching later.
    * Author, email, date, and comment made while committing.

    Record the output of the ```git log``` as **Answer 8**.

---
**Working with remote repositories on GitHub**

---

6. Open a browser window and go to GitHub (```https://github.com```), login if necessary.

    * Create a new *public* repository (click the + symbol on the top right).
    * Name your repository ```git-lab```
    * Do not select anything else.
    * Click on ```Create repository``` button.
    * Now you have an empty repository called ```git-lab```. You should see two instructions on how to ```push an existing repository from the command line```. These are the commands you need to push your local repository to GitHub.
    * Let's try the commands:

      ```sh
      git remote add origin git@github.com:<user-name>/git-lab.git
      git push -u origin master

      or

      git remote add origin https://github.com/<user-name>/git-lab.git
      git push -u origin master
      ```

    Watch the output to make sure you did not get any errors. Your repo should be updated on GitHub. Refresh your browser to see your ```README.md``` and ```answers.md`` files on GitHub.

    Check the status of your repository. Record the output as **Answer 9**.


7. Update README.md locally. Add your email address and a message informing your TA where you recorded your answers. At the terminal ```push``` your changes to GitHub.

    **Hint:** see workflow above.


8. Update README.md on GitHub by clicking on README.md and then clicking on the edit button. Add your class information. For example, ```CS 2400, Section 107```. At the bottom add a commit message and commit your changes.

9. Open a terminal window and look at README.md in your local directory. Were the changes you made online reflected in your local copy? Record your answer as **Answer 10**.

10. Try the push command again ```git push``. What happens? Record your answer as **Answer 11**.

10. Open the terminal window and ```pull``` your remote changes to your local repository. Issue the command:

    ```sh
    git pull
    ```

Look at README.md in your local directory. Were the changes you made online reflected in your local copy? Record your answer to **Answer 12**.

----

<div align="center">
 D O N E
</div>

----
