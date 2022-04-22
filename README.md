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

Note:
Customise the following variables as required:
  - CA_PRVKEY_FILE          ## Path of Private Key file of CA 
  - CA_CSR_FILE             ## Path of Certificate Service Request file 
  - CA_CERT_FILE            ## Path of CA Certificate
  - APP_PRVKEY_FILE         ## Path of Private key file to Application/Nginx
  - APP_CSR_FILE            ## Path of Certificate Service Request file for application
  - APP_CERT_FILE           ## Path of Application Certificate 
  - HOST_IP                 ## IP address of Nginx host
  - DNS_NAME                ## Domain Name for which the certificate is to be produced
  - SUBJ_ALT                ## Subject Alternative - provide IP address & DNS name
  - NEXUS_URL               ## URL to be redirected to
