Ansible Role for ZSH 
=========

This role:

- installs zsh
- installs oh-my-zsh at ~{{ansible_ssh_user}}/.oh-my-zsh
- backs up existing ~/.zshrc
- backs up existing ~/.zsh_aliases 
- copies [my .zshrc](https://raw.github.com/ChengLong/configs/master/.zshrc) to ~{{ansible_ssh_user}}/.zshrc 
- copies [my .zsh_aliases](https://raw.github.com/ChengLong/configs/master/.zsh_aliases) to ~{{ansible_ssh_user}}/.zsh_aliases 
- copies [my pygmalion.zsh-theme](https://raw.github.com/ChengLong/configs/master/pygmalion.zsh-theme) to ~{{ansible_ssh_user}}/.oh-my-zsh/themes/pygmalion.zsh-theme
- changes the shell of {{ansible_ssh_user}} to zsh

This role works for both OSX and Debian based OS.

Requirements
------------

Note that this role requires sudo to `Install zsh` and change shell to `zsh`.
Please make sure that the user that your control machine ssh into has *sudo access*. I recommend using `ansible_ssh_user` in your inventory file, e.g. 

```
[test]
xxx.xxx.xxx.xxx ansible_ssh_user=exampleuser 
```

You can use `--ask-sudo-pass` when running your playbook

`ansible-playbook playbook.yml -i inventory.ini --ask-sudo-pass`

If you are provisioning OSX, you need to have `homebrew`.

Role Variables
--------------

NONE

Example Playbook
----------------

```
- hosts: servers
  roles:
    - role: ChengLong.zsh
```

License
-------

[WTFPL](http://www.wtfpl.net/)

Author Information
------------------

[Cheng Long](https://twitter.com/ChengLong_)
