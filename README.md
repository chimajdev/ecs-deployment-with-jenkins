# ecs-deployment-with-jenkins

  ![image](https://user-images.githubusercontent.com/58024415/113471615-248c6100-947b-11eb-9e68-02fa557c09d9.png)

# Pre-Requisites
    - Install Jenkins
    - Create AWS User with ECR and ECS policies
    - Create ECR Repo
    - Create ECS Cluster
 # Build ECR image with Jenkins
   1. Add Below plugins:
   
    1. Docker
    2. Amazon ECR
    3. Docker Pipeline
    4. CloudBees AWS Credentials

  2. Create Credentilas in Jenkins with the name of "ecr_credentials"
     Goto Mange Jenkins --> Manage Credentials  -->  Jenkins  -->  Global credentials (unrestricted)  -->  Add Credentials
  
  ![image](https://user-images.githubusercontent.com/58024415/113471683-a8464d80-947b-11eb-829c-1efb2ddfbfcc.png)

  Click on OK
  
  3. Create new job in Jenkins and Run
     Goto New item --> Copy content of "Jenkinsfile-Build" inside new job and click on Build

  ![image](https://user-images.githubusercontent.com/58024415/113471739-0a06b780-947c-11eb-944c-4dbffb8745bb.png) 

# Deploy ECR image in ECS cluster
  1. Create ECS cluster with the name of "springboot-cluster"

  ![image](https://user-images.githubusercontent.com/58024415/113471763-41756400-947c-11eb-9462-c37ad92ff328.png) 

  2. Add below plugin in Jenkins
     Amazon Elastic Container Service (ECS) / Fargate
  3. Create Credentilas in Jenkins with the name of "AWS_Credentials"
     Goto Mange Jenkins  -->  Manage Credentials  -->  Jenkins  -->  Global credentials (unrestricted)  -->  Add Credentials
  4. Create new job in Jenkins and Run
     Goto New item --> Copy content of "Jenkinsfile-Deploy" inside new job and click on Build
  5. Check output of application in UI
  
  ![image](https://user-images.githubusercontent.com/58024415/113471821-a9c44580-947c-11eb-8564-809361857a38.png)
