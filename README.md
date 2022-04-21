# Ansible_playbooks
To install Nexus:
   Pass the extra variables in vars folder and sample ansible command to run playbook
        
         ansible-playbook -v -i inventory.yml playbook.yml 

To create repos in nexus:
   Pass extra varaibles in vars folder.
    If need to create only maven hosted repo with release version type, update the vars/main.yml file as below 
    
       ---
       nexus_url: 34.121.46.70
       create_docker_hosted: 'no'
       docker_hosted_repo_name: myapp_docker_hosted

       create_maven_hosted: 'yes'
       maven_hosted_repo_name: myapp_maven_hosted
       maven_hosted_versionType: RELEASE

       create_maven_proxy: 'no'
       maven_proxy_repo_name: myapp_maven_proxy
       maven_proxy_remote_url: https://repo1.maven.org/maven2/
   
  Sample ansible command to run playbook
  
       ansible-playbook -v -i inventory.yml playbook_nexusrepo_creation.yml
