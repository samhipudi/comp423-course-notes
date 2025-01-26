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
!!! note 
    If you want to create this tutorial directory somewhere else on your machine, change into that parent directory first. Otherwise, the tutorial directory will be made in the parent directory.

3. Initialize a new Git repository
``` bash
git init
```
4. Create a README file linking the tutorial page
``` bash
echo "https://samhipudi.github.io/comp423-course-notes/tutorials/rust-setup/" > README.md
git add README.md
git commit -m "Adding tutorial link to README"
```
### Creating a Remote Repository on GitHub
1. Navigate to the Create a New Repository page after logging into GitHub
2. Fill in the details as follows:
    * __Repository Name__: first-rust-project
    * __Description__: "Following a Rust tutorial."
    * __Visibility__: Public
4. Click Create Repository

### Link your Local Repository to GitHub
1. Add the GitHub repository as a remote one
``` bash
git remote add origin https://github.com/<your-username>/first-rust-project.git
```
2. Rename your default branch name to main if it is not already using the command below
``` bash
git branch -M main
```
3. Push your local commits to your GitHub repository
``` bash
git push --set-upstream origin main
```

## Setting Up the Development Enviornment

1. Open the `first-rust-project` directory in VS Code
2. Install the Dev Containers extension for VS Code
3. Create a `.devcontainer` directory in the root of your project with the following file inside:
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

    !!! note 
        This allows us to define the configuration for our development enviornment. `name` = Descriptive name for the container. `image` = The Docker image to use (latest version of a Rust environment). `customizations` = Installing the rust-analyzer extension to our environment.

5. Reopen the Project in a VSCode Dev Container by pressing `Ctrl+Shift+P` (`Cmd+Shift+P` for Macs) and type in "Dev Containers: Reopen in Container", and select the option. 
6. After the dev continer setup completes, open a new terminal pane within VSCode and run `rustc --version` to see your dev continer running a recent version of Rust.

    !!! success
        As of January 2025, the latest version is rustc 1.83.0

## Creating a Rust Project

### Create a New Rust Binary Project
1. In your terminal, run the command:
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

### Running the project

#### Option 1:

1. To compile the project run the following command in the terminal:
`cargo build`

    !!! info
        This command, like the gcc command which compiles C programs into executables (files that a computer's operating system can run), simply compiles the source code into a binary executable file without executing it. 

2. To run the compiled binary file, run the following command in the terminal:
`./target/debug/hello_comp423`

#### Option 2:

1. Instead of completing the steps in option 1, you can also run the following command in the terminal: `cargo run`. This command combines both building and running the program. 

    !!! info
        `cargo build` compiles the project and generates and executable, but does not run it. `cargo run` both compiles and runs the project in one step.


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

## Citations
Many instructions in this tutorial were written using the following resources:

* COMP423 Course Materials: [COMP423 Starting a Static Website project with MkDocs](https://comp423-25s.github.io/resources/MkDocs/ex00/#tutorial-content-requirements)
* Rust Documentation: [Documentation Used](https://doc.rust-lang.org/book/ch01-02-hello-world.html)


