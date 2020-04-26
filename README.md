## CS 2400, Homework 1, Git/GitHub

### 20 Points

### Prepared by: Nasseef Abukamail (abukamai@ohio.edu)

---
### It is important that you follow the instructions in the order given.

## Version Control

Version control is the management of changes of projects (code) overtime. It is essential in team projects. As changes are made to a project, these changes need to be tracked.  The collection of the project and their changes overtime is called a repository (repo).

## Repository (Repo)

A repository includes a chronological record of all the changes made to a project. The repositories need to be stored on a server to be shared between team members. Services like GitHub are used to store repositories. Alternatively, an organization can set up their own servers to maintain their repositories.

## Git

Git is a free and open source tool (collection of commands) that is used for version control. It is the most commonly used version control system in the industry. It allows for easy management of individual and team projects. It will allow multiple people to work on the same project without worrying about their changes being overwritten (lost).

---

## Homework Assignment

---

### Record your answers, where indicated, in a file called `answers.md`. Each answer is worth 5 points.

1. Create a directory (folder) called `cs2400` on your `Desktop`. From this point on, you will place all your homework and lab assignments in this directory.

2. Create the project directory. Open a terminal window
   - In Windows, open `Powershell`
   - In Mac and Linux open `Terminal`
3. You can navigate directly to `cs2400` directory by issueing the following command:
   ```console
   cd ~/Desktop/cs2400
   ```
    > ~ represents your user (home) directory

4. Issue the commands:

    ```console
    cd ~/Desktop/cs2400
    mkdir git-lab
    cd git-lab
    ```

5. Create two empty files (Markdown files) `README.md` and `answers.md` using your favorite editor and save them inside the `git-lab` directory. Markdown is similar to html but much simpler. Search online for a quick reference. Record all your answers for this lab in `answers.md`.
6. From this point on, you can edit these files using `VS Code`. In `VS Code`. Under the `File` menu, choose `Open Folder` and select `git-lab` folder. 


7. In a terminal window find out what version of git is installed on the system. You can start a terminal window from within `VS Code` by clicking on `Terminal` menu and selecting `New Terminal`.

    ```console
    git --version
    ```
    Record the output of the command as **`Answer 1`**.

8. Git needs to know your information (name and email). Issue the commands:

    ```console
    git config --global user.name "Your name"
    git config --global user.email "Your email"
    ```
    You can verify the changes by issuing the command:

    ```console
    git config --list
    ```

    Record the output of this command as **`Answer 2`**.

9. Git includes a comprehensive help system. You can invoke help by issuing the following command

    ```console
    git <command> --help
    ```
    replace `<command>` with any git command. Try the following:

    ```console
    git add --help
    ```

    What happens when you type `git --help`? Record your answer as **`Answer 3`**.

---
**Creating and maintaining a repository**

---

6. In a terminal window use the `cd` command to go to the `git-lab` directory.

    We will use the directory `git-lab` as our local repository. Issue the command `ls` or `ls -a`.

    In Mac and Linux systems, `-a` option allows you to see hidden files and directories (files and directories names that start with a period). In addition to the two files you created in step 2, you should see two hidden entries `.` and `..`. These are relative names for the current directory and the parent directory.

    **Make `git-lab` a repo by issuing the following command:**

    ```console
    git init
    ```

    This will create a hidden subdirectory called `.git`. This is the directory where all changes will be tracked for this repository. Do not modify or delete this directory or you will loose all your tracking information.

    **Workflow**

    Locally, Git has three areas: `Working` directory (also called `Index`), `Staging` area, and `Repository commit area` area.
    * **Working directory (tree)**

        Any changes you make to your files (including adding new files) will be in this area. Newly created files will be considered `untracked`.

    * **Staging area (index)**

        Files will be `tracked` and changes will be ready to be committed.

    * **Repository Commit area (History)**

        Once files are committed, they become part of the repository history. They are tracked by the git system and a snapshot of your repository is created. Each snapshot is identified by a *hash* string.

    Let's modify the first file. Normally in a repo we start by creating a `README.md` file (created in step 2). Edit the `README.md` file and type your **full name** and your **GitHub user name** and save it.

    One of the common commands we use is to check the status of our repo is the `git status` command.

    Type the status command inside the `git-lab` directory and record the output of this command as **`Answer 4`**.

    You now have an untracked file in your working area. Let's track the file by staging it. Issue the command:

    ```console
    git add README.md
    ```

    Check the status of your project and record the output of the command as your answer to **`Answer 5`**.

    Did you notice the different file name colors in the two status command? Add the second file `answers.md` to the staging area.

    Check the status again and record your output as **`Answer 6`**.

    Your files are now ready to be committed. Issue the commit command:

    ```console
    git commit -m "Initial commit"
    ```

    Messages in the commit command is very important. It describes what has happened since the last commit. It is specially helpful when working with teammates on the same project.

    Issue the status command again and record your output as **`Answer 7`**.

    The above workflow outlines the steps that you usually take to create a commit (snapshot) of your repository at any given time.

