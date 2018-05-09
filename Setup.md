

## Setup

### Global configuration

terminal config
```sh
git config --global user.name "tomandjerryfun"
git config --global user.email "tomandjerrysco@gmail.com"
git config --global core.autocrlf
```

###  Generating a new SSH key

```sh
ssh-keygen -t rsa -b 4096 -C "tomandjerrysco@gmail.com"
```

Start the ssh-agent in the background.
```sh
eval "$(ssh-agent -s)"
```

Add your SSH private key to the ssh-agent.
```sh
ssh-add ~/.ssh/id_rsa
```

### Adding a new SSH key to your GitHub account

Copy the SSH key to your clipboard.
```sh
sudo apt-get install xclip
xclip -sel clip < ~/.ssh/id_rsa.pub
```

1. In the upper-right corner of any page, click your profile photo, then click __Settings__. 
2. In the user settings sidebar, __click SSH and GPG keys__.
3. Click __New SSH key__ or __Add SSH key__.
4. In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal Mac, you might call this key "Personal MacBook Air".
5. Paste your key into the "Key" field.
6. Click __Add SSH key__.
7. If prompted, confirm your GitHub password.


## Usage

### Create a repo

1. In the upper-right corner of any page, click `+`, and then click __New repository__.
2. Type a short, memorable name for your repository. For example, "hello-world".
3. Optionally, add a description of your repository. For example, "My first repository on GitHub."
4. Choose between creating a public or private repository.

*   __Public__ repositories are a great choice for getting started. They're visible to any user on GitHub, so you can benefit from a collaborative community.
*   __Private__ repositories are only available for paid accounts. For more information, see "GitHub's billing plans."

5. Select __Initialize this repository with a README__.
6. Click __Create repository__.

### Fork A Repo

Keep your fork synced. The original tutorial can be found [here](https://help.github.com/articles/fork-a-repo/).

#### Create a local clone of your fork.

1. On GitHub, navigate to __your fork__ of the Spoon-Knife repository.
2. Under the repository name, click __Clone or download__.
3. In the Clone with HTTPs section, click to copy the clone URL for the repository.
4. Open Terminal.
5. Type `git clone`, and then paste the URL you copied in Step 2. It will look like this, with your GitHub username instead of `YOUR-USERNAME`:
```sh
git clone https://github.com/YOUR-USERNAME/Spoon-Knife
```
6. Press __Enter__. Your local clone will be created.

####  Configure Git to sync your fork with the original Spoon-Knife repository.

1. On GitHub, navigate to the `octocat/Spoon-Knife`repository.
2. Under the repository name, click __Clone or download__.
3. In the Clone with HTTPs section, click to copy the clone URL for the repository.
4. Open Terminal.
5. Change directories to the location of the fork you cloned in _Step 2: Create a local clone of your fork.

*   To go to your home directory, type just `cd` with no other text.
*   To list the files and folders in your current directory, type `ls`.
*   To go into one of your listed directories, type `cd your_listed_directory`.
*   To go up one directory, type `cd ...`

6. Type `git remote -v` and press __Enter__. You'll see the current configured remote repository for your fork.
7. Type `git remote add upstream`, and then paste the URL you copied in Step 2 and press __Enter__. It will look like this:
```sh
git remove add upstream https://github.com/octocat/Spoon-Knife.git
```
8. To verify the new upstream repository you've specified for your fork, type `git remote -v` again. You should see the URL for your fork as `origin`, and the URL for the original repository as `upstream`.


