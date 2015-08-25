# Intro to Vagrant

This document is meant to be a getting started guide to [Vagrant](http://vagrantup.com/). It will walk you through getting a development environment setup on your computer. Complete documentation about Vagrant can be found on [Vagrant's Website](https://vagrantup.com/.)

## A note about the Terminal

When I talk about the Terminal throughout this document, I mean one of the following things:

- If you're on Mac or Linux, I mean the Terminal.  Mac users, you can find the Terminal application in the Utilities folder (or just type 'Terminal' into Spotlight). Linux people: You know what the Terminal is.
- If you're on Windows, the Terminal is Git Bash.  You should install it with Git (outlined below).

## Installation

There are a few pieces of software that need to be installed prior to getting a development environment setup.

### Step 1: Install VirtualBox
Visit https://www.virtualbox.org/ to download the version of VirtualBox that works on your computer. It's an automatic installer, so hopefully nothing goes wrong.

### Step 2: Install Vagrant
Visit http://vagrantup.com/ to download and install the version of Vagrant for your system. Once again it is a simple automatic installer.

### Step 3: Install Git
Visit http://git-scm.com/ and download the version of Git for your system. There is an automated installer for this as well. The default options should work well enough.

**If you are using Windows, make sure you include Git Bash in your install!**

**If you are new to programming or Git:** I would strongly suggest that you download [GitHub Desktop](https://desktop.github.com/). It is pretty friendly, and comes with a tutorial.

### Usage

Vagrant is a command line tool, and thus it helps to be familiar with Bash commands. If you're new to Bash don't worry, it isn't that bad, and it's a very useful thing to have a working knowledge of. Here is a good guide: [The Command Line Crash Course](http://cli.learncodethehardway.org/book/).

### Clone this repository

GitHub Desktop

1. It will be necessary for you to fork this repository before cloning it. To do so, simply hit the 'Fork' link in the top-right of this page.
2. Open GitHub Desktop, if you do not already have it open.
3. Click to '+' icon in the top-left of the GitHub Desktop window.
4. In the panel that appears, click the 'Clone' link in the panel that appears.
5. In the text box in the panel, type 'cwdg-vagrant'.
6. Click the 'Clone cwdg-vagrant' button.
7. Select where on your computer you want to have the CWDG vagrant. It doesn't matter where you put it, just remember where it is.

Command Line

1. Pat yourself on the back for being cool.
2. `cd` into the directory where you would like to put this repository.
3. If you have your ssh keys uploaded to GitHub, run `git clone git@github.com:CWDG/cwdg-vagrant`. Otherwise, run `git clone https://github.com/robbyrussell/oh-my-zsh.git`. **If you do not know whether you have your ssh keys uploaded to GitHub, you probably do not.

## Workflow

### Start the VM

Using the terminal of your choice (Git Bash is a valid option for Windows), use `cd` to go where you cloned this repo. If you are new to the shell, try using `ls` and `pwd` to get your bearings. Using `cd ..` will take you up to the parent directory of the one you are in.

Once you are in the place where you cloned this repo, run `vagrant up`.

### ssh into the running VM

Once the `vagrant up` command finishes, it is time to ssh into your virtual machine.  Simply type

```
vagrant ssh
```

And you will connect to your virtual machine.  You now have access to a Linux machine that is preconfigured with our Ruby on Rails development environment setup.

When you're done working in your VM, type `exit` to close the ssh connection and return to your computer's terminal.

### Doing exercises

In your "home" directory, there will be a directory called "workspace". This is where we will be doing our exercises. This directory is linked from inside the VM to the "workspace" folder inside this cloned repository on your computer. This way, you can use [Atom](https://atom.io/) or [Sublime Text](www.sublimetext.com) to edit files within the "workspace" folder natively on your computer, and your changes will be present inside of the Vagrant VM.

The workflow for doing exercises will be:

1. Fork the exercise repository on GitHub
2. Clone the repository **into the "workspace" directory inside of this repository** using your preferred method (GitHub Desktop or just `git`).
3. ssh into the VM using `vagrant ssh`.
4. Go to the "workspace" directory inside the VM using `cd workspace`.
5. Make your changes locally on your computer. Test them inside the VM.
6. Commit your changes with Git.
7. Open a pull-request against the exercise repo on GitHub.
8. Celebrate and wait for a peer review!

### Shutting down the VM

When you are done using the VM, make sure to shut it down by running:

```
vagrant halt
```

**Make sure you do this inside your clone of this repository**.

## Updating

You should occasionally update your Vagrant box. You can do this by running `./scipt/update` in your clone of this repository. **I am unsure this works in Git Bash**.

