# Installing pyenv on WSL
Instructions based on [this](https://www.techtronic.us/install-python-pyenv-on-wsl-ubuntu/) blog post.

## Step 1: Install dependencies

```
sudo apt-get update
```

```
sudo apt-get install git gcc make openssl libssl-dev libbz2-dev libreadline-dev libsqlite3-dev zlib1g-dev libncursesw5-dev libgdbm-dev libc6-dev zlib1g-dev libsqlite3-dev tk-dev libssl-dev openssl libffi-dev
```

### Key errors? 

If you encounter errors like this: 
```
W: GPG error: http://archive.ubuntu.com trusty-updates Release: The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 40976EAF437D05B5 NO_PUBKEY 3B4FE6ACC0B21F32
```

You can update the specified key from the ubuntu keyserver (in this case `40976EAF437D05B5`):

```
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 40976EAF437D05B5
```

[source](https://chrisjean.com/fix-apt-get-update-the-following-signatures-couldnt-be-verified-because-the-public-key-is-not-available/)

## Step 2: Install pyenv

```
curl https://pyenv.run | bash
```

## Step 3: Update config

add this to your .bashrc or .zshrc:

```
export PATH="/home/USERNAME/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```

## Step 4: reload config

```
source ~/.bashrc
```

or 

```
source ~/.zshrc
```

After installing pipenv, you can [update your repo's vscode config](../ide/vscode/pipenv-python-interpreter.md) to use the appropriate python interpreter.
