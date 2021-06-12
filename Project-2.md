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



