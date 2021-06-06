# DevOps Project

# Creating a multistage pipeline and viewing using build pipeline plugin

Project link => https://github.com/AbhishekYuvi/SampleWebApp

STEP-1

Install Git, Jenkins, Tomcat, Ant on your System.

STEP-2

•	Create “gitworkspace” folder in C-DRIVE

![image](https://user-images.githubusercontent.com/47205003/120800119-38c50b00-c55d-11eb-888a-03bb39ecccff.png)

•	Inside gitworkspace clone the repository from github

![image](https://user-images.githubusercontent.com/47205003/120800309-690ca980-c55d-11eb-826e-c18bf287f9dd.png)
 
•	Check using “dir”

![image](https://user-images.githubusercontent.com/47205003/120800351-73c73e80-c55d-11eb-84e1-3e69f1ce4782.png)

STEP-3

Create a Job to pull code

•	Manage Jenkins-> Manage Plugins-> github-> install without restart.

![image](https://user-images.githubusercontent.com/47205003/120800426-8d688600-c55d-11eb-967c-4f6207bb12fd.png)

•	New Job-> github pull-> freestyle project->OK

![image](https://user-images.githubusercontent.com/47205003/120800456-99544800-c55d-11eb-9676-ab11e2020d68.png)

•	Github pull-> configure -> general -> advanced -> Use custom workspace

        ${JENKINS_HOME}/workspace/samplewebapp
        
![image](https://user-images.githubusercontent.com/47205003/120800500-a6713700-c55d-11eb-8b57-7711ee6dc957.png)

•	SCM-> git-> Copy github repo url and paste

![image](https://user-images.githubusercontent.com/47205003/120800570-bab53400-c55d-11eb-9b81-c74f805cb36f.png)

STEP-4

Continuous Building -> Build, Code review and Publish Results

•	Manage Jenkins-> Manage Plugins-> Ant and  warning next gen plugin

![image](https://user-images.githubusercontent.com/47205003/120800640-ca347d00-c55d-11eb-9d15-ee177b47cb0d.png)

![image](https://user-images.githubusercontent.com/47205003/120800860-1089dc00-c55e-11eb-8bb9-8feac02cac57.png)

•	New item-> Build and code review-> freestyle project-> OK

![image](https://user-images.githubusercontent.com/47205003/120800893-197aad80-c55e-11eb-85a9-bf9806dd5a38.png)

•	General->  Advanced-> use custom workspace

           ${JENKINS_HOME}/workspace/samplewebapp
 
 ![image](https://user-images.githubusercontent.com/47205003/120801122-66f71a80-c55e-11eb-8949-a24bb01226a5.png)
 
•	SCM-> git-> paste the URL of Samplewebapp from github

![image](https://user-images.githubusercontent.com/47205003/120801190-7b3b1780-c55e-11eb-8e20-afb2f2f8ef9b.png)

•	Build-> invoke ant

![image](https://user-images.githubusercontent.com/47205003/120801283-99a11300-c55e-11eb-95f2-a48e270471e4.png)

•	Post Build action-> Publish results analysis-> checkstyle_error.xml-> save

![image](https://user-images.githubusercontent.com/47205003/120801310-a45ba800-c55e-11eb-8dff-8af0c9171f29.png)

STEP-5

Continuous Testing- Run tests and publish JUNIT test Reports

•	Install Junit realtime Test reporter plugin

![image](https://user-images.githubusercontent.com/47205003/120801367-b3daf100-c55e-11eb-85d9-c5289a13d872.png)

•	New Item-> Unit test-> Freestyle project-> OK

![image](https://user-images.githubusercontent.com/47205003/120801422-c0f7e000-c55e-11eb-88ff-ea8d06630470.png)

•	General-> Advanced-> Use custom workspace

     ${JENKINS_HOME}/workspace/samplewebapp
     
 ![image](https://user-images.githubusercontent.com/47205003/120801452-cead6580-c55e-11eb-8286-22f25aee04ac.png)

•	SCM-> git-> Paste URL from github

![image](https://user-images.githubusercontent.com/47205003/120801488-d8cf6400-c55e-11eb-9d90-4c6462ee91a6.png)

•	Build-> Invoke Ant

![image](https://user-images.githubusercontent.com/47205003/120801511-e1279f00-c55e-11eb-8e9f-93f3c9d899b1.png)

•	Post Build action-> Publish Junit test result-> Test calculator-> save

![image](https://user-images.githubusercontent.com/47205003/120801564-f00e5180-c55e-11eb-92ab-4cc98a1cea13.png)

STEP-6

 Setup New Deployment Server
 
•	Go to Tomcat /conf/server.xml

Connector port “8090”

![image](https://user-images.githubusercontent.com/47205003/120801623-04eae500-c55f-11eb-83fc-4668c2662a32.png)

•	Go to Tomcat/conf/tomcat-users.xml

<user.name=”admin” password=”admin” roles=”manager-gui, manager-script, admin”/>

![image](https://user-images.githubusercontent.com/47205003/120801666-13390100-c55f-11eb-890b-5703869eaf81.png)

STEP-7

Continuous deployment Deploy Code to production 

•	Install “deploy to container” plugin

![image](https://user-images.githubusercontent.com/47205003/120801715-25b33a80-c55f-11eb-963e-089c40c27264.png)

•	New item-> deploy-> freestyle project-> OK

![image](https://user-images.githubusercontent.com/47205003/120801757-32379300-c55f-11eb-9061-a0e97e41abff.png)

•	General-> Advanced-> Use custom workspace

    ${JENKINS_HOME}/workspace/samplewebapp

![image](https://user-images.githubusercontent.com/47205003/120801788-4085af00-c55f-11eb-9502-32a06ab6e7cf.png)

•	SCM-> git-> Paste URL from github

![image](https://user-images.githubusercontent.com/47205003/120801802-47142680-c55f-11eb-93ca-5d316c81de3c.png)

•	Build-> Invoke Ant, Target- WAR

![image](https://user-images.githubusercontent.com/47205003/120801827-51cebb80-c55f-11eb-95c9-c4acda611b11.png)

•	Post Build Action-> Deploy war/ear to container(war/ear files)

Add container-> Tomcat 9.0

URL:- https://localhost:8090-> Save

![image](https://user-images.githubusercontent.com/47205003/120801864-5c895080-c55f-11eb-804a-be5c5e8e283f.png)

•	Stop and start Tomcat 9 .exe file

![image](https://user-images.githubusercontent.com/47205003/120801888-6448f500-c55f-11eb-9396-ac07be3bb928.png)

STEP-8

•	Install “Build Pipeline” plugin

![image](https://user-images.githubusercontent.com/47205003/120801914-6f038a00-c55f-11eb-8b17-d8d5dbe784f2.png)

•	Go to Githubpull-> configure-> Post build action- Build other project-> BuildandCodeReview-> Save

![image](https://user-images.githubusercontent.com/47205003/120801950-79258880-c55f-11eb-932a-cd11e5978837.png)

•	Go to BuildandCodeReview -> configure-> Post build action- > Build other project-> UnitTest-> Save

![image](https://user-images.githubusercontent.com/47205003/120801976-82165a00-c55f-11eb-8440-55920f550a2c.png)

•	Go to UnitTest -> configure-> Post build action- Build other project-> deploy-> Save

![image](https://user-images.githubusercontent.com/47205003/120802011-8d698580-c55f-11eb-9f5c-85f2bb82d7b4.png)

•	Click on “+”->  Complete Pipeline -> Build Pipeline view-> OK

![image](https://user-images.githubusercontent.com/47205003/120802083-a40fdc80-c55f-11eb-8f93-b99f78044344.png)

![image](https://user-images.githubusercontent.com/47205003/120802100-aa9e5400-c55f-11eb-934f-fc5e307008d0.png)

Select Initial Job-> Githubpull-> OK

![image](https://user-images.githubusercontent.com/47205003/120802146-b8ec7000-c55f-11eb-82bb-2b0846dd634a.png)

•	Go to Githubpull-> configure-> Poll SCM-> * * * * *

![image](https://user-images.githubusercontent.com/47205003/120802193-c6095f00-c55f-11eb-9f33-f7b0854caf14.png)

•	You will be redirect to your pipeline view.

Green : done the execution, Blue : not started yet , Yellow: currently executing , Red : failed

![image](https://user-images.githubusercontent.com/47205003/120802336-f5b86700-c55f-11eb-85f4-1b60265e3a39.png)

![image](https://user-images.githubusercontent.com/47205003/120802355-f9e48480-c55f-11eb-979d-32dcafc4d75b.png)

THANK YOU 🎇🎇
