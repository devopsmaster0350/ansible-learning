### Ansible Regular commands

* To list the all configurations
```
  ansible-config list
  ansible-config show # to show the current configuration file
  ansible-config dump # To show current settings  
```
* command to check wether ansible control node able to connect the remote machines or not
```
   ansible -i inventory.yaml all -m ping
   ansible -i inventory.yaml all -m setup # to list the facts of all remote machines specified in inventory file
```
* Commands to check syntax,lint and dry-run of a playbook
```
   ansible-playbook -i inventory.yaml playbook.yaml --syntax-check # to check the syntax of playbook
   ansible-playbook -i inventory.yaml playbook.yaml --check # it will do a dry-run
   ansible-lint playbbok.yaml # ansible-lint is a tool used to analyze and enforce best practices in Ansible playbooks, roles, and tasks. It helps detect syntax errors, inefficiencies, and security risks before execution.
```
* `--diff`: The --diff option in Ansible is used to show the changes made to files and templates before and after execution. It helps in debugging and verifying modifications.
  ```
   ansible -i inventory.yaml all playbook.yaml --diff
   ansible -i inventory.yaml all playbook.yaml --check --diff # we can use this with --check also
  ```
* how to pass configuration file from command line, this is explicitly passing configuration.
```
   ANSIBLE_CONFIG=/opt/ansible.cfg ansible-playbook platbook.yaml
```
* How to pass variables form command line
```
  ansible-playbook playbook.yml -e "variable_name=value"
  ansible-playbook playbook.yml --extra-vars "variable_name=value"
  ansible-playbook playbook.yml -e "var1=value1 var2=value2"
```
### ansible Roles
* ansible roles commands
  ```
    ansible-galaxy list # list the installed roles
    ansible-galaxy role install mysql # To install a role form ansible-galaxy
    ansible-galaxy search mysql # To search a role in ansible-galaxy
    ansible-galaxy remove mysql # To uninstall the role
    ansible-galaxy init <role_name> # To create the structure of role in your local
  
  ```
### Ansible Collections
* ansible collection commands
  ```
    ansible-galaxy collection list # list the installed collections
    ansible-galaxy collection install <collection_name> # To install a collection form ansible-galaxy
    ansible-galaxy collection search <collection_name> # To search a collection in ansible-galaxy
    ansible-galaxy collection remove <collection_name> # To uninstall the collection
    ansible-galaxy collection init <collection_name> # To create the structure of role in your local
  ```  
  
