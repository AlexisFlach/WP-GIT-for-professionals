#### Git for professionals Tutorial

Notes from the course: https://www.youtube.com/watch?v=Uszj_k0DGsg&t=328s

#### The perfect commit 

- Add the right changes
- Compose a good commit message

###### Add the right changes

Only combine changes from the same topic in a single commit.

```
git add 404.php
```

```
git diff index.php
```

```
index c489446..9bc1279 100644
--- a/index.php
+++ b/index.php
@@ -1,3 +1,6 @@
 <?php

-echo "hello world";
\ No newline at end of file
+echo "hi world";
+
+
+echo "new line here";
```

```
git add -p index.php
```

A commit should be easy to read and understand.

###### The perfect Commit message

1. Subject = concise summary of what happend
2. Body= More detailed explanation
   - What is now different than before?
   - What is the reason for the change?
   - Is there anything to watch out fore / anything particulary remarkable?

```
git commit
```

```
Add 404 page

404 page now added
- simple 404 page

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# On branch main
# Your branch is ahead of 'origin/main' by 1 commit.
#   (use "git push" to publish your local commits)
#
# Changes to be committed:
#       new file:   404.php
#       modified:   index.php
#
# Changes not staged for commit:
#       modified:   README.md
```

```
:wq
```

```
git log
```

#### Branching Strategies

Git leaves it completely up to you how you want to work with branches. We are the ones responsible for using it in the optimal way.

###### A written convention

Agree on Branching Workflow in your team

1. Git allows you to create branches - but it doesn't tell you how to use them.
2. You need a written best practise of how work is ideally structured in your team - to avoid mistakes and collisions.
3. It highöy depends on your team / team size, on your project, and how you handle releases.
4. It helps to onboard new team members("this is how we work here")

#### How to design your Branches Workflows

######  Integrating Changes & Structuring Releases

1. Mainline Development ("Always Be Integrating")
2. State, Release, and Feature Branches

###### Mainline Development

"Always Be Integrating"

- few branches
- relatively small commits
- High-quality testing and QA standards

###### State, Release, and Feature Branches

Branches Enhances Structure & Workflows

- Different type of branches
- ...that fulfill different types of jobs

The idea here is to work with feature branches.

#### Two main types of Branches - Long-Running & Short-Lived Branches

###### Long-Running

- exists through the complete lifetime of the project
- Often, they mirror "stages" in your dev life cycle
- common convention: no direct commits!
  - They should only make it to long-running branches through integration; merge or rebase. We dont want to add un-tested, un-reviewed code to our production environment, for example.

They often represent states in a projects dev or realeas process.

###### Short-lived

- for new features, bug fixes, refactoring, experiments...
- will be deleted after integration (merge/rebase)

#### Two Example Branching Strategies

1. GitHub Flow
2. GitFlow

###### GitHub Flow

- very simple. Only one long-running branch("main") + feature branches.

Everything we currently are working on is done in a seperate branch (feature branch).

###### GitFlow

- more structure, more rules
- Long-running: 'main' + 'develop'
- Short-lived: features, releases, hotfixes

The main branch is a reflection of the current production state. Every short-lived branch starts from "develop", and will be merged back into that one. When we are done with "development" we merge it back to "main".

#### The "best" Branching Model?

- depends on project, release cycle, and team
- take inspiration from existing models(like "GitFlow" and "GitHub Flow")
- ...and create your own model!

#### Pull request

Why would you want to use Pull Requests?

A way of Communicating About and Reviewing Code.

A good example is when you are finished working on a feature. Without a pull request you would simply merge your code into main. In that stage, a pull requests invites reviewers to provide feedback before merging. A second pair of eyes. And this is what Pull Requests was created to do.

Another reason is to contribute code to other repositories.

###### Forks

A fork is a personal copy of a repository. Creating a "fork" of the original repository where you can make changes, and later suggest those changes to be included via a Pull Request.

Since we don't have permission to make pushes directly to a repository we don't own, forking it and come up with suggestions via a Pull Requests is way of doing it!

#### Merge conflicts

###### How and When Conflicts Occur

When integrating Commits from Different Sources

Merging Changes in Git = A flawless Process, most of the time.

The conflicts happens when Git can't know what's correct: when contradictory changes happen.

These decisions require a decision from a human.

And how to know when a Conflict has occurred? Git will tell you!

```
git merge develop
```

```
git status
```

```
Unmerged paths:
```

###### How to Undo a Conflict and Start over?

```
git merge --abort
```

```
git rebase --abort
```

How to solve it?

Simply clean up the file!

#### Merge Vs. Rebase

Integrating Strategies.

The two most common ones i merge and rebase.

###### Merge

```
git merge develop
```

When Git performs a merge it looks for three commits:

1. common ancestor
2. Last commit on branch-A
3. last commit on branch-B

###### Rebase

A straight line of Commits

```
git rebase develop
```

Do not use Rebase on commits that you have already pushed/shard on a remote repository!

Instead. use it for cleaning up your local commit history before merging it into a shared team branch.



#### Many thanks

Thanks to Freecodecamp and Tower.

[https://www.git-tower.com](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbVIyQUYwSHNXLTIxWDZIWXNEanBmSk1TR09DQXxBQ3Jtc0ttNEtBNXItdV9TYU9zdEFkUGt6VjRGYlZZcHJPN21MMHJFRkgxdUotdFFyMUhIU1dsMUhYWW5IdTlsS3BIWUNTSFZ2ekpwSmlFNWprUmE4RUJkeGhOWExXZUFyM09faklmOVVMQVVTSmNma2dzSEg4cw&q=https%3A%2F%2Fwww.git-tower.com)

https://www.freecodecamp.org/