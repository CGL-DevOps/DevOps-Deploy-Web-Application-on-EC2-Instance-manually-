### Deploy Web Application on EC2 Instance (manually)

### Technological Used:

AWS, Docker, Linux, React, NodeJS

### Project Description:

1- Create and configure an EC2 Instance on AWS.

2- Install Docker on remote EC2 Instance.

3- Deploy Docker image from private Docker repository on EC2 Instance.

### Usage Instructions:

###### Step 1: Create and configure an EC2 Instance on AWS.

![image](image/Screenshot%202023-02-25%20at%2011.39.21%20pm.png)
![image](image/Screenshot%202023-02-25%20at%2011.13.57%20pm.png)
![image](image/Screenshot%202023-02-25%20at%2011.17.46%20pm.png)
![image](image/Screenshot%202023-02-25%20at%2011.18.01%20pm.png)
![image](image/Screenshot%202023-02-25%20at%2011.20.51%20pm.png)
![image](image/Screenshot%202023-02-25%20at%2011.24.08%20pm.png)
![image](image/Screenshot%202023-02-25%20at%2011.28.08%20pm.png)
![image](image/Screenshot%202023-02-25%20at%2011.26.38%20pm.png)
![image](image/Screenshot%202023-02-25%20at%2011.43.50%20pm.png)

###### Step 2: Install Docker on remote EC2 Instance

1- Configure the .pem file and change its permissions
![image](image/Screenshot%202023-02-25%20at%2011.50.29%20pm.png)
2- Login the EC2 Instance as ec2-user via ssh
![image](image/Screenshot%202023-02-25%20at%2011.55.44%20pm.png)
3- Check current user

```
whoami
```

4- Update the YUM package manager tool.

```
sudo yum update
```

5- install docker as sudo user

```
sudo yum install
```

6- start the Docker Deamon

```
sudo service docker start
```

7.1- Add current user: ec2-user into docker group

```
sudo usermod -aG docker $USER
```

![image](image/Screenshot%202023-02-26%20at%2012.17.46%20am.png)
or

7.2- Add current user: ec2-user into sudo group

```
sudo usermod -aG sudo $USER
```

8- Exit from EC2 Instance and login again

```
exit
```

```
ssh -i ~/.ssh/ec2-docker-server.pem ec2-user@3.25.180.251
```

9- check groups

```
groups
```

###### Step 3: Deploy Docker image from private Docker repository on EC2 Instance

1- docker login docker hub private repository

```
docker login
```

![image](image/Screenshot%202023-02-26%20at%2012.53.22%20am.png)

2- Run React-node-app image from private repository

![image](image/Screenshot%202023-02-26%20at%202.54.19%20am.png)

3- Check web running status
![image](image/Screenshot%202023-02-26%20at%202.54.26%20am.png)
4- Update the security group for inbound
![image](image//Screenshot%202023-02-26%20at%202.58.07%20am.png)
![image](image/Screenshot%202023-02-26%20at%202.58.28%20am.png)
![image](image/Screenshot%202023-02-26%20at%202.58.45%20am.png)

5- Open the web app in browser
![image](image/Screenshot%202023-02-26%20at%202.59.35%20am.png)
