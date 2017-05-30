[![Français](http://upload.wikimedia.org/wikipedia/commons/1/14/Flag_of_france.png "Française")](README-FR.md)

<h1>
  <span>Ansible role for HP iLo</span>
  <a href='http://ansible_role_iLo.rtfd.io/en/latest/?badge=latest'>
    <img src='https://readthedocs.org/projects/ansible_role_iLo/badge/?version=latest' alt='Documentation Status' />
  </a>
</h1>

## Object

The objective is to set up an Ansible role to change automaticly the HP iLo password.

## Context

With the recent cyber-attacks events, we have to put in place all the means at our disposal to harden the servers of our customers.

## Example Playbook


```yml
---
- hosts: all
  become_method: sudo
  vars_files:
    - secrets/{{site}}-secrets.yml
  vars:
    passwdHPiLo: "{{ vault_HP_ilo_hpadmin_pwd }}"
    passwdORACLEiLo: "{{ vault_ORACLE_ilo_admin_pwd }}"
  roles:
     - {role: iLo , tags: iLo-change }
```
## Author Information
Made with passion by Jérémie CUADRADO [Linkedin](https://fr.linkedin.com/in/jeremiecuadrado)


## Link to the readthedocs web page...
[Full documentation](http://ansible_role_iLo.readthedocs.io/en/latest/)

[![](https://hydra-media.cursecdn.com/bukkit.gamepedia.com/4/4d/AGPL_icon.png "")](LICENSE)