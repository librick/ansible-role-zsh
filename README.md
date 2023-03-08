# Ansible Role: ZSH
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit)](https://github.com/pre-commit/pre-commit)

This role installs and customizes ZSH and [Oh My Zsh](https://ohmyz.sh/) on Debian-based Linux systems. It:
 - Ensures that ZSH is installed
 - Ensures that ZSH is the default shell for a provided user
 - Ensures that Oh My Zsh is installed for a provided user
 - Ensures that Oh My Zsh is configured for a provided user

## Role Variables
See [defaults/main.yml](./defaults/main.yml) for a comprehensive list of role variables.  
Some of the most pertinent variables are:
- `zsh_user`
- `zsh_xdg_config_home`  
- `zsh_xdg_data_home`  
- `zsh_zdotdir`

## Testing
Testing is performed using Molecule.  
See the [molecule](./molecule/) directory for more information.

## Linting
Linting is done automatically via [https://pre-commit.com/](https://pre-commit.com/).  
After setting up a virtual environment and installing `requirements.txt`, run  
`pre-commit run --all-files`  
See: https://github.com/ansible/ansible-lint  
See: https://github.com/pre-commit/pre-commit

## Example Playbook
    - hosts: servers
      vars_files:
        - vars/main.yml
      roles:
        - librick.flatpak

*Inside `vars/main.yml`*:

    zsh_user: johndoe
    zsh_xdg_config_home: "/home/{{ zsh_user }}/.config"
    zsh_xdg_data_home: "/home/{{ zsh_user }}/.local/share"  
    zsh_zdotdir: "{{ zsh_xdg_config_home }}/zsh"


## License

MIT Licensed

## Author Information

This role was created in 2023 by [Eric McDonald](https://juniperspring.xyz/).
