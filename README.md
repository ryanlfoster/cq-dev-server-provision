<h3>GOAL</h3>
Provision a cq dev server with the following software pre-installed

  Java OpenJDK <br>
  Tomcat Latest<br>
  Git<br>
  SVN Client<br>
  SVN Server<br>
  OpenLDAP<br>
  Nexus<br>
  and last but not least CQ<br>
  
  This project uses Chef Solo to do the provisioning. Currently onlu Ubuntu 12.04 and CentOS 6 are supported
  which at the time of developemnt are the latest LTS versions of the respective OSs.<br>

The bootstrap script for ubuntu is modified from the following gist:<br>
https://gist.github.com/chrismdp/1026628

For bootstraping CentOS 6, use:


<h3>Prerequisites</h3>
Its assumed that you have access to a barebones server and the server can connect to the internet.
Also, if you plan to use github repository to do the server build, Github requires you to authenticate with them. So you would first need to request to add your public SSH key to the github to be able to clone this repository. If you need steps to generate SSH keys on the barebones Linux server, here are the steps: <br>
https://help.github.com/articles/generating-ssh-keys

After the ssh key is added, just copy the bootstrap script,(For bootstapping Ubuntu 12.04, use:
bootstrap_chef.sh and For CentOS Use:  ) to the home folder of the user and run it.

You will have to set execute flags on the file. e.g. chmod 755 bootstrap_chef.sh

This would update and install all the nessesary software. The script would need you to confirm adding github.com to known hosts list. After the script is done executing succesfully it will print a chef-solo command to run. Please copy and paste that command in the terminal.

You can verify that the tomcat is running by accessing it at http://<code>ip-address</code>:8080/
