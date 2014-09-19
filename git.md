# Git

## Environment

In order to maintain the quality of the code you should install [Editor Config](http://editorconfig.org/) on your text editor. There are plugins for the vast majority of text editors, such as [VIm](https://github.com/editorconfig/editorconfig-vim#readme), [Sublime](https://github.com/sindresorhus/editorconfig-sublime#readme) or [Textmate](https://github.com/Mr0grog/editorconfig-textmate#readme).


## The master branch

The **master is the main branch** in the system. It reflects the code used in production. Anything in this branch should be immediatelly ready for deploy. The tests (Ruby and Javascript) are not allowed to fail in this branch.


## New features and bugfixes flow

If you want to develop a new feature or to correct a bug:

1. Update your master branch.

```
git checkout master
git pull origin master
```

2. Create a branch from master and go to it. Its name should give a short description about what you are trying to solve.

```
# In the master branch
git branch name_of_branch
git checkout name_of_branch
```

3. Change the code as you need, and keep commiting to the branch you created.

4. If it is a large feature or bugfix, send the code to Github, so other people can review the code. Integrate the changes in master everyday, so your code don't stay out of sync with the rest of the project.

```
# To send it to Github
# In the feature/bugfix branch
git push origin name_of_branch

# Make sure your master branch is up-to-date
git checkout master
git pull origin master
# And then integrate to your branch
git checkout name_of_branch
git merge master
```

5. When the feature or bugfix is ready, integrate the master changes for the last time and run the tests.

```
# In the feature/bugfix branch
git merge master
foreman run rake spec konacha:run
```

6. If all the tests are passing, send the code to Github and create a _Pull Request_ by clicking in the _Pull Request_ button in the top of the page. There's a helpful guide from Github teaching [how to send Pull Requests](https://help.github.com/articles/creating-a-pull-request). **Always** write a description about the new feature or bug you are trying to solve and put its link from Basecamp.

7. If the bugfix is too simple, integrate it directly to master, without Pull Request. Make sure all the tests are passing and do not forget to delete the branch (from Github and from your local repository).

```
# In the master branch
git merge name_of_branch
foreman run rake spec konacha:run
# Delete from your local repo
git branch -d name_of_branch
# Delete it from Github
git push origin :name_of_branch
```

## Remarks

- Avoid to commit directly to the master branch, except in very simple cases.

- The _commit_ messages should always be in english. Format it like a phrase. Describe the changes completely, but try to be concise. Examples:

```
# Good
Updates Rails version to 3.2.10.
# Good
Switches angular back to 1.0.2. Posts doesn't open with version 1.0.3.
# Bad. Too general. What tests were added?
Tests
# Bad. Starts in with verb in gerund
Making posts more easy to use.
# Bad. In portuguese. Too verbose. It is usually a bad idea to use filepaths in commit messages
Autenticação com Twitter funcionando. Detalhe para o app/models/user/location.rb, que foi modificado para que tudo funcionasse corretamente.
```

There is a lot of useful information about commit messages in the [OpenStack wiki](http://wiki.openstack.org/GitCommitMessages).

- Do not change the default merge messages. They point what branches were merged and if there was any conflict.

- Before adding files, perform a `git diff` and review the changes. Look for debugging code that is not necessary anymore (yeah, that `puts` or that `console.log`) and make sure all the changes are relevant to the commit.

- You can also use a diff tool to better visualize the modifications. There are many available, such as [FileMerge](http://en.wikipedia.org/wiki/Apple_Developer_Tools#FileMerge) or [Kaleidoscope](http://www.kaleidoscopeapp.com/). See how to setup the difftool for Git in [this post](http://www.silverwareconsulting.com/index.cfm/2010/6/21/Comparing-Files-from-Different-Branches-with-Git-Difftool).

- Avoid to use the `git add .` command. Instead, take time to review and add the files separately.

- Always commit the minimum set of changes that makes sense to be together. It can be four new files or just a variable renaming. If it is a completed unit of work, commit it.

- Prefer small commits. Commits are free, so you don't need to save them.

- If your commit message has multiple phrases, items or _and_ clauses, it is probably too large. Try splitting it in multiple commits.

- Use `git add filename -p` to add partial modifications when needed. Know more about partial commits in [Codingdomain](http://codingdomain.com/git/partial-commits/).

- If you are new to the project, take a time to look at the commit history and previous pull requests. Pay attention to their size and how they are structured.
