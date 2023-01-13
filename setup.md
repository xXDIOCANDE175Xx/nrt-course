# Setup

- [Setup](#setup)
  - [Node and npm](#node-and-npm)
    - [Windows](#windows)
    - [Ubuntu](#ubuntu)
    - [NPM registry configuration](#npm-registry-configuration)
  - [Playwright](#playwright)
  - [Docker](#docker)
    - [Windows](#windows-1)
    - [Ubuntu](#ubuntu-1)
  - [Visual Studio Code (VSCode)](#visual-studio-code-vscode)
  - [Setup existing project](#setup-existing-project)


To get started in automatic NRT development we need install on our personal machine this components/tools/frameworks:

* node and npm
* Playwright
* Docker
* Develope IDE (recommended Visual Studio Code)

## Node and npm

### Windows

Download the Node.js Windows installer from the official [Node.js website](https://nodejs.org/en/download/).

Run the installer; this will install Node.js, npm and add them to your PATH environment variable.

To check installation, type in Command Prompt:
```sh
node -v
npm -v
```
### Ubuntu

```sh
sudo apt install nodejs
sudo apt install npm
```

to check installation

```sh
node -v or node –version
npm -v or npm –version
```

### NPM registry configuration

To add a new private registry you need to edit the npm configuration
```sh
npm config set @rgi:registry "https://rgiregistry.ad.rgigroup.com:8443/repository/npm-group"
```

## Playwright
*This method uses the Playwright native runner (npx), in our projects we use our own runner based on Cucumber*

Create a folder and inside it run this command

```sh
npm init playwright@latest
```

## Docker

### Windows

Download the Docker Desktop installer from the [Docker page](https://www.docker.com/products/docker-desktop)

Double-click on the downloaded .exe file to start the installation process.

Follow the prompts to install Docker Desktop on your system. This will install the Docker Engine, as well as other tools such as Docker Compose and Docker CLI.

Once the installation is complete, click on the Docker icon in the system tray to launch the Docker Desktop application.

To check installation, write in cmd

```sh
docker --version
```

### Ubuntu

Follow instructions on official [Docker page](https://docs.docker.com/engine/install/ubuntu/). Below you can find a slim version.

Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker repository. Afterwards, you can install and update 

```sh
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg lsb-release
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

install docker 

```sh
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

## Visual Studio Code (VSCode)

Download the latest VSCode version available from the [official site](https://code.visualstudio.com/) for your operative system (you can find at bottom of the official page setup download).

VSCode offers a large catalog of plugins: we can suggest some of them which are very useful to accelerate and simplify development activities:

* Gitlens - Git supercharged
* Docker Extension Pack
* JavaScript and TypeScript Nightly
* npm Intellisense
* Cucumber (Gherkin) Full Support ([See here if not link steps in feature with definition](./troubleshoot.md#link-steps-in-the-feature-with-their-definition))

To install an extension click on **Extensions** icon in the left sidebar of the IDE:

<img width="50" height="50" src="images/setup/vscode_extension.webp"></img>

on the top you will find a search box where type your search terms. When you find the desired extension click on the **install** blue button near the description of the extension.

## Setup existing project

To setup an existing NRT project in your local workspace run the following commands

```sh
git clone <repo-url>
cd <repo>
npm install
```

---

[[Return to main page](./main-page-nrt.md)] - [[Next chapter (Basic concept)](./basic_concept.md)]