# Lab 0 - Install the Prerequisites

## 1. Golang Installation

### Ubuntu 16.04+
The following `wget` command makes use of [this open source repository](https://github.com/canha/golang-tools-install-script) to install Golang onto your machine and configure the environment.

```bash
wget -q -O - https://raw.githubusercontent.com/canha/golang-tools-install-script/master/goinstall.sh \
| bash -s -- --version 1.14.2
```

or

Follow this [quick installation](https://medium.com/better-programming/install-go-1-11-on-ubuntu-18-04-16-04-lts-8c098c503c5f) guide. Making sure you change `1.11` -> `1.14.2` (This should also work on Ubuntu 20.04)

### macOS

The following `curl` commands make use of [this open source repository](https://github.com/canha/golang-tools-install-script) to install Golang onto your machine and configure the environment.

```bash
curl https://raw.githubusercontent.com/canha/golang-tools-install-script/master/goinstall.sh \
| bash -s -- --version 1.14.2
```

or

Follow this short [installation guide](https://quii.gitbook.io/learn-go-with-tests/go-fundamentals/install-go) up the end of the section "Go Environment".

### Windows / Manual Installation

To manually install the Go tools, use the official [Go documentation](https://golang.org/doc/install) and follow the instructions.

> **Note**: A quick Windows setup guide can be found [here](https://www.geeksforgeeks.org/how-to-install-go-on-windows/)

### Check your version

In your terminal, check your go version by using the following command

```bash
go version
```

Once Go is installed via which ever method you have chosen, it is **important** to ensure your system follows the folder tree shown below:

```bash
.
├── $HOME
│   ├── /go
│        ├── /bin
│        ├── /pkg
│        └── /src
│             └── /github.com
```

---

## 2. IBM Cloud account registration

Login or create an [IBM Cloud](https://cloud.ibm.com/login) account

---

## 3. IBM Cloud command line interface installation

(If you already have these setup and installed, go straight to [Lab 1](./lab-1.md) // FIX THIS LINK

1. Install the [IBM Cloud command-line interface from this link](https://cloud.ibm.com/docs/cli?topic=cloud-cli-install-ibmcloud-cli).

   Once installed, you can access IBM Cloud from your command-line with the prefix `ibmcloud`.

2. Log in to the IBM Cloud CLI: `ibmcloud login`.
3. Enter your IBM Cloud credentials when prompted.

> **Note**: If you have a federated ID, use `ibmcloud login --sso` to log in to the IBM Cloud CLI. Enter your user name, and use the provided URL in your CLI output to retrieve your one-time passcode. You know you have a federated ID when the login fails without the `--sso` and succeeds with the `--sso` option.

---

## 4. Create a Twitter account

Login or create a [Twitter account](https://twitter.com/?login)

---

## 5. IDE

[Visual Studio Code](https://code.visualstudio.com/) with the recommended [Go extension](https://code.visualstudio.com/docs/languages/go). When you begin to code Go inside VSCode you may be prompted to install a bunch of extnesions. These are good and will help make development much easier!

OR

[Jet Brains GoLand](https://www.jetbrains.com/go/download/#section=mac) (GoLand isn't free but it does have a 30 day free trial)

Once you are all set up you can move straight on to [Lab 1](./lab-1.md)
