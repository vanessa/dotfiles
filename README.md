# Vanessa's dotfiles

Made with [Ansible](https://www.ansible.com/) for [`Ubuntu 18.04 LTS`](http://releases.ubuntu.com/18.04/) (bionic). Must be used locally.

## Using

1. Set up SSH in your account (follow [this tutorial](https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) to create a key and [this tutorial](https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account) to add it to your GitHub account)
1. Clone this repository into `~/.dotfiles/`

    ```bash
    $ git clone git@github.com:vanessa/dotfiles.git ~/.dotfiles/
    ```
1. Go to the directory and create and configure the local variables:

    ```bash
    $ cd .dotfiles
    $ cp group_vars/local.example group_vars/local
    $ nano group_vars/local # or vim group_vars/local
    ```
1. Make sure your SSH private and public keys exist (`id_rsa` and `id_rsa.pub`). You should have because you executed the first step of this checklist. Check if they exist with:

    ```bash
    $ ls ~/.ssh | grep id_rsa
    # Make sure id_rsa and id_rsa.pub show on the output
    ```
1. Execute the `run.sh` file:

    ```bash
    # This will install ansible 2.5.2 if it's not installed;
    # Arguments to the ansible-playbook command can be passed here like: ./run.sh --tags=vscode
    ./run.sh
    ```
