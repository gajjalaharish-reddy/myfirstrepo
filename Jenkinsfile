node('master')
   
 {
    
  stage('Cdownload')
    
 {
         
  git 'https://github.com/Suryam2498/MyDevops.git'
   
 }
    
   stage('CBulid')
  
  {
        
  sh 'mvn package'
   
 }
   
 stage('CDeploy')
   
 {
        
  sh 'scp /home/ubuntu/.jenkins/workspace/Pipeline/webapp/target/webapp.war ubuntu@172.31.37.194:/var/lib/tomcat9/webapps/Ptest.war'

    }
   
 stage('Ctest')
    
 {
       
   git 'https://github.com/gajjalaharish-reddy/FunctionalTesting.git'
     
   sh 'java -jar /home/ubuntu/.jenkins/workspace/Pipeline/testing.jar'
    }
   
  stage('Cdelivery')
   
  {
        
    input message: 'waiting for approval', submitter: 'manager'
       
          
    sh 'scp /home/ubuntu/.jenkins/workspace/Pipeline/webapp/target/webapp.war ubuntu@172.31.34.9:/var/lib/tomcat9/webapps/Live.war'


    }
    
    
    
    
  
 }
