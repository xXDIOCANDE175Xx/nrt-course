# Setup

- [Setup](#setup)
  - [Node and npm](#node-and-npm)
    - [Windows](#windows)
    - [Ubuntu](#ubuntu)
  - [Playwright](#playwright)
  - [Docker](#docker)
    - [Windows](#windows-1)
    - [Ubuntu](#ubuntu-1)
  - [Visual Studio Code (VSCode)](#visual-studio-code-vscode)


To be able develope automatic NRT we need install on the workstation this components/tools/framework:

* node and npm
* Playwright
* Docker
* Develope IDE (recommended Visual Studio Code)

## Node and npm

### Windows

???

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

## Playwright

```sh
npm init playwright@latest
```

## Docker

### Windows

???

### Ubuntu

Follow instruction on official [Docker page](https://docs.docker.com/engine/install/ubuntu/). Below you can find a cndensed version.

Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker repository. Afterward, you can install and update 

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

Download from the [official site](https://code.visualstudio.com/) the last version available for your operative system (you can find at bottom of the official page setup download).

VSCode offer a large catalog of plugins we can suggest some of them very useful to accelerate and semplify develop activities:

* Gitlens - Git supercharged
* Docker Extension Pack

To install extension click on **Extensions** icon on the left of the IDE :

![VSCode extensions](1_setup/extensions.png)

on the top you will find a search box where type your search terms. When you find desired extension click on **install** blue button near the description of the extension

---

[[Return to main page](./0_NRT.md)] - [[Next chapter (first test)](./2_FIRST_TEST.md)]