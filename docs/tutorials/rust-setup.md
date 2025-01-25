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

## Setting Up the Development Enviornment

1. Open the `first-rust-project` directory
2. Install the Dev Containers extension for VS Code
3. Create a .devcontainer directory in the root of your project with the following file inside:
`.devcontainer/devcontainer.json`
4. Add the following code into that file:
``` json
{
  "name": "First Rust Project",
  "image": "mcr.microsoft.com/devcontainers/rust:latest",
  "customizations": {
    "vscode": {
      "settings": {},
      "extensions": ["rust-lang.rust-analyzer"]
    }
  }
}
```
The result of the `rustc --version` command should show the most recent version of rust.

5. Reopen the Project in a VSCode Dev Container by pressing `Ctrl+Shift+P` (`Cmd+Shift+P` for Macs) and type in "Dev Contianers: Reopen in Container", and select the option. 
6. After the dev continer setup completes, open a new terminal pane within VSCode and run `rustc --version` to see your dev continer running a recent version of Rust.

## Creating a Rust Project

### Create a New Rust Binary Project
1. In the terminal, run the command:

``` bash
cargo new hello_comp423 --bin --vcs none
```

2. Change to the project's directory with the following command:
``` bash
cd hello_comp423
```

3. Open the `src/main.rs` file in the `src` folder
4. Add the following code to the `main.rs` file and save:
``` rust
fn main() {
    println!("Hello COMP423");
}
```

### Build the project
1. To compile the project run the following command in the terminal:
`cargo build`
This command, like the gcc command which compiles C programs into executables, simply compiles the source code into binary without executing it. 

2. To run the compiled binary file, run the following command in the terminal:
`./target/debug/hello_comp423`

* Instead of completing steps 1 and 2, you can also run the following command in the terminal: `cargo run`. This command combines both building and running the program. 
* `cargo build` compiles the project and generates and executable, but does nto run it. `cargo run` both compiles and runs the project in one step.


## Pushing Changes to GitHub Repository
1. Add and commit your changes with the following commmands:
``` bash
git add .
git commit -m "Hello COMP423 in Rust"
```
2. Push the changes to GitHub:
``` bash
git push origin main
```

## Conclusion

Congratulations! You have now created your first rust project inside of a dev container!


