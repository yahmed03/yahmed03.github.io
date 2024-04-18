# training_github_pages

Graduate training - git, VS Code, terminal and basic web page building with Github Pages

## Learning Objectives

- Learn how to use git and Github
- Learn how to use VS Code
- Learn how to use the terminal
- Learn how to build a basic web page with Github Pages

## Prerequisites

- Create a [Github account](https://github.com/)
- Xcode command line tools - `xcode-select --install`
- Install [homebrew](https://brew.sh/) using `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
- Install node using `brew install node`
- Install [VS Code](https://code.visualstudio.com/) via homebrew using `brew install --cask visual-studio-code`
- Allow `VS Code` to be opened with `code` command in terminal [link](https://code.visualstudio.com/docs/setup/mac#:~:text=Keep%20in%20Dock.-,Launching%20from%20the%20command%20line,code'%20command%20in%20PATH%20command.)

# Tutorial

## Forking the repository

- Fork this repository to your own Github account
  > Important! Rename the repository to `<your_github_username>.github.io` - this is required for Github Pages to work. Read more about Github Pages [here](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site).
- Clone your forked repository to your local machine using `git clone`
  - Think about where you want to clone the repository to on your local machine and consider using the `.` operator
- Open the repository in VS Code using `code .`
- Open the terminal in VS Code using (on Windows) `Ctrl + Shift + ` or (on Mac) `Cmd + Shift + `

## Creating a new branch

You now have a copy of this repository on your local machine. You can now create a new branch to work on.

- Create a new branch using `git branch <branch_name>`
- Checkout the new branch using `git checkout <branch_name>`
- Push the new branch to your forked repository using `git push --set-upstream origin <branch_name>`
- In your VS Code terminal, you should now see that you are on your new branch
  - Also check the bottom left of the VS Code window to see that you are on your new branch `<branch_name>`

## Making changes

You will make changes on the new branch you have created. You will then commit and push these changes to your forked repository.

Making changes on a new branch is good practice as it means you can work on multiple features at the same time without affecting the `main` branch.

- Open the `README.md` file in VS Code
  - Alternatively, open the `README.md` file in preview mode in VS Code for a more readable view
- Update the areas in the `index.html` file that are marked with `TODO` comments
- Make edits to `style.css` to change the styling of the page marked with `TODO` comments
- Make changes to other styles in `style.css` to change the styling of the page (optional)
- Once you've made changes, stage the changes using `git add .`
- Commit the changes using `git commit -m "<commit_message>"`
  - Edit the <commit_message> to be a short description of the changes you have made
  - Best practice is to use the present tense in your commit message
- Push the changes to your forked repository using `git push origin <branch_name>`

Your changes should be on the github repository you forked on your account on the new branch you created.

## Creating a pull request

You will now create a pull request to merge your changes from your new branch into the `main` branch. This is standard practice when working on a project with multiple people.

- Go to your forked repository on Github
- Click on the `Pull requests` tab
- Click on the green `New pull request` button
- Select the `main` branch as the base branch
- Select your new branch as the compare branch

Here you will see the changes you have made on your new branch compared to the `main` branch. You can review the changes you have made and add comments if you wish.

- Add a title and description for your pull request
- Click on the green `Create pull request` button
- Wait for the pull request action to complete
  - If any of the checks fail, you will need to fix the issues on your local machine/branch and push the changes to your branch again, then let the pull request action run again

## Merging the pull request

At this point, you should have a pull request open on your forked repository. You will now merge this pull request into the `main` branch.

- Click on the green `Merge pull request` button
- Click on the green `Confirm merge` button
- Click the button to delete the branch after merging
- Go back to the `Code` tab
  - You should see that your changes have been merged into the `main` branch and only the `main` branch is available

## Pulling the changes to your local machine

Your remote and local repositories are now out of sync. You will now pull the changes from the remote repository to your local repository.

- Checkout the `main` branch using `git checkout main` in your VS Code terminal
- Pull the changes from the remote repository to your local repository using `git pull origin main`

## Setting up Github Pages

You will now set up Github Pages to host your web page.

- Go to the `Settings` tab on your forked repository
- Under `Code and automation`, click on `Pages`
- Under `Build and Deploy`, select `main` as the branch and `/ (root)` as the folder
- Click on the `Save` button
- Wait for the Github Pages action to complete
- Click on the link to your Github Pages site
  - should be in the format:
    - `https://<your_github_username>.github.io/` (if you've named your repository `<your_github_username>.github.io`)
    - `https://<your_github_username>.github.io/<your_repository_name>/` (if you've chosen a repository name other than `<your_github_username>.github.io`, you will need to add this to the url)
  - You should see your web page - this is live on the internet!

# Extension tasks

If you want to do more with your web page, here are a few ideas to get you started.

> Recommended: delete the .github/workflows file (or edit it to your needs), as you may have trouble merging changes to your main branch if you have the training Github Action running on your repository.

## Add a favicon (Easy)

In the images folder, you can find a favicon image. This is the icon that appears in the browser tab. You can add this to your web page by adding the following code to the `<head>` section of your `index.html` file

```html
<link rel="icon" href="images/favicon.png" type="image/png" />
```

## Add Blog pages (Medium)

You can have more than one page on your Github Pages site. You can add more pages by creating new html files in the root of your repository. You can then link to these pages from your `index.html` file.

> Note - this is a very simple, framework-agnostic approach to creating websites which isn't recommended for larger projects. For larger projects, you would use a framework such as Ruby on Rails, NextJS, .NET, etc. Managing multiple loose html files can become difficult to maintain in large teams and projects.

- Create a new html file in the root of your repository called `first_blog_post.html` (or similar)
- Add some basic html for your blog post to the file
- Add a link to your new blog post in the `index.html` file
  - Consider adding a Latest Blog Posts section to the index page
  - The link should be in the format `<a href="first_blog_post.html">First Blog Post</a>` and will be accessible at `https://<your_github_username>.github.io/first_blog_post.html`
- Add a link back to the index page from your new blog post or a back button
  - The link should be in the format `<a href="index.html">Back to Home</a>` and will be accessible at `https://<your_github_username>.github.io/index.html`

## Setup Jekyll (Hard)

Jekyll is a static site generator that is built into Github Pages. It allows you to create a site with multiple pages and blog posts using markdown files. You can read more about Jekyll [here](https://jekyllrb.com/).

Full guide to setting up Jekyll on Github Pages [here](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll).

If you want to try this, you can either:
- Create a new branch with Jekyll setup and merge this into your `main` branch
- Create a new repository with Jekyll setup and copy your changes from this repository into the new repository (recommended)

The first option *could* work, but you may have trouble merging changes to your `main` branch if you have the training Github Action running on your repository.

Creating a new repository is recommended as you can then copy your changes from this repository into the new repository. You can then delete this repository.
