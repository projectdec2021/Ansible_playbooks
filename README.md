# Ansible_playbooks


* Create User - nginx:

   ```
    ansible-playbook -v cre_nginx.yaml --ask-vault-pass
    ```

Reads password from a vault file named  "my_vault.yml" and sets it to the user 'nginx' which is being created. The password for the vault is "password1". Need to enter it while running this playbook. If required, reset the passwod by using "rekey" command in "ansible-vault". 

Note:

Edit the variable "client_pubkey" to pass the value of the path of public key on Ansible controller or client. 


* Install Nginx, Configure TLS certificate &  Redirect to Nexus url:

   ```
   ansible-playbook -v revprxy.yaml
   ```
