# Install Nodejs from Repo

## Step 1: Add Node.js Repository

Step 1: Add Node.js Repository

```shell
curl -sL https://deb.nodesource.com/setup_16.x | sudo -E bash -
```

Step 2: Update System

After adding the node repository, run the update command below to flush the system's repository cache. That lets the system know you have added a new repository.

```shell
sudo apt update
```

## Step 3: Install Node.js Version 14 on Kali Linux

Up to this point, we have everything present on our system to download and install the latest version of Node.js and NPM. Execute the command below.

```shell
sudo apt install nodejs
```

## Step 4: Check Node and NPM Versions

*Tip:* Node.js installer includes the NPM package manager. Therefore, by installing Node.js, you also install NPM.

To check the installed version of Node.js, run the command below.

```shell
node -v
```

To check the installed version of NPM, run the command below.

```shell
npm -v
```
