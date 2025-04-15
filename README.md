# rancher
Rancher-Setup-Ubuntu


Running Rancher Kubernetes Cluster Management on Ubuntu Server
Installing Docker and Running Rancher
1. Log into the Ubuntu server
   
   
2. Run the following commands
# install docker
curl https://releases.rancher.com/install-docker/19.03.sh | sh 
# add the current user to the docker group
sudo usermod -aG docker $USER
# reauthenticate for the new group membership to take effect
su - $USER
# verify docker is installed and working
docker version
# run rancher container
docker run -d --restart=unless-stopped -p 80:80 -p 443:443 -v /opt/rancher:/var/lib/rancher --privileged rancher/rancher:latest


3. Open a web browser and navigate to the https://DNSorIP

  
4. Accept the certificate warning

   
5. When Rancher loads, enter an admin password and re-type to confirm
   
6. Select the I'm only going to use the cluster Rancher was installed on option
     
Click Continue
Welcome to Rancher
Congratulations, you now have a web based UI to deploy and manage docker containers
https://rancher.com/docs/rancher/v2.x/en/best-practices/v2.5/rancher-server/deployment-types/




->Find Your Host IP Address (Ubuntu Machine)
 ip a

->Find the Ubuntu Host’s LAN IP Address
ip a | grep inet

EXAMP: inet 192.168.1.100/24 brd 192.168.1.255 scope global dynamic ens33

->Check Which Ports Rancher Is Using
 docker ps

 example:
 CONTAINER ID   IMAGE                    PORTS
a1b2c3d4e5f6   rancher/rancher:latest   0.0.0.0:8443->443/tcp

->Access Rancher in Your Browser
https://<ubuntu-host-ip>:8443

https://192.168.1.100:8443 or
https://192.168.1.100:8080




 
