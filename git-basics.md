### Cloning a repository

Go to github or gitlab and find the repository you want to clone to your local file system:

https://github.com/neoito-hub/learningHub

Locate the https link from the home page of the repository, and copy down the url

It will be something like below `https://github.com/neoito-hub/learningHub.git`

```
$ git clone https://github.com/neoito-hub/learningHub.git
```

This makes a `learningHub` directory in the current directory.
You can also find a hidden folder name `.git` inside the `learningHub` directory.

If you ever want to remove git functionality inside your project then that is the folder you need to remove.

### Adding files

To add a file, just create the file and notify `git`, using the below command

```
$ git add notify.txt
```

Or in some cases you may need to add all the files inside a git enabled folder.

```
$ git add .
```

To commit the "change" (the addition of a file, modification of a file) to the repository, we `commit` those changes:

```
$ git commit -m 'this is a commit mesage'
```

The `-m` means message. From `git help commit`:

It's always advisable to give real meaningul commit messages, after all it can help you later.

Please not that for all the Create, Update, Delete operation on files, you need to commit them before it is sent to the repo

### Push your changes to github

We have been working on a local copy of the repository stored at github or gitlab. To send our changes to the origin from the local machine, we use `push`:

```
$ git push origin main
```

The `origin` refers to github in our case and `main` is the name of the branch in which we are working.

### Pulling changes from github

If you move to a new computer, or your local copy gets wiped out for some reason, you need to pull from github any changes pushed to it that your local copy does not have. We use `pull` for this.

```
$ git pull origin master
$
```

You will see a message saying that some changes have come down from github to your local copy, if there is any.

### Stash

To save everything you've done in the working directory to files git is aware of, you can stash things:

```
$ git stash
```

Which will take a snapshot of your current working directory and reset the working directory to look like the most recent commit. You can jump around to different branches and do whatever you like then do the following to restore the state of your working directory:

```
$ git stash pop
```

to get the most recent stashed working directory. These are not committed changes. It's a temporary stack of snapshots.
