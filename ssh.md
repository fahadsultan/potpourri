
<img src="https://cdn-icons-png.flaticon.com/512/5261/5261911.png" width="20%" align="right">

# Secure Shell (SSH)

Just as HTTP is a protocol for unencrypted web traffic and HTTPS is a protocol for encrypted web traffic, SSH is a protocol for encrypted remote login and other secure network services.

Using the SSH protocol, you can connect and authenticate to remote servers and services.

In simple words, you can use SSH to access another computer over a network and execute commands on the other computer. All of this takes place in the command line, without needing a graphical interface. This is how most servers are administered. 

## SSH Keys

SSH keys are a way to identify trusted computers and communicate with them without involving passwords.

SSH keys are two files that are generated together: a public key and a private key. The private key is kept on the computer you log in from, while the public key is shared with all the computers you want to log  communicate with.

``` {warning}
Never share or upload your private SSH key! 
```

<img align="center" width="70%" src="assets/ssh.png">


### Check if you already have an SSH key

If you want to check if you already have an SSH key, you can use the following command:

```bash
ls -al ~/.ssh
```

`ls`: prints the contents of a directory
`-a`: list all files in long format
`-l`: use a long listing format
`~/.ssh`: path to the ssh folder
`~`: home directory
`.ssh`: hidden ssh folder in your home directory

If you see a file named `id_rsa.pub`, you already have an SSH key pair and you can skip the next step.

The filename ending with `.pub` is your public key. The other file is the corresponding private key. If you don't have these files (or you don't even have a `.ssh` directory), you need to create them.

### Generate a new SSH key, if needed

SSH keys are generated using a command line tool called `ssh-keygen`. This tool is installed by default on most systems.

```bash

ssh-keygen -t ed25519 -C "your_email@example.com"
    
```

`-t`: the type of encryption to use

`ed25519`: the encryption type

`-C`: comment to help you identify the key

Try the `ls -al ~/.ssh` command again to see your new SSH key.

### Copy the SSH key to your clipboard



````{tab-set}
```{tab-item} Mac
```bash
pbcopy < ~/.ssh/id_rsa.pub
```

```{tab-item} Windows
```bash
clip < ~/.ssh/id_rsa.pub
```

````

Now you can paste your public ssh key on the website you want to use it on.
