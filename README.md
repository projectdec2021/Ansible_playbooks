# Ansible_playbooks


* Create User - nginx:

   ```
    ansible-playbook -vv cre_nginx.yaml --ask-vault-pass
    ```

Reads password from a vault file named  "my_vault.yml" and sets it to the user 'nginx' which is being created. The password for the vault is "password1". Need to enter it while running this playbook. If required, reset the passwod by using "rekey" command in "ansible-vault". 


* Install Nginx, Configure TLS certificate &  Redirect to Nexus url:

   ```
   ansible-playbook -vv revprxy.yaml
   ```
