- 👋 Hi, I’m @GIO
- 👀 I’m interested in learning how to code to create a website/
- 🌱 I’m currently learning how to use Github for my class :)
- 💞️ I’m looking to collaborate on professional growth.
- 📫 How to reach me. You can reach me via personal email - mgio0133@gmail.com
- 😄 Pronouns: He/Him
- ⚡ Fun fact: I am competing in this year's state Boxing Golden Gloves!

<!---
Gm31518821/Gm31518821 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->















How to use Git:

1.) Create a "repository" (project) with a git hosting tool (like Bitbucket)

2.) Copy (or clone) the repository to your local machine

3.) Add a file to your local repo and "commit" (save) the changes

4.) "Push" your changes to your main branch

5.) Make a change to your file with a git hosting tool and commit

6.)"Pull" the changes to your local machine

7.)Create a "branch" (version), make a change, commit the change

8.)Open a "pull request" (propose changes to the main branch)

9.)"Merge" your branch to the main branch


























How to use Github:
Step 1: Create a local git repository 

To begin, open up a terminal and move to where you want to place the project on your local machine using the cd (change directory) command. For example, if you have a 'projects' folder on your desktop, you'd do something like:

mnelson:Desktop mnelson$ cd ~/Desktop
mnelson:Desktop mnelson$ mkdir myproject
mnelson:Desktop mnelson$ cd myproject/
To initialize a git repository in the root of the folder, run the git init command: 

mnelson:myproject mnelson$ git init
Initialized empty Git repository in /Users/mnelson/Desktop/myproject/.git/

Step 2: Add a new file to the repo
Go ahead and add a new file to the project, using any text editor you like or running a touch command.
`touch newfile.txt` just creates and saves a blank file named newfile.txt. 

Once you've added or modified files in a folder containing a git repo, git will notice that  the file exists inside the repo. But, git won't track the file unless you explicitly tell it to. Git only saves/manages changes to files that it tracks, so we’ll need to send a command to confirm that yes, we want git to track our new file.

mnelson:myproject mnelson$ touch mnelson.txt
mnelson:myproject mnelson$ ls
mnelson.txt

After creating the new file, you can use the git status command to see which files git knows exist.

mnelson:myproject mnelson$ git status
On branch master

Initial commit

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	mnelson.txt

nothing added to commit but untracked files present (use "git add" to track)

What this basically says is, "Hey, we noticed you created a new file called mnelson.txt, but unless you use the 'git add' command we aren't going to do anything with it."

An interlude: The staging environment, the commit, and you
One of the most confusing parts when you're first learning git is the concept of the staging environment and how it relates to a commit.

A commit is a record of what changes you have made since the last time you made a commit. Essentially, you make changes to your repo (for example, adding a file or modifying one) and then tell git to put those changes into a commit.

Commits make up the essence of your project and allow you to jump to the state of a project at any other commit.

So, how do you tell git which files to put into a commit? This is where the staging environment or index come in. As seen in Step 2, when you make changes to your repo, git notices that a file has changed but won't do anything with it (like adding it in a commit).

To add a file to a commit, you first need to add it to the staging environment. To do this, you can use the git add <filename> command (see Step 3 below).

Once you've used the git add command to add all the files you want to the staging environment, you can then tell git to package them into a commit using the git commit command. 

Note: The staging environment, also called 'staging', is the new preferred term for this, but you can also see it referred to as the 'index'.

Step 3: Add a file to the staging environment
Add a file to the staging environment using the git add command. 

If you rerun the git status command, you'll see that git has added the file to the staging environment (notice the "Changes to be committed" line). 


mnelson:myproject mnelson$ git status
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

	new file:   mnelson.txt
To reiterate, the file has not yet been added to a commit, but it's about to be.

Step 4: Create a commit
It's time to create your first commit!

Run the command git commit -m "Your message about the commit"

