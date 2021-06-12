# DevOps Project-2

![image](https://user-images.githubusercontent.com/47205003/121778114-13667b80-cbb3-11eb-9b32-141fce334665.png)

DevOps Project with GITHUB, AWS, Ansible

![image](https://user-images.githubusercontent.com/47205003/121778118-1e211080-cbb3-11eb-8abc-d9b360f615ec.png)

1.	Launch four Ec2 Instances in AWS: Developer, Jenkins, Ansible, Web

![image](https://user-images.githubusercontent.com/47205003/121778126-29743c00-cbb3-11eb-8324-b8f2df1a7fbf.png)

2.	Now ready your Jenkins Server in Putty: {Copy Public IP of Jenkins}:

![image](https://user-images.githubusercontent.com/47205003/121778131-34c76780-cbb3-11eb-86e1-1eedec84400a.png)

•	Install Java in this Server:
     
    yum install java* -y
    
    ![image](https://user-images.githubusercontent.com/47205003/121778166-5cb6cb00-cbb3-11eb-9817-3f390843dfaf.png)

 
    wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
  
    rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
 
 ![image](https://user-images.githubusercontent.com/47205003/121778173-63ddd900-cbb3-11eb-86a2-9fb05ab72a95.png)

    yum install jenkins
 
 ![image](https://user-images.githubusercontent.com/47205003/121778184-70623180-cbb3-11eb-88ce-ea62e195e347.png)

    systemctl start jenkins
    
    systemctl enable jenkins
 
 ![image](https://user-images.githubusercontent.com/47205003/121778193-82dc6b00-cbb3-11eb-8f43-6a3e9364e277.png)


• Copy Public IP of Jenkins and Run on Google: {for eg. 65.1.107.39:8080}

![image](https://user-images.githubusercontent.com/47205003/121778201-8b34a600-cbb3-11eb-9910-bb0e1451a882.png)

•	Copy /var/lib/jenkins/secrets/initialAdminPassword and run on Jenkins server by 
  
    cat /var/lib/jenkins/secrets/initialAdminPassword

![image](https://user-images.githubusercontent.com/47205003/121778210-a2739380-cbb3-11eb-9363-d133e89d1c90.png)

	Now copy output and paste on Jenkins administrator Password

•	Getting Started With Jenkins:

![image](https://user-images.githubusercontent.com/47205003/121778228-b4edcd00-cbb3-11eb-8c85-e2bf73f168e3.png)

•	Create First Admin User or Sign Up to Jenkins:

![image](https://user-images.githubusercontent.com/47205003/121778239-bf0fcb80-cbb3-11eb-87c9-791c725fb877.png)

3.	Now ready your Ansible Server in Putty: {Copy Public IP of Ansible}:

![image](https://user-images.githubusercontent.com/47205003/121778256-ccc55100-cbb3-11eb-9c21-99e5cb20feab.png)

    yum install ansible

![image](https://user-images.githubusercontent.com/47205003/121778271-dcdd3080-cbb3-11eb-95f4-d605c3e7892c.png)

    amazon-linux-extras install ansible2
    
  ![image](https://user-images.githubusercontent.com/47205003/121778290-ebc3e300-cbb3-11eb-8426-58de25beec80.png)

  •	vim /etc/ansible/hosts: (And Put Web server Private IP)  
  
 ![image](https://user-images.githubusercontent.com/47205003/121778309-f7170e80-cbb3-11eb-82d8-f1ef4c4bddab.png)

![image](https://user-images.githubusercontent.com/47205003/121778313-faaa9580-cbb3-11eb-8b1f-2f7d744788ad.png)

 4.	Now Setup Web_Server on PUTTY:{Copy Public IP of Web}

![image](https://user-images.githubusercontent.com/47205003/121778322-072eee00-cbb4-11eb-8fb2-1b6d2971786d.png)
  
    yum install httpd    
    
![image](https://user-images.githubusercontent.com/47205003/121778330-1150ec80-cbb4-11eb-866f-5460f46a8b93.png)

    systemctl start httpd
    systemctl enable httpd

![image](https://user-images.githubusercontent.com/47205003/121778341-1dd54500-cbb4-11eb-951b-b8fecf292b70.png)

    cd  /var/www/html
    
  ![image](https://user-images.githubusercontent.com/47205003/121778353-29287080-cbb4-11eb-9ec0-0f5c53870524.png)
   
  •	Now Connect Ansible Server with Web Server
  
   Go to Ansible Server and generate a Key: 
       
       ssh-keygen 
       
Then Press Enter 4 times
 
![image](https://user-images.githubusercontent.com/47205003/121778376-465d3f00-cbb4-11eb-8b6a-972a747472bd.png)

•	Now go to Web Server and create password for root

![image](https://user-images.githubusercontent.com/47205003/121778383-4cebb680-cbb4-11eb-85f9-e79bb405cef2.png)

•	Now in ssh configuration enable Root login and PASSWORD AUTHENTICATION yes

![image](https://user-images.githubusercontent.com/47205003/121778399-5aa13c00-cbb4-11eb-83e3-4a7b7047a590.png)

![image](https://user-images.githubusercontent.com/47205003/121778402-5d039600-cbb4-11eb-8827-a9cf2ee020d2.png)

![image](https://user-images.githubusercontent.com/47205003/121778406-60971d00-cbb4-11eb-9217-b4e5b0ea1c58.png)

    systemctl restart sshd
    
 •Now in Ansible Server 
 
   {ssh-copy-id –i root@(Private IP of Web)}
   {ssh root@( Private IP of Web)}
   
![image](https://user-images.githubusercontent.com/47205003/121778442-8b817100-cbb4-11eb-903a-951576f3b2b8.png)

	Exit


•   Now connect Ansible server with Jenkins server

   Go to jenkins server and generate a key
   
    ssh-keygen  

Then Press Enter 4 times

![image](https://user-images.githubusercontent.com/47205003/121778496-b53a9800-cbb4-11eb-9bc8-98dee51eb216.png)

•	Now go to Ansible Server and create password for root

![image](https://user-images.githubusercontent.com/47205003/121778573-19f5f280-cbb5-11eb-9627-9d15d39e9d4e.png)

•	Now in ssh configuration enable Root login and PASSWORD AUTHENTICATION yes

![image](https://user-images.githubusercontent.com/47205003/121778585-28dca500-cbb5-11eb-9ce5-661b576ae0f9.png)

![image](https://user-images.githubusercontent.com/47205003/121778587-2c702c00-cbb5-11eb-97d9-426ca8390115.png)

![image](https://user-images.githubusercontent.com/47205003/121778594-2f6b1c80-cbb5-11eb-8992-470259539691.png)

    systemctl restart sshd
    

•	Now in Jenkins Server

   ssh-copy-id –i root@(Private IP of Ansible)
   ssh root@( Private IP of Ansible)
   
   ![image](https://user-images.githubusercontent.com/47205003/121778618-4f024500-cbb5-11eb-987f-6ddee7c4f7f5.png)
	Exit
    
5.	Now in Ansible server

       mkdir /sourcecode
       cd /sourcecode
    ![image](https://user-images.githubusercontent.com/47205003/121778643-735e2180-cbb5-11eb-8201-803b6d5e2f73.png)

       vim playbook.yml   
       
       - hosts: all
             tasks:
              - copy:
                   src: /opt/index.html	
                   dest: /var/www/html
                   
     ![image](https://user-images.githubusercontent.com/47205003/121778685-9be61b80-cbb5-11eb-8391-9fde1c8fb132.png)
     
6.	Create a repository on GitHub

![image](https://user-images.githubusercontent.com/47205003/121778703-b5876300-cbb5-11eb-81db-6a4db3aaf2c5.png)

•	Now create File and NAME IT “index.html” and commit

![image](https://user-images.githubusercontent.com/47205003/121778708-c0da8e80-cbb5-11eb-88cf-5d64e8f82032.png)

•	Add a WEBHOOK to your repo

![image](https://user-images.githubusercontent.com/47205003/121778714-c932c980-cbb5-11eb-9058-5b1508ff8853.png)

   	Now to add secret go to Jenkins CLICK ON YOUR NAME->configure->add new token->generate-> Save and Apply->copy and paste in secret 

![image](https://user-images.githubusercontent.com/47205003/121778730-da7bd600-cbb5-11eb-87f8-30cfe4fe7c57.png)

•	Now Add webhook->Refresh

![image](https://user-images.githubusercontent.com/47205003/121778737-e5366b00-cbb5-11eb-8aa0-b64ca2e0cd2d.png)

NOTE: - INSTALL GIT ON JENKINS SERVER

    yum install git* -y
    
![image](https://user-images.githubusercontent.com/47205003/121778746-f54e4a80-cbb5-11eb-8fea-49a7d508e5da.png)

    yum install git
    
 ![image](https://user-images.githubusercontent.com/47205003/121778771-131baf80-cbb6-11eb-94b3-7107736087c9.png)
 
 •	Install “Publish Over SSH” plugin in jenkins
 
 7.	Now Create a New JOB “Project-1” a FreeStyle Project

![image](https://user-images.githubusercontent.com/47205003/121778776-1f077180-cbb6-11eb-90f9-ca58361fd40d.png)

Configuration

![image](https://user-images.githubusercontent.com/47205003/121778781-26c71600-cbb6-11eb-86f6-a165c7353952.png)

![image](https://user-images.githubusercontent.com/47205003/121778783-2af33380-cbb6-11eb-982e-d3bbfb430818.png)

	Now in Jenkins server create root password

        vim /etc/ssh/sshd_config
        
	Now in ssh configuration enable Root login and PASSWORD AUTHENTICATION yes

![image](https://user-images.githubusercontent.com/47205003/121778794-3e060380-cbb6-11eb-8b7e-05d67c8f534f.png)

![image](https://user-images.githubusercontent.com/47205003/121778836-6d1c7500-cbb6-11eb-8305-e9a901e9b3ef.png)
![image](https://user-images.githubusercontent.com/47205003/121778838-70affc00-cbb6-11eb-80fc-24db76a2cd16.png)
	systemctl restart sshd 

•	Now configure your servers in

SSH SERVER (BOTH ANSIBLE AND JENKINS)->Test Configuration for Both-> Save and APPLY

![image](https://user-images.githubusercontent.com/47205003/121778851-7f96ae80-cbb6-11eb-90c7-0351c2cb1e26.png)

![image](https://user-images.githubusercontent.com/47205003/121778854-82919f00-cbb6-11eb-86b3-4b14a990b4a4.png)

•	Now in Jenkins Server 

    cd /etc/lib/jenkins/
    ls
 ![image](https://user-images.githubusercontent.com/47205003/121778863-90dfbb00-cbb6-11eb-8657-16b41181cac2.png)
 
 	To get that workspace run your job without any servers{Build Now}
 
 ![image](https://user-images.githubusercontent.com/47205003/121778871-9a692300-cbb6-11eb-9cfb-df171875538f.png)

•	Now go into that Workspace

![image](https://user-images.githubusercontent.com/47205003/121778877-a523b800-cbb6-11eb-98b7-f0feb76e9a1b.png)

•	Now go to Build and add build step {Send files or execute command over SSH}

![image](https://user-images.githubusercontent.com/47205003/121778886-af45b680-cbb6-11eb-82f3-89860a6baf52.png)

![image](https://user-images.githubusercontent.com/47205003/121778888-b1a81080-cbb6-11eb-9a79-00661c8139cb.png)

	Now in Transfers {EXEC COMMAND}

    rsync -avh /var/lib/jenkins/workspace/Project-1/*.html root@172.31.13.70/opt/index.html 
  
  {This root@ Private IP of Ansible}
  SAVE AND APPLY
  
![image](https://user-images.githubusercontent.com/47205003/121778914-cdabb200-cbb6-11eb-9044-52e9d01fd322.png)

  BUILD NOW
   
![image](https://user-images.githubusercontent.com/47205003/121778923-dc926480-cbb6-11eb-9c5f-00514b8513cd.png)

•	Now go to Ansible Server

![image](https://user-images.githubusercontent.com/47205003/121778934-ec11ad80-cbb6-11eb-94cb-759f7b64e496.png)

	But on Web Server Nothing came

![image](https://user-images.githubusercontent.com/47205003/121778941-f338bb80-cbb6-11eb-8bf6-e7d4c808ca83.png)

•	Now go to POST BUILD ACTION {select SEND BULD ARTIFACTS OVER SSH}

![image](https://user-images.githubusercontent.com/47205003/121778948-f9c73300-cbb6-11eb-9b29-7caf97396d9c.png)

	Now in Transfers {EXEC COMMAND}

    ansible-playbook  /sourcecode/playbook.yml
    
   APPLY AND SAVE

![image](https://user-images.githubusercontent.com/47205003/121778966-09df1280-cbb7-11eb-881b-1ca7aeebd0e5.png)

BUILD NOW

8.	Now Copy Web Server Public IP and paste on GOOGLE and Enter
YOUR INDEX.HTML material Will be SHOWN

9.	Now setup DEVELOPER SERVER
Copy Public IP address of DEVELOPER start that in PUTTY

![image](https://user-images.githubusercontent.com/47205003/121778981-1d8a7900-cbb7-11eb-9948-2e38e48c28a4.png)

•	Install Git on it

![image](https://user-images.githubusercontent.com/47205003/121778989-24b18700-cbb7-11eb-9d04-ceff3240c5ed.png)

•	Git clone “repository URL”

![image](https://user-images.githubusercontent.com/47205003/121778996-2d09c200-cbb7-11eb-873d-8f28625b45b2.png)

![image](https://user-images.githubusercontent.com/47205003/121779001-3004b280-cbb7-11eb-9e34-7c4be64a4d0d.png)

    vim index.html 

![image](https://user-images.githubusercontent.com/47205003/121779011-3abf4780-cbb7-11eb-9574-6e6e90dbf728.png)

	Now edit this

![image](https://user-images.githubusercontent.com/47205003/121779020-4448af80-cbb7-11eb-91e1-bef424f14b83.png)

•	Now Do A Commit

![image](https://user-images.githubusercontent.com/47205003/121779026-4a3e9080-cbb7-11eb-9b52-2e3b97b2ba3b.png)

•	Now Push Your Commit {Main because mine its main It can Be Master in You}

![image](https://user-images.githubusercontent.com/47205003/121779037-54f92580-cbb7-11eb-9ac4-d4326f9571e7.png)

•	After Doing this Your Build Run Automatically

![image](https://user-images.githubusercontent.com/47205003/121779047-63dfd800-cbb7-11eb-81da-7089aca7b16d.png)

10.	Now Copy Web Server Public IP and paste on GOOGLE and Enter
YOUR updated INDEX.HTML material Will be SHOWN



![image](https://user-images.githubusercontent.com/47205003/121779084-8f62c280-cbb7-11eb-93c9-4bdd5cb73fa1.png)


                                                
















