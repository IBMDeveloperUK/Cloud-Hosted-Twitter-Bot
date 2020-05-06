# Lab 0 - Install the Prerequisites

## 1. Golang Installation

### Automated Installation \(**Ubuntu 16.04+ & macOS only**\)

Use [this open source repository](https://github.com/canha/golang-tools-install-script) to install Golang onto your machine.

Ubuntu 16.04+

```bash
wget -q -O - https://raw.githubusercontent.com/canha/golang-tools-install-script/master/goinstall.sh \
| bash -s -- --version 1.14.1
```

macOS

```bash
brew install go
```

or

```bash
curl https://raw.githubusercontent.com/canha/golang-tools-install-script/master/goinstall.sh \
| bash -s -- --version 1.14.1
```

Once the installation has finished, create a folder called `github.com` inside `$HOME/go/src`. Copy and paste the following command to do this for you.

```bash
mkdir $HOME/go/src/github.com
```

### Manual Installation

1. To manually install the Go tools, use the [Go documentation](https://golang.org/doc/install) and follow the instructions 
2. Ensure your system follows the folder tree below

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

---

## 5. IDE
[Visual Studio Code](https://code.visualstudio.com/) with the recommended [Go extension](https://code.visualstudio.com/docs/languages/go). When you begin to code Go inside VSCode you may be prompted to install a bunch of extnesions. These are good and will help make development much easier!

OR

[Jet Brains GoLand](https://www.jetbrains.com/go/download/#section=mac) (GoLand isn't free but it does have a 30 day free trial)


Once you are all set up you can move straight on to [Lab 1](./lab-1.md)
