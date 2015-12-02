### SWBATs
***Students will be able to put their work on Github and deploy their site with GH Pages***
  + Initialize a local repository
  + Add and commit their work locally
  + Create a remote repository
  + link their local directory with the remote repository
  + Push their work to Github
  + Create a feature branch
  + Deploy with GH Pages

### Motivation / Why Should You Care?
Now that you’ve got your site going we’re ready to start deploying our changes and sharing it with the world. If your site doesn’t look exactly how you want it to yet, don’t worry! You can make as many changes as you want before you send out the link to share with other people. We’re just going to show you the process for getting your site set up and deploying changes.

The whole point of building websites is to share your work with the world, but in order to do that, we need to deploy them.


### Lesson Plan
####Creating a new Repo
+ We’re going to be deploying your site via GitHub but before we do that we need to initialize a git repository on your computer. 
+ Everyone go to your terminal and navigate to the root of your project. When you hit `ls` you should see your `index.html` file and `css` and `img` folders.

+ To initialize a git repository type in terminal: `git init`. You only have to do this once at the very beginning of a project. 
+ Now that git is set up you should be able to do `git status` to see the status of all your files. 
  + They should all be red because you have not staged them (prepared them) to be committed (frozen in time at this moment). Remember git is all about saving your files at a certain moment in time - a snapshot - so that if you make a bunch of changes later and you end up hating them or they break your site, you know you can go back to this moment in time when you committed your changes and your files will still be exactly the same.
+ So first we need to prepare our files to be committed. We can do them one at a time with `git add <filename>` and you might want to do this so that you can capture the changes you made to each individual file.
  + If you want to capture the complete status of your project as is you can also add all of your files at once with `git add .`. I’m going to do that for now.
+ Now type `git status` to see the status of your files - they should all be green and ready to go.
+ Now we commit them - take a snapshot of their current status - with `git commit -m “message”`. 
  + This message should be descriptive so that it can help you remember which changes are being recorded in this version of the files. For instance if you changed the style of your nav bar and you wanted to save the latest version you might commit with a message like “navbar color pink, font comic sans”
  + For the first commit I usually just write "initial commit."
+ Now do `git status` and you should see working directory clean. Now that you’ve initialized a repository I HIGHLY recommend committing your work as often as possible. 
+ Any time you finish making a change to your website that you are pleased with, even if it’s something as small as changing the font commit those changes. You never know how you are going to feel about a change the next day and being able to easily rollback to a previous version of your site with git will save you tons of time.
+ It’s also great practice if you eventually work with clients. A client might love what you’ve done one day and then hate it the next. 
+ The first step is to create a repository on Github for this project to live. A repository is just a Github word for directory or folder.  To do that, go to Github.com and look for the plus sign in the top right corner:

<img src="https://s3.amazonaws.com/after-school-assets/git-create-new-repo-arrows.png" alt="Github Plus Sign">

  * After you click on the `+`, make sure you select `New Repository`.

+ From there, you'll be directed to a form. Make sure you fill out a repository name and select the repository to remain public.

<img src="https://s3.amazonaws.com/after-school-assets/github_repo_name.png" alt="github new repository form">

+ Once you hage submitted the form on Github to create a new repository, you'll want to follow the steps in the grey box in the screen provided. Make sure you select `HTTPS` in the top!

<img src="https://s3.amazonaws.com/after-school-assets/git-new-repo-cli.png" alt="New Repo Command Line Instructions">
  *  We already did the git add and commit parts,
+ The next step is to link our local directory to the Github repository. Github had us type a lengthy command, something like:
```bash
git remote add origin https://github.com/vicfriedman/test_repo.git
```
  * This command send your code to github.com
+ Next, we enter `git push -u origin master`.
  * We only have to enter that command the very first time we push our code to Github - it helps establish the connection.
  * Go to Github and refresh the page, and you'll see your code
+ From here on out, your workflow will be:
```bash
git add file_name
git commit -m "commit message"
git push
```
+ In your terminal when you initialized your git repository with `git init` a new thing popped up on your command line (master). This is the name of the branch that you are on. Git will record the progress that you make on a simple timeline like this if you stick to one branch. 
  * BUT if you have several people making changes to a site at the same time you may want them to each have their own timelines. 
+ We can do this by creating a new branch. This is also really important when you are adding new content or features to your website. While you are working on something and styling it and updating the content you probably don’t want the world to see it. 
+ By creating a feature branch something maybe like styling-navbar you can experiment and track your progress without worrying about messing up your published site. Then when you are ready to go you can merge your changes into your master branch and deploy the changes.
  + This is a web design best practice and once you get your site to a point where it looks good and any changes you make are like icing on the cake - I HIGHLY recommend you follow this process to make changes.
+ Right now branching is important to us because we only have a master branch and Github will only publish content that is on a branch called gh-pages. We need to create this branch.
+ To do this go to your terminal and create this branch locally on your computer `git checkout -b gh-pages`.
  * The `-b` stands for branch. This command will create a new branch called gh-pages and checkout that branch, or move you onto that branch.
  + When you checkout a branch you should see the name of the branch on your command line. Any changes that you commit on this branch will not appear on any of the other branches.
  + Again this is fantastic if you are working on a new feature - like maybe a sidebar. You can create a branch called "sidebar" and experiment with different html and css and track your progress as you build the feature. If you end up hating the sidebar though you can just abandon your changes - move back to the master branch and work on something else.
+ For now the one thing we are going to do here is push up our changes from this branch up to our Github remote repository with git push. This is actually going to create a new `gh-pages` branch on github.
  * From on the gh-pages branch, enter `git push origin gh-pages`. This will create a new branch on Github called `gh-pages`
+ Everyone go to GitHub and refresh the page. You should see a new branch available in the dropdown menu of branches. If you click on settings you can scroll down and see Your site is published at http://vanessadean.github.io/traveling-van. With the url where you can see your published site.
  + Check out your published site. 
  + You are free to keep making changes to your site and you can publish them by committing your work - with add, commit and `git push origin gh-pages`.

### Conclusion / So What?
Not only is Github a powerful tool for storing your work, version control, and collaboration, it also allows you to quickly and easily deploy a static website. YOU ARE NOW PUBLISHED DEVELOPERS!!!

### Hints and Hurdles
+ Concept of branches can be really confusing. Tree analogy is helpful - Master is like the trunk of the tree and is always the stable working version. If you wanted to build a new feature, like letting a user upload a profile picture, you would create a branch. Creating the branch will photocopy all the work that's on master, and move it to the branch. When you're finished you merge that branch back in with Master
+ GH Pages is a little different, GH Pages is whatever you want deployed.
<a href='https://learn.co/lessons/hs-intro-web-design-teachers-guides-ghpages' data-visibility='hidden'>View this lesson on Learn.co</a>
