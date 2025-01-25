# Setting up a dev container for Rust
* Primary author: [Samhitha Pudipeddi](https://github.com/samhipudi)
* Reviewer: [Margot Bohlin](https://github.com/margotbohlin)

## Intro

In this tutorial, you will create a "Hello COMP423" program in Rust by setting up a Dev Container project specifically for Rust. You will also learn how to use Git to manage your code history and share your project.

## Prerequistes

1. A GitHub account
2. Git installed
3. Visual Studio Code (VS Code)
4. Docker installed

## Git Repository Setup

### Creating a Local Directory & Initalize Git

1. Open your terminal
2. Create a directory for your project
``` bash
mkdir first-rust-project
cd first-rust-project
```
3. Initialize a new Git repository
``` bash
git init
```
4. Create a README file
``` bash
echo "https://samhipudi.github.io/comp423-course-notes/" > README.md
git add README.md
git commit -m "Adding tutorial link to README"
```
### Creating a Remote Repository on GitHub
1. Navigate to the Create a New Repository page after logging into GitHub
2. Fill in the details as follows:
    * Repository Name: first-rust-project
    * Description: "Following a Rust tutorial."
    * Visibility: Public
4. Click Create Repository

### Link your Local Repository to GitHub
1. Add the GitHub repository as a remote
``` bash
git remote add origin https://github.com/<your-username>/first-rust-project.git
```
2. Rename your default branch name to main if it is not main already using the command below
``` bash
git branch -M main
```
3. Push your local commits to the GitHub repository
``` bash
git push --set-upstream origin main
```



