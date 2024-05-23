# 📦 LudsGit

> **Short Description**: Automate github repository initialization for C project (more to come).

## 📖 Short Presentation

**LudsGit** is a project setup tool that automates the creation of a GitHub repository structure, including workflows and Makefile for a C project (mainly for EPITECH). It ensures that your project is initialized with the necessary files and configurations to maintain coding standards, build processes, and documentation generation.

Feel free to explore the project and contribute to its development. I appreciate your interest and involvement!

## Features

- **Automated Project Initialization**: Sets up directory structure, includes initial C source and header files.
- **GitHub Actions Workflows**:
  - `deploy.yml`: Handles push and pull request events, checks coding style, builds the project, and deploys.
  - `doxygen.yml`: Generates Doxygen documentation on push to the `main` branch.
- **Customizable Makefile**: Includes targets for building, cleaning, and rebuilding the project, with colored logs for easy readability.

## Directory Structure

After running the script, the project directory will have the following structure:

```
$(NAME)/
├── .github/
│ └── workflows/
│ ├── deploy.yml
│ └── doxygen.yml
├── include/
│ └── $(NAME).h
├── src/
│ └── main/
│ └── main.c
└── Makefile
```

## 💻 Technical Presentation

### Technologies Used

[![made-with-bash](https://img.shields.io/badge/Made%20with-Bash-1f425f.svg)](https://www.gnu.org/software/bash/)



## Installation

1. **Download the Script**: Save the script to your preferred location, e.g., `/usr/local/bin`.

    ```sh
    sudo nano /usr/local/bin/ludsgit
    ```

2. **Paste the Script**: Copy the content of the provided script into the editor.

3. **Save and Exit**: Press `CTRL + O`, then `Enter` to save. Press `CTRL + X` to exit.

4. **Make the Script Executable**:

    ```sh
    sudo chmod +x /usr/local/bin/ludsgit
    ```

## Usage

To initialize a new project, run the script with the repository URL and project name:

```sh
ludsgit <repository_url> <project_name>
```

Run `make help` to get all Makefile features

### Example

```
ludsgit git@github.com:username/repo.git MyProject
```

### Workflows features

`deploy.yml`

This workflow runs on push and pull_request events and includes:

    Repository Mirror Check: Verifies if the repository is a mirror.
    Coding Style Check: Uses a coding style checker container to validate coding standards.
    Build: Compiles the project using the Makefile.
    Deploy: Pushes changes if all checks pass.
    Discord Notification: Sends a report to a specified Discord webhook.

`doxygen.yml`

This workflow generates Doxygen documentation on pushes to the main branch:

    Doxygen Documentation: Uses the DenverCoder1/doxygen-github-pages-action to generate and deploy documentation to the gh-pages branch.

## Tips

- Don't forget to complete the github actions and your secrets with the needed tokens, SSH key and discord Webhook.
- Feel free to edit if as you need.
- If you're running on arch, it seems that you'll have to add "-e" in each line of the `make help`.

## 👥 Contributing

Feel free to fork this repository and submit pull requests to enhance the functionality or fix any issues.
