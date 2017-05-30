[![English](http://upload.wikimedia.org/wikipedia/commons/e/e1/Union_Jack_22x16.png "English")](README.md)
<h1>
  <span>Rôle Ansible pour HP iLo</span>
  <a href='http://ansible_role_iLo.readthedocs.io/en/latest/?badge=latest'>
    <img src='https://readthedocs.org/projects/ansible_role_iLo/badge/?version=latest' alt='Documentation Status' />
  </a>
</h1>

Object
======
L'objectif est de mettre en place un rôle Ansible pour le changement des mots de passe HP iLo

Context
=======
Avec les évenements récents concernant les cyber-attaques, nous nous devons de mettre en place tous les moyens à notre dispositions pour durcir les serveurs de nos clients.

## Role Variables
Vous devez paramétrer les variables pour l'emplacement des binaires hponcfg/ipmitool

```yml
---
hp_bin: /sbin/hponcfg
oracle_bin: /usr/bin/ipmitool
```

## Example Playbook


```yml
---
- hosts: all
  become_method: sudo
  vars_files:
    - secrets/yourfile.secrets.yml
  vars:
    passwdHPiLo: "{{ vault_HP_ilo_hpadmin_pwd }}"
    passwdORACLEiLo: "{{ vault_ORACLE_ilo_admin_pwd }}"
  roles:
     - {role: iLo , tags: iLo-change }
```


## Information sur l'auteur
Made with passion by Jérémie CUADRADO [Linkedin](http://lnked.in/jcua)

## Url vers la documentation complète en anglais...
[Full documentation](http://ansible_role_iLo.readthedocs.io/en/latest/)

[![](https://hydra-media.cursecdn.com/bukkit.gamepedia.com/4/4d/AGPL_icon.png "")](LICENSE)