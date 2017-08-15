**Using Git to manage a project**

**Person 1**

1. Open terminal
2. Navigate to where you keep your projects, i.e.
```
$ cd Desktop
```
(cd = change directory)

3. Create a new folder for your project, for example, if you want to build a website about cats in hats...
```
$ mkdir cats_in_hats
```
(mkdir = make a new folder)

4. Navigate into this folder
```
$ cd cats_in_hats
```
5. Check where you are in your file system
```
$ pwd
```
(pwd = print working directory - check you are in the right folder!)

6. Now, initialize this folder as a new Git repository
```
$ git init
```
You should see a message stating that an empty git repository has been initialized

7. Create some files for your project - maybe start with an html file...
```
$ touch index.html
```
(touch = create a new file)

8. Check that worked - list the files inside your ``cats_in_hats`` folder
```
$ ls
```
You should see your ``index.html`` file is there

Now, we've created a new project folder, initialised it as a new Git repository, and created a file.

9. Go to your text editor (Atom or Sublime), and open up your project. Add some html code to your ``index.html`` file. Maybe a heading...
```
<h1>Cats in hats</h1>
```
10. Now, lets go back into the terminal - you should still be inside your project folder. Check your git status:
```
$ git status
```
You should see a message stating you have untracked files.
11. Lets stage our index file
```
git add index.html
```
12. Check the status again, and you should see your changes staged, ready to commit, so let's do that
```
git commit -m "Add index.html page"
```
13. Now, lets go to Github.com, and create a new repository, calling it the same as our project folder - ``cats_in_hats``
14. Once we hit create, we can follow the instructions to 'push an existing repository from the command line', so copy and paste the two lines it gives us, a bit like this:
```
$ git remote add origin https://github.com/vickymg/cats_in_hats.git
$ git push -u origin master
```
Hit enter, and when you refresh the page on Github where the instructions are, you should see your new files.

15. Finally, go to settings, and add your colleague as a collaborator

**Person 2**

1. Go to the github repository your colleague just added you to, click 'Clone or download', and copy and paste the link

2. Open your terminal, and navigate to where you would like to keep the project, for example:
```
$ cd Desktop
```
3. Lets clone the repository here, by running ``git clone``, followed by pasting the project address that you just copied, something like:
```
$ git clone https://github.com/vickymg/cats_in_hats.git
```
You can now work on this project.

5. Lets make a new git branch, so we don't mess up any of our colleague's work:
```
$ git checkout -b adding-content
```
This will switch us to a new branch to make our changes.

4. Open up your text editor, and add some more html, maybe a paragraph:
```
<p>This is a website all about cats in hats!</p>
```

5. Now, lets add and commit this change in the terminal:
```
$ git add .
$ git commit -m "Add paragraph about site"
```
(``git add .`` is a quick way to add all the files we have changed - but only use it if you're sure you really want to add all the changes you made!)

6. Lets push those changes up to Github:
```
$ git push
```
7. Got to your project on github.com. Using the branch dropdown, switch to your new branch. Clicking into the file, you can see your changes. But we want to put these on our master branch, ready to go live on the site.

8. Find where it says 'pull request', just below the 'Clone or download' button. Click, and on the next page, go ahead and 'Create pull request'

**Person 1**

1. In the project repository on Github, go to the 'Pull Requests' tab. Go into your colleague's pull quest, check that the code all looks good, and 'Merge pull request'

2. Now, your local version of the code is out of date. In terminal, inside your project folder, pull down the latest changes from Github:
```
$ git pull
```

3. You are now ready to create a new branch, and make more changes!

**Person 2**

1. Your work has been merged to the master branch on Github, yay! But you are still on your feature branch:
```
$ git branch
```

This shows which branch you are on - you are probably still on the branch ``adding-content``.

2. We're done with that branch now, as our changes were merged, so lets go back to the master branch:

```
$ git checkout master
```
3. Finally, lets pull down the most recent changes from Github, so we're up to date:
```
$ git pull
```

3. Now, your ready to make another new feature branch, and keep building!

