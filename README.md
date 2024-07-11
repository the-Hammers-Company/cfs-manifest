#  Hammers cFS Training Manifest
Manifest file for Hammers Company cFE Training Exercises 


## How to use the manifest file(s) in this repo

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
$ cd ~/lessons
# Create a new working project directory and navigate into it
$ mkdir practice
$ cd practice
# grab the manifest from github and use the "main" branch
$ repo init -u https://github.com/the-Hammers-Company/cfs-manifest.git -b main
# Fetch the git repositories from the manifeest
$ repo sync
```
At this point you can run the cFS CMake tool and build a running image of the flight software.  If you don't bother to run the "repo start" instruction, you can still either (1) navigate directly to a repository and use command-line git to check out branches, make commits, do pushes, and so on, or you can (2) add a temporary local repository entry to your favorite GUI-based git software and manage the repo graphically.
Just remember to push your changes and pull them to any "permanent" local repositories you might have.

