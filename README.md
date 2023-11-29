# website
Integration of Devops tools with Jenkins

Following are the specifications of the Continuous integration:
1. Git Workflow hasto be implemented
2. Code Build should automatically be triggered once commit is made to master branch 
or develop branch.
If commit is made to master branch, build and publish website on 
port 82. If commit is made to develop branch, just build the 
product, do not publish.
3. Create a pipeline for the above tasks.
4. Create a container with Ubuntu and apache installed in it and use that container to
build the code and the code should be on ‘/var/www/html’

steps:
Create 3 EC2 instance -1 Master and 2 Slave
 
 
run below command sudo apt update
connect master node and install java17 ,Jenkins 
sudo apt update
sudo apt install fontconfig openjdk-17-jre
java -version

sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian/jenkins.io-2023.key
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins

5.connect in webbroswer= http://publicip:8080
6.install recommended plugins
7.set environment variable
export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64/
export PATH=$PATH:$JAVA_HOME/bin
8. Start Jenkins
sudo systemctl start jenkins
sudo systemctl status jenkins
sudo systemctl enable Jenkins
9.jenkins console -> tools -> install java jdk -add path and install maven -latest version and save.
 
 
==================================================================================
Add 2 nodes to Jenkins master
1.create passwordless ssh between Master and salve1 and slave2
2.open master node- run ssh-keygen -t rsa
3.cd ~/.ssh
4.copy id_rsa.pub and paste in slave nodes -authorized_keys
5.try to connect in master ssh public_ip(slave1 or slave2)
 
6.install java17 in slave 1 and slave2
7.open Jenkins console – create credentials
Dashboard-manage Jenkins – credentials – system -global credentials
In private key – paste from master id_rsa

8.add webhook in github project
 
9.Install docker in Machines
Create Nodes – slave1 and slave2
Nodes-new nodes
Slave1 node
 ![image](https://github.com/karthikravi123/website/assets/86100724/2d3b7a3f-638f-42bd-ae78-8a56ee40b254)
 ![image](https://github.com/karthikravi123/website/assets/86100724/539c3b33-5c8f-4853-ac06-0c3621f54324)
 
Slave2 node
![image](https://github.com/karthikravi123/website/assets/86100724/0ebb643f-9bf0-481f-aed2-a2169512ae4f)
![image](https://github.com/karthikravi123/website/assets/86100724/2bb89972-36f6-471e-b490-1a146a062d8c)


   
Finally nodes created
 
==================================================================================
create job1 and job2 for Master branch and develop branch
Dashboard-new item-create free style project
Master-branch
 ![image](https://github.com/karthikravi123/website/assets/86100724/2123e992-be90-4b2e-b142-1d0d231fd870)
![image](https://github.com/karthikravi123/website/assets/86100724/35bb708d-d2e4-412f-af34-b9318e7e7591)
![image](https://github.com/karthikravi123/website/assets/86100724/ce7f33cb-9e80-4ba6-8f93-62c5cbdd848f)
![image](https://github.com/karthikravi123/website/assets/86100724/90db5ff1-1d92-4cef-af4a-50bd289c09b8)
![image](https://github.com/karthikravi123/website/assets/86100724/3c113dff-a226-432f-918c-9d8260f4d967)
![image](https://github.com/karthikravi123/website/assets/86100724/e5de5fd9-dfb9-4f28-b6bf-541402365e75)

 
Develop branch
![image](https://github.com/karthikravi123/website/assets/86100724/8ceb0958-d730-44d7-8f2c-74a77cb3033e)
![image](https://github.com/karthikravi123/website/assets/86100724/935a70b4-8a33-42b1-894e-c2703d0a4052)
![image](https://github.com/karthikravi123/website/assets/86100724/c5097e60-2006-411f-8783-762c0719a332)
![image](https://github.com/karthikravi123/website/assets/86100724/c8dcabbf-dd01-4c7e-b162-21df21eca5f8).

![image](https://github.com/karthikravi123/website/assets/86100724/05d0595a-2ac2-4650-8bd7-3acafe9d3924)# website 





 
 
 
 
 

