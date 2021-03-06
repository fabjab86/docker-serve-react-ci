### *work in progress

This project was produced in a joint pairing between <a href="https://github.com/Benjamin-Tomkins">myself</a> and <a href="https://github.com/fabjab86">Farah Jabri</a>, to explore continuous integration and TDD scenarios for deploying ReactJS projects.

The Sample project in this repo is to test setting up a boilerplate React App with a continuous integration build, triggered on updating the master branch. The code is then pulled to its associated <a href="https://cloud.docker.com/repository/docker/glossyfly/mismocodes">docker repo</a>, where it'll build a deployable node/serve docker container (upon passing all tests).
The successfully built image can then be pulled onto the deployment server and run.

This sample is currently running live on a <a href="https://www.digitalocean.com/">DigitalOcean</a> docker droplet at the following address:

http://178.128.170.149/


How to use locally
==================

From the commad line `docker build -t <username>/<projectname>:latest .`  
Once completed `docker push <username>/<projectname>:latest`   
To run the project `docker run -it -d --rm -p 80:5000 <username>/<projectname>`  
Go to `localhost` in your browser to view the project  

### To stop running the project  
Type `docker ps`  
Copy the `<CONTAINER ID>`  
Type `docker stop <CONTAINER ID>`  

## Why digitial oceans

It is a vertual private server  
Multiple pricing plans that you switch between any time  
Provides SSD for preformance  
To use any other provider all you need is ubunto 16.04 and root SSH  

### Creating a droplet   

> A digital ocean droplet is a vertual server  

  
- [ ] On the top right section of the website click Create 
- [ ] Droplets 
- [ ] Go to the One-click-apps 
- [ ] Docker 18.xx on 18.xx 
- [ ] Scroll down to select size of the droplet 
- [ ] Select the data centre region which is below it 
- [ ] Get your SSH public key (below) 
- [ ] Click on New SSH key 
- [ ] Paste the copied public SSH key 
- [ ] _Make sure to remove any white space after the last charachter of your public SSH key_ 
- [ ] Name your SSH public key 
- [ ] Click Add SSH key 
- [ ] Hover over the SSH public key to check that it has been added correctly 
- [ ] Select how many droplets you want 
- [ ] Chose a host name 
- [ ] Click on the create button 

### To get your SSH Key

In your terminal `cd ~/.ssh`  
Type `cat id_rsa.pub` to get your SSH public key  
Copy the SSH public key  


### Connecting to the droplet
In your termial type `ssh root@<droplet IP address>` which can be found on the right hand side of your droplet    
You will get a message to verify the connection to the server 
Type `yes`  
Type `docker run -it -d --rm -p 80:5000 <username>/<projectname>`  
Paste your droplet <IP> address in your browser to see your project live  
  <b> If you want to stop the docker container type `docker stop <CONTAINER ID>` </b>  
    
### To log out of the droplet 

Type `exit` in the command line 
  

### Continous integration

docker-compose.test.yml 
system under tests (SUT) 

