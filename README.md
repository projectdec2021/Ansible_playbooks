# Ansible_playbooks
To install Nexus:
   Pass the extra variables in vars folder and sample ansible command to run playbook
        
         ansible-playbook -v -i inventory.yml playbook.yml 

To create repos in nexus:
   Pass extra varaibles in vars folder.
    If need to create maven hosted repo with release version type, update the vars/main.yml file as below 
    
       create_maven_hosted: 'yes'
       maven_hosted_repo_name: repo_name
       maven_hosted_versionType: RELEASE
   
  Sample ansible command to run playbook
  
       ansible-playbook -v -i inventory.yml playbook_nexusrepo_creation.yml