7. View the repository history (commits). Issue the `log` command.

    ```console
    git log
    ```

    The output should include your commits' information including:
    * Hash value (`0c6112a...`).
    * `HEAD->master`: a pointer to a repository called `master`. `master` is your main repository `branch` name. More on branching later.
    * Author, email, date, and comment made while committing.

    Record the output of the `git log` as **`Answer 8`**.

---
**Working with remote repositories on GitHub**

---

8. Open a browser window and go to GitHub (`https://github.com`), login if necessary.

    * Create a new *public* repository (click the + symbol on the top right).
    * Name your repository `git-lab`
    * Do not select anything else.
    * Click on `Create repository` button.
    * Now you have an empty repository called `git-lab`. You should see two instructions on how to `push an existing repository from the command line`. These are the commands you need to push your local repository to GitHub.
    * Let's try the commands:


      ```console
      git remote add origin https://github.com/<user-name>/git-lab.git
      git push -u origin master
      ```

      or

      ```console
      git remote add origin git@github.com:<user-name>/git-lab.git
      git push -u origin master
      ```

    Watch the output to make sure you did not get any errors. Your repo should be updated on GitHub. Refresh your browser to see your `README.md` and `answers.md` files on GitHub.

    Check the status of your repository. Record the output as **`Answer 9`**.


9. Update `README.md` locally. Add your email address and a message informing your TA where you recorded your answers. At the terminal, add `README.md`, `commit` the changes, and  `push` your changes to GitHub.

    ```console
    git add README.md
    git commit -m "Enter a message here"
    git push
    ```
    > You may have to enter your GitHub credentials here.

10. Open your browser and go to GitHub. Update `README.md` on GitHub by clicking on `README.md` and then clicking on the edit button. Add your class information. For example, `CS 2400, Section 107`. At the bottom add a commit message and commit your changes.

11. Open a terminal window and look at `README.md` in your local directory. Were the changes you made online reflected in your local copy? Record your answer as **`Answer 10`**.

12. Try the push command again `git push`. What happens? Record your answer as **`Answer 11`**.

13. Open the terminal window and `pull` your remote changes to your local repository. This is what you would normally do when the online version of your repo changes while you're working on your local one. Issue the command:

    ```console
    git pull
    ```

Look at `README.md` in your local directory. Were the changes you made online reflected in your local copy? Record your answer to **`Answer 12`**.

---
**Cloning a Repository**

---
The `git clone` command downloads an existing repository to your local machine. This is something you will do often. You will be asked to clone a repository, work on it, and push your changes online. Let's try it.

14. Go online to GitHub

    * Create a new repository
      * Name your repository `git-lab-2`
      * Select `Public`
      * Check `Initialize this repository with a README`
      * click on `Add .gitignore: None` button and select `C++`
      * Click `Create repository` button

    * click on the clone button and copy the link
    * Open a terminal window and go to your 2400 directory and clone the repository. You will normally do this for most homework projects. Go to your CS 2400 folder on your system (Desktop if you don't have one)
        ```console
        git clone <link you copied above>
        ```
    * This should download the repository directory to you machine. The directory should be called `git-lab-2`.
    * Use the `cd` to go to the new repo's directory and issue the `ls -a` command. Record the output as **`Answer 13`**.
    * The file `.gitignore` has a list of files that `git` will ignore when pushing the repo. For example, it ignores executable files.

15. (35 points) Lets create a C++ program inside `git-lab-2` directory and update the online master branch.

    * In your editor, create the file `git-lab-program.cc`.
    * Copy the following code into it

        ```cpp
        /*
         *        File: git-lab-program.cc
         *      Author: <Enter your name>
         *        Date: <Enter today's date>
         * Description: Add Description
         */

        #include <iostream>
        #include <iomanip>
        #include <cstdlib>
        using namespace std;


        int main(int argc, char const *argv[]) {

            /*add code*/
            return 0;
        }// main
        ```

        * Add your name and today's date in the comments
        * Add the line `cout << "Hello Git!!" << endl;` in the main function
        * Save your program
        * Compile and run the program using the commands:

        ```console
        g++ -Wall git-lab-program.cc
        ./a.out
        ```

    * Did you get the right output? If not, fix your program and try again
    * Add, commit, and push your changes to GitHub (See Workflow above)
    * Go to your repository on GitHub
    * Are the changes you made reflected online? If not, try again or ask your TA.
* **Last Steps:**

    * Use the `cd` command to go to the `git-lab` directory
    * Edit the file `README.md` and write the word `Done` in the file
    * Make sure the files `README.md` and `answers.md` are saved
    * Add `README.md` to the staging area
    * Add `answers.md` to the staging area
     * Push your changes to GitHub
    * Go to your repository on GitHub and tag me `@nasseef` in the comment section of the commit.
      * Click on `commits`
      * Click on the last commit (top one)
      * Scroll down to the comment section and tag me by entering `@nasseef, I'm done`
      * Click on the button: `Comment on this commit`


    **I encourage you to learn more about Git. It is an essential tool for every computer science professional.**
---

<div align="center">
 D O N E
</div>

---
