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
  - CA_PRVKEY_FILE                           ## Path of Private Key file of CA 
  - CA_CSR_FILE: /root/CA.csr                ## Path of Certificate Service Request file 
  - CA_CERT_FILE: /root/CA.crt               ## Path of CA Certificate
  - APP_PRVKEY_FILE: /root/app_key.pem       ## Path of Private key file to Application/Nginx
  - APP_CSR_FILE: /root/app.csr              ## Path of Certificate Service Request file for application
  - APP_CERT_FILE: /root/app.crt             ## Path of Application Certificate 
  - HOST_IP: "34.148.84.22"                  ## IP address of Nginx host
  - DNS_NAME: mydom.in                       ## Domain Name for which the certificate is to be produced
  - SUBJ_ALT: 'IP:34.148.84.22,DNS:mydom.in' ## Subject Alternative - provide IP address & DNS name
  - NEXUS_URL: http://10.128.0.18:8081       ## URL to be redirected to
