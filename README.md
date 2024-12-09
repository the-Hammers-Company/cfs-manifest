#  Hammers cFS Training Manifest

Manifest file for Hammers Company cFE Training Exercises 

The manifest file in this repository is intended to be used with the git-repo tool to retrieve a collection of cFS repositories from the NASA github instance.  The manifest also retrieves a vagrant virtual machine configuration from the Hammers Company github instance.

To use this manifest, you will need the following installed on your machine:

- git
- git-repo (see below for installation instructions)
- A code editor of your choice

For Windows users, you will also need:

- PowerShell
- VirtualBox (to build and run the cFS)
- vagrant (to configure the VirtualBox VM)
- XMing (to use the cFS Ground System GUI)

For Mac users, you will also need:

- VirtualBox (to build and run the cFS)
- vagrant (to configure the VirtualBox VM)
- XQuartz (to use the cFS Ground System GUI)

---

## Instructions for Linux and Mac

(This has been tested on MacOS 13 and Ubuntu 20.04)

### Download and install the repo tool:

```bash
$ mkdir -p ~/.bin
$ PATH="${HOME}/.bin:${PATH}"
$ curl https://storage.googleapis.com/git-repo-downloads/repo > ~/.bin/repo
$ chmod a+rx ~/.bin/repo
```

### Create a project directory and download the manifest

```bash
# create the project directory
$ mkdir <large-project> 
$ cd <large-project>
# Download repo scripts from google. Download our desired custom manifest
$ repo init -u ssh://<username>@<url>.com/<path>/manifest 
# Download/Sync/Fetch from all git repositories listed in the manifest
$ repo sync 
# Optional: Repo start develop --all' will checkout a local branch 'develop' in each git repository
$ repo start develop --all
```

## Example

Generate a build-able cFS directory structure from NASA's repos on github 

```bash
# Navigate to a learning directory (we're assuming "lessons" has already been created for this example)
mymachine:some/path $ cd ~/lessons
# Create a new working project directory and navigate into it
mymachine:lessons $ mkdir practice
mymachine:lessons $ cd practice
# grab the manifest from github and use the "main" branch
mymachine:lessons/practice $ repo init -u https://github.com/the-Hammers-Company/cfs-manifest.git -b main
# Fetch the git repositories from the manifeest
mymachine:lessons/practice $ repo sync
```

At this point you can run the cFS CMake tool and build a running image of the flight software.  If you don't bother to run the "repo start" instruction, you can still either (1) navigate directly to a repository and use command-line git to check out branches, make commits, do pushes, and so on, or you can (2) add a temporary local repository entry to your favorite GUI-based git software and manage the repo graphically.
Just remember to push your changes and pull them to any "permanent" local repositories you might have.

---

## Instructions for Windows

This has been tested on Windows 10 using the PowerShell terminal window.

### Download and install the repo tool:

There are several versions of git-repo that have been modified for Windows, but most of the versions we've found have not been updated for a long time.  The version we use is "git repo 0.7.8"(64-bit) found at https://github.com/alibaba/git-repo-go/releases. 
 
```
Download git-repo-0.7.8-Windows-64.zip from https://github.com/alibaba/git-repo-go/releases and unzip it.
Copy the file git-repo.exe from the zip file to the C:\Windows\System32 directory.
```

### Create a project directory and download the manifest

```bash
# create the project directory
C:\Users\[your_path]> mkdir <large-project> 
C:\Users\[your_path]> cd <large-project>
# Download repo scripts from google. Download our desired custom manifest
C:\Users\[your_path]\[large-project]> git-repo init -u ssh://<username>@<url>.com/<path>/manifest 
# Download/Sync/Fetch from all git repositories listed in the manifest
C:\Users\[your_path]\[large-project]> git-repo sync 
# Optional: Repo start develop --all' will checkout a local branch 'develop' in each git repository
C:\Users\[your_path]\[large-project]> git-repo start develop --all
```

## Example

Generate a build-able cFS directory structure from NASA's repos on github 

```bash
# Navigate to a learning directory (we're assuming "lessons" has already been created for this example)
C:\some\path> cd ~/lessons
# Create a new working project directory and navigate into it
C:\Users\myname\lessons> mkdir practice
C:\Users\myname\lessons> cd practice
# grab the manifest from github and use the "main" branch
C:\Users\myname\lessons\practice> git-repo init -u https://github.com/the-Hammers-Company/cfs-manifest.git -b main
# Fetch the git repositories from the manifeest
C:\Users\myname\lessons\practice> repo sync
```

At this point you can run the cFS CMake tool and build a running image of the flight software.  If you don't bother to run the "repo start" instruction, you can still either (1) navigate directly to a repository and use command-line git to check out branches, make commits, do pushes, and so on, or you can (2) add a temporary local repository entry to your favorite GUI-based git software and manage the repo graphically.
Just remember to push your changes and pull them to any "permanent" local repositories you might have.
