# Setup key
Generate SSH for user:
`cd ~/.ssh` -> `ssh-keygen -t rsa -C "<email>"`
**NAME IT SOMETHING UNIQUE TO NOT OVERWRITE**

Then run:
`ssh-add ~/.ssh/<key>`

# Add to Github
Login to Github and go to setting/SSH and GPG keys, and add a new SSH key.
Name the key something that makes sense and insert the public key you just created.

To get the public key:
`code ~/.ssh/<key>.pub` and copy from there.

# Repos
Go to the repo and `git remote set-url --push origin 'git@<host>:<username>/<repo>.git'`

`<host>` is the `Host` from config `~/.ssh/config`

# Config
Add a host to the `~/.ssh/config`, current:
```
Host github.com
	HostName github.com
	User git
	IdentityFile ~/.ssh/personal_git

Host github.com-sdu
	HostName github.com
	User git
	IdentityFile ~/.ssh/sdu_git
```