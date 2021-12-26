# Configuration of Apache WebServer and MYSQL

Build a Ansible Script with following items :-
- Ansible script should install and setup Apache.
- Ansible script should install and setup MYSQL.
- Ansible script should download the code from :-
https://github.com/django/django
- Ansible script should copy the above mentioned code at :-
/var/www/dmlabs/django
If location is not there on machine, then it should create location.

### Pre requisite

Ansible must be installed in controller node. There is no need of ansible in target node. Update the configuration file of ansible in controller node with the inventory file which contains IP address, user-name and password of Target Node.

## The Playbook


- ### **configuration.yml** 
  Install and setup Apache WebServer. Then it create the directory /var/www/dmlabs/django if it does not exist and then downloads the code form github repository. This Playbook also install and start the MYSQL service. 

- In **configuration.yml**, **package** module is used to install Apache WebServer. To start the service of Apache WebServer, **service** module is used. 
- To create the directory **file** module is used. To download the code from gihub **git** module is used and copied into the created directory.
- To install the MYSQL **package** module is used and to start the service, **service** module is used.


- ### **conf_var.yml** 
  Contains the variables for configuration.yml .




### Running the playbooks

Run the Playbook using following command-
- ansible-playbook configuration.yml
