# DevOps Project-2

DevOps project with Git, Jenkins and Docker on AWS 

1. Launch Four EC2 instances on AWS console Developer, Jenkins Server, Ansible Server, Web Server

![image](https://user-images.githubusercontent.com/47205003/120963736-c41de680-c77f-11eb-87a8-e10ea11d6aa3.png)

2. Setup Jenkins Server on Putty

![image](https://user-images.githubusercontent.com/47205003/120965129-0d6f3580-c782-11eb-98a8-d339e9ef0980.png)

    wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
    
    rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key

![image](https://user-images.githubusercontent.com/47205003/120965268-44dde200-c782-11eb-89be-f1c52e085ada.png)

![image](https://user-images.githubusercontent.com/47205003/120965349-69d25500-c782-11eb-88eb-0642f1eefd6d.png)

![image](https://user-images.githubusercontent.com/47205003/120965438-84a4c980-c782-11eb-8760-88848bad48a2.png)

![image](https://user-images.githubusercontent.com/47205003/120971129-eae11a80-c789-11eb-8e13-020d25983ef3.png)

![image](https://user-images.githubusercontent.com/47205003/120971171-f6344600-c789-11eb-8394-268fc38c1304.png)

3. Setup Ansible Server on Putty

![image](https://user-images.githubusercontent.com/47205003/120972081-fd0f8880-c78a-11eb-9d56-85b924c429bb.png)

![image](https://user-images.githubusercontent.com/47205003/120972567-7d35ee00-c78b-11eb-93d7-b34b7bf8184b.png)

![image](https://user-images.githubusercontent.com/47205003/120972521-7313ef80-c78b-11eb-8278-52a908701834.png)

4. Setup Web Server on Putty

![image](https://user-images.githubusercontent.com/47205003/120974111-5e385b80-c78d-11eb-93c3-ee881215cf32.png)

![image](https://user-images.githubusercontent.com/47205003/120974180-74461c00-c78d-11eb-918d-3d28301be620.png)

5. Connecting Web-Server with Ansible

![image](https://user-images.githubusercontent.com/47205003/120974272-92ac1780-c78d-11eb-9ed2-ced58aa28639.png)

![image](https://user-images.githubusercontent.com/47205003/120974365-a8b9d800-c78d-11eb-97a2-6915a6b63f79.png)
