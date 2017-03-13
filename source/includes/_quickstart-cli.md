# Using the command line

The Flex.io Command Line Interface (CLI) is a tool used to manage your Flex.io resources and services.   One just one compact tool, you can integrate Flex.io services into your scripts and command-line environment, enabling powerful integration with other systems and software.

## Download and Install

If you use a Mac or want to install via npm (on Windows, Mac, or Linux), you can install using the following command

```
$ npm install -g flexio
```

If you use a Windows or Linux computer, the following binary installation packages are available for download:

* [Windows MSI (64-bit)](http://downloads.flex.io/flexiocli.msi)
* [Windows standalone executable (64-bit)](http://downloads.flex.io/flexiocli.zip)
* [Linux/Debian .deb](http://downloads.flex.io/flexiocli-1.0-amd64.deb)
* Linux/Redhat .rpm (TBA)

## Source Code

The source code is available on Github.  Download it or view it [here](https://github.com/flexiodata):

## Configure

After installation, to begin using the Flex.io Command Line Interface, you must first configure it with your API Key.   The API Key can be found on your account info page on Flex.io's website.

```
$ flexio configure\nConfiguring profile 'default'\nPlease enter your API key: YOUR-API-KEY",
```

## Run Flex.io CLI commands

After configuring the Flex.io Command Line Interface, integrating with Flex.io pipes and services is a snap.

```
$ flexio pipes run r9q485j56n data.csv
```