mnelson:myproject mnelson$ git commit -m "This is my first commit!"
[master (root-commit) b345d9a] This is my first commit!
 1 file changed, 1 insertion(+)
 create mode 100644 mnelson.txt
The message at the end of the commit should be something related to what the commit contains - maybe it's a new feature, maybe it's a bug fix, maybe it's just fixing a typo. Don't put a message like "asdfadsf" or "foobar". That makes the other people who see your commit sad. Very, very, sad. Commits live forever in a repository (technically you can delete them if you really, really need to but it’s messy), so if you leave a clear explanation of your changes it can be extremely helpful for future programmers (perhaps future you!) who are trying to figure out why some change was made years later.

Step 5: Create a new branch
Now that you've made a new commit, let's try something a little more advanced.

Say you want to make a new feature but are worried about making changes to the main project while developing the feature. This is where git branches come in. 

Branches allow you to move back and forth between 'states' of a project. Official git docs describe branches this way: ‘A branch in Git is simply a lightweight movable pointer to one of these commits.’ For instance, if you want to add a new page to your website you can create a new branch just for that page without affecting the main part of the project. Once you're done with the page, you can merge your changes from your branch into the primary branch. When you create a new branch, Git keeps track of which commit your branch 'branched' off of, so it knows the history behind all the files. 

Let's say you are on the primary branch and want to create a new branch to develop your web page. Here's what you'll do: Run git checkout -b <my branch name>. This command will automatically create a new branch and then 'check you out' on it, meaning git will move you to that branch, off of the primary branch.

After running the above command, you can use the git branch command to confirm that your branch was created:

mnelson:myproject mnelson$ git branch
  master
* my-new-branch
The branch name with the asterisk next to it indicates which branch you're on at that given time. 

A note on branch names
By default, every git repository’s first branch is named `master` (and is typically used as the primary branch in the project). As part of the tech industry’s general anti-racism work, some groups have begun to use alternate names for the default branch (we are using “primary” in this tutorial, for example). In other documentation and discussions, you may see “master”, or other terms, used to refer to the primary branch. Regardless of the name, just keep in mind that nearly every repository has a primary branch that can be thought of as the official version of the repository. If it’s a website, then the primary branch is the version that users see. If it’s an application, then the primary branch is the version that users download. This isn’t technically necessary (git doesn’t treat any branches differently from other branches), but it’s how git is traditionally used in a project.

If you are curious about the decision to use different default branch names, GitHub has an explanation of their change here: https://github.com/github/renaming

Now, if you switch back to the primary branch and make some more commits, your new branch won't see any of those changes until you merge those changes onto your new branch.

Step 6: Create a new repository on GitHub
If you only want to keep track of your code locally, you don't need to use GitHub. But if you want to work with a team, you can use GitHub to collaboratively modify the project's code.

To create a new repo on GitHub, log in and go to the GitHub home page. You can find the “New repository” option under the “+” sign next to your profile picture, in the top right corner of the navbar:

Git_1

After clicking the button, GitHub will ask you to name your repo and provide a brief description:

Git_2

When you're done filling out the information, press the 'Create repository' button to make your new repo.

GitHub will ask if you want to create a new repo from scratch or if you want to add a repo you have created locally. In this case, since we've already created a new repo locally, we want to push that onto GitHub so follow the '....or push an existing repository from the command line' section: 

