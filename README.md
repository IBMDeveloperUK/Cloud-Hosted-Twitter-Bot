# cloud-hosted-twitter-bot

This workshop will show you how to build a simple Golang application and then deploy it into a cloud environment.

## Golang Installation

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

## Prerequisites

1. Twitter API Keys - These can be obtained by registering for a [developer account](https://developer.twitter.com/en/docs/basics/developer-portal/overview) on Twitter. This is only needed for the final lab and takes ~15minutes to set up
2. An IDE installed \(GoLand/Visual Studio Code etc\)

---

- [Presentation]
- [Lab-0]
- [Lab-1]
- [Lab-2]
- [Lab-3]
- [Lab-4]

[Presentation]: ./presentation/Intro_to_Golang.pdf
[Lab-0]: ./Labs/lab-0.md
[Lab-1]: ./Labs/lab-1.md
[Lab-2]: ./Labs/lab-2.md
[Lab-3]: ./Labs/lab-3.md
[Lab-4]: ./Labs/lab-4.md
