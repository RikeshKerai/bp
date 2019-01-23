BP

Tasks
- Spin up a Linux Vagrant box of your choice
- Configure Vagrant to use Ansible as the provisioner
- Configure the box with an IP address available to the hosting OS
- Write playbook/playbooks to:
  i.   Install and start docker
  ii.  Build a docker container based on the official Alpine Linux container (library/alpine:latest)
  iii. Build the container so that nginx is installed and started
  iv.  Configure nginx to serve out some static “Hello World” content
  v.   Start the container as a micro service
  vi. At the end of the provisioning the URL to the web page should be available from the hosting OS
  vii. Write appropriate documentation in the repository to explain how someone cloning it should provision the Vagrant VM and access the web URL serving out the “Hello World”


Prerequisites

- Install vagrant
- Setup vagrant networking:
  i. Select vagrant instance from the vagrant ui
  ii. select settings>network>nat>advanced
  iii. change tcp host port to 8888 and tcp guest port to 8080

HOWTO
- git clone https://github.com/RikeshKerai/bp.git
- cd bp
- vagrant status
- vagrant up
- open browser eg. chrome/safari/ie
- enter into browser http://localhost:8888/

RESULT
- Hello World