mnelson:myproject mnelson$ git remote add origin https://github.com/cubeton/mynewrepository.git
mnelson:myproject mnelson$ git push -u origin master
Counting objects: 3, done.
Writing objects: 100% (3/3), 263 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/cubeton/mynewrepository.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.
(You'll want to change the URL in the first command line to what GitHub lists in this section since your GitHub username and repo name are different.)

Step 7: Push a branch to GitHub
Now we'll push the commit in your branch to your new GitHub repo. This allows other people to see the changes you've made. If they're approved by the repository's owner, the changes can then be merged into the primary branch.

To push changes onto a new branch on GitHub, you'll want to run git push origin yourbranchname. GitHub will automatically create the branch for you on the remote repository:

mnelson:myproject mnelson$ git push origin my-new-branch
Counting objects: 3, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 313 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/cubeton/mynewrepository.git
 * [new branch]      my-new-branch -> my-new-branch

You might be wondering what that "origin" word means in the command above. What happens is that when you clone a remote repository to your local machine, git creates an alias for you. In nearly all cases this alias is called "origin." It's essentially shorthand for the remote repository's URL. So, to push your changes to the remote repository, you could've used either the command: git push git@github.com:git/git.git yourbranchname or git push origin yourbranchname

(If this is your first time using GitHub locally, it might prompt you to log in with your GitHub username and password.)

If you refresh the GitHub page, you'll see note saying a branch with your name has just been pushed into the repository. You can also click the 'branches' link to see your branch listed there.

Git_3

Now click the green button in the screenshot above. We're going to make a pull request!

Step 8: Create a pull request (PR)
A pull request (or PR) is a way to alert a repo's owners that you want to make some changes to their code. It allows them to review the code and make sure it looks good before putting your changes on the primary branch.

This is what the PR page looks like before you've submitted it:

Git_4

And this is what it looks like once you've submitted the PR request:

Git_5

You might see a big green button at the bottom that says 'Merge pull request'. Clicking this means you'll merge your changes into the primary branch..

Sometimes you'll be a co-owner or the sole owner of a repo, in which case you may not need to create a PR to merge your changes. However, it's still a good idea to make one so you can keep a more complete history of your updates and to make sure you always create a new branch when making changes.

Step 9: Merge a PR
Go ahead and click the green 'Merge pull request' button. This will merge your changes into the primary branch.

Git_6

When you're done, I recommend deleting your branch (too many branches can become messy), so hit that grey 'Delete branch' button as well.

You can double check that your commits were merged by clicking on the 'Commits' link on the first page of your new repo.

Git_7

This will show you a list of all the commits in that branch. You can see the one I just merged right up top (Merge pull request #1).

Git_8

You can also see the hash code of the commit on the right hand side. A hash code is a unique identifier for that specific commit. It's useful for referring to specific commits and when undoing changes (use the git revert <hash code number> command to backtrack).

Step 10: Get changes on GitHub back to your computer
Right now, the repo on GitHub looks a little different than what you have on your local machine. For example, the commit you made in your branch and merged into the primary branch doesn't exist in the primary branch on your local machine.

In order to get the most recent changes that you or others have merged on GitHub, use the git pull origin master command (when working on the primary branch). In most cases, this can be shortened to “git pull”.

mnelson:myproject mnelson$ git pull origin master
remote: Counting objects: 1, done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), done.
From https://github.com/cubeton/mynewrepository
 * branch            master     -> FETCH_HEAD
   b345d9a..5381b7c  master     -> origin/master
Merge made by the 'recursive' strategy.
 mnelson.txt | 1 +
 1 file changed, 1 insertion(+)
This shows you all the files that have changed and how they've changed.

Now we can use the git log command again to see all new commits.

(You may need to switch branches back to the primary branch. You can do that using the git checkout master command.)

mnelson:myproject mnelson$ git log
commit 3e270876db0e5ffd3e9bfc5edede89b64b83812c
Merge: 4f1cb17 5381b7c
Author: Meghan Nelson <mnelson@hubspot.com>
Date:   Fri Sep 11 17:48:11 2015 -0400

    Merge branch 'master' of https://github.com/cubeton/mynewrepository

commit 4f1cb1798b6e6890da797f98383e6337df577c2a
Author: Meghan Nelson <mnelson@hubspot.com>
Date:   Fri Sep 11 17:48:00 2015 -0400

    added a new file

commit 5381b7c53212ca92151c743b4ed7dde07d9be3ce
Merge: b345d9a 1e8dc08
Author: Meghan Nelson <meghan@meghan.net>
Date:   Fri Sep 11 17:43:22 2015 -0400

    Merge pull request #2 from cubeton/my-newbranch
    
    Added some more text to my file

commit 1e8dc0830b4db8c93efd80479ea886264768520c
Author: Meghan Nelson <mnelson@hubspot.com>
Date:   Fri Sep 11 17:06:05 2015 -0400

    Added some more text to my file

commit b345d9a25353037afdeaa9fcaf9f330effd157f1
Author: Meghan Nelson <mnelson@hubspot.com>
Date:   Thu Sep 10 17:42:15 2015 -0400

    This is my first commit!
Step 11: Bask in your git glory


























How to use Webstorm:
Open, check out, or create a project﻿
A project in WebStorm is a folder with the source code you edit, the libraries and tools you use (for example, in the node_modules subfolder), and various app configuration files (for example, package.json or .eslintrc).

Once you have opened a folder in WebStorm, the .idea subfolder is added to it where WebStorm stores its internal configuration settings, for example, for the project code style or the version control system.

You can open, check out, and create projects from the WebStorm Welcome screen.

Open, check out, and create projects from the Welcome screen
To open a project﻿
On the Welcome Screen, click Open and then select the folder with your application in the dialog that opens.

To check out a project from a version control system﻿
Click Get from VCS on the Welcome screen.

Alternatively, select File | New | Project from Version Control or Git | Clone… or VCS | Get from Version Control from the main menu.

Instead of Git in the main menu, you may see any other Version Control System that is associated with your project. For example, Mercurial or Perforce.

In the dialog that opens, select your version control system from the list and specify the repository to check out the application sources from. For more information, refer to Check out a project (clone).

To create an empty WebStorm project﻿
Click Create New Project on the Welcome screen or select File | New | Project from the main menu. The New Project dialog opens.

In the left-hand pane, choose Empty Project. In the right-hand pane, specify the application folder and click Create.

You can also generate a project from a template. For more information, refer to Generating framework-specific projects.

To create a new file in a project﻿
In the Project tool window, select the folder where you want to create a new file and press AltInsert.

Alternatively, choose New from the context menu of the selection and then choose the file type from the list:


Complete your code﻿
WebStorm automatically completes keywords, symbols from standard language API's and from the project dependencies. Press CtrlSpace to get the code completion options for the current context, the icon next to each suggested member indicates its type:

Code completion
To have more variants shown, press CtrlSpace once again.

By default, completion suggestions in JavaScript and TypeScript files are sorted by their relevance based on machine-learning algorithms. To turn off this sorting, open the Settings dialog (CtrlAlt 0S), go to Editor | General | Code Completion, and clear the Sort completion suggestions based on machine learning checkbox. Learn more from Sort suggestions based on Machine Learning.

Inspect and fix your code on the fly﻿
WebStorm monitors your code and tries to keep it accurate and clean. It detects potential errors and problems and suggests quick-fixes for them. Every time WebStorm finds unused code, an endless loop, a missing import statement for a symbol, and many other things that probably require your attention, you’ll see a highlight and a light bulb. Click this bulb or press AltEnter to apply a fix.

Run and debug your application﻿
In WebStorm, the entry point to running or debugging an application is a run/debug configuration. WebStorm comes with a number of predefined run/debug configuration templates for different types of applications and files. The information you need to provide in a configuration depends on its type, it can be a file to run or a test. Some configurations can attach to already running applications, in this case you need to specify the URL and port to attach to.

To run your application﻿
Create a run configuration of the type that fits your app and click Run.















Sources: 
https://www.atlassian.com/git
https://www.jetbrains.com/help/webstorm/getting-started-with-webstorm.html#ws_getting_started_customize_your_environment_keymap
https://github.com/Gm31518821/Glossary/settings
