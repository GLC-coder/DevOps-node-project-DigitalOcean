# Node Projects Management deployed on DigitalOcean

Node-Projects-Management URL:http://159.223.68.233:3000

Create an server and deploy the application which developed in HTML, CSS, and Node on DigitalOcean.

## Technologies used:

DigitalOcean, Linux, npm, HTML, CSS

## Project Description :

1- Setup and configure a server on DigitalOcean.

2- Configure SSH on the firewall for the server.

3- Create and configure a new Linux user on the Droplet for best security practice.

4- Deploy and run a Node application on the Droplet.

## Run and test app locally

#Install the dependencies

```
npm install
```

#Start the app locally

```
npm start
```

#Test the app locally

```
npm run test"
```

## Instructions;

### Step 1 :

1- Sign up / sign in an account on the DigitalOcean and configure SSH keys.

2- Create a Droplet for Node projects management with Linux Ubuntu distribution in Singapore Region by configuring the authentication method with SSH Key instead of Password.

3- Turn on the firewall for the server and configure the SSH with port 22 and specific ip address for Inbound traffics.

### Step 3 : Prepare the server and create a new Linux user by root user

#ssh into the newly created server by root user

```
ssh -i .ssh/id_rsa root@159.223.68.233
```

#Create a new Linux user and

```
adduser jason
```

#Assign the new user with the root user privileges.

```
usermod -aG sudo jason
```

#Switch to the new Linux user account

```
su - jason
```

#Create a ".ssh" folder under the current user directory

```
mkdir .ssh
```

#Copy and paste the public key into authorized_keys file under the .ssh folder

```
sudo vim .ssh/authorized_keys
```

#log out the server

```
exit
```

```
exit
```

### Step 5 : Login, Configure and manage the server by new Linux user

#Login server using new Linux user: jason via ssh

```
ssh -i .ssh/id_rsa jason@159.223.68.233
```

### Step 6 : Install node.js and npm on server

```
apt install -y nodejs npm
```

### Step 7 : Package the node app and copy the app

#package the node app

```
npm pack
```

#Copy the node app to the server

```
scp -i .ssh/id_rsa bootcamp-node-project-1.0.0.tgz jason@159.223.68.233:~/
```

### Step 8 : Run the Node App

#unpack the node-project file

```
tar zxvf bootcamp-node-project-1.0.0.tgz
```

![image](https://github.com/GLC-coder/DevOps-node-project-DigitalOcean/blob/master/images/readme-img/Screenshot%202023-01-26%20at%2011.49.21%20pm.png)

#Change into unpacked directory code package

```
cd package
```

#Install the dependencies for the Node App

```
npm install
```

#Run the application

Attached mode

```
node server.js
```

or

Detached mode

```
node server.js &
```

#Get the current running processes info, including the Port and process ID/PID

```
netstat -lpnt
```

![image](https://github.com/GLC-coder/DevOps-node-project-DigitalOcean/blob/master/images/readme-img/Screenshot%202023-01-26%20at%2011.57.20%20pm.png)

#Stop run the Java-React App from the detached mode

```
kill <PID>
```

![image](https://github.com/GLC-coder/DevOps-node-project-DigitalOcean/blob/master/images/readme-img/Screenshot%202023-01-26%20at%2011.57.32%20pm.png)

### Step 9 : Update the firewall rules

#1-Update the firewall rules with the server listening port number: 3000 for all ip address in inbound traffic.
![image](https://github.com/GLC-coder/DevOps-node-project-DigitalOcean/blob/master/images/readme-img/Screenshot%202023-01-26%20at%2011.33.34%20pm.png)

![image](https://github.com/GLC-coder/DevOps-node-project-DigitalOcean/blob/master/images/readme-img/Screenshot%202023-01-26%20at%2011.56.25%20pm.png)

### Step 10 :Visit the Node App with the public ipv4 and port number of the server.

URL:http://159.223.68.233:3000
![image](https://github.com/GLC-coder/DevOps-node-project-DigitalOcean/blob/master/images/readme-img/Screenshot%202023-01-26%20at%2011.58.10%20pm.png)
