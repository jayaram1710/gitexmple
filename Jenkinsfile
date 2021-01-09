pipeline {
    agent any
    stages { 

  stage('ContinuousDownload') 
  {
  steps {
    git 'https://github.com/selenium-saikrishna/maven.git'
  } 
  }
  stage('ContinuousBuild') 
  {
  steps {
    sh 'mvn package'
  } 
  }
  stage('ContinuousDeployment') 
  {
  steps {
    sh 'scp /var/lib/jenkins/workspace/test/webapp/target/webapp.war ubuntu@172.31.52.40:/var/lib/tomcat8/webapps/test.war'
  }
  }
  stage('ContinuousTesting') 
  {
  steps {
    git 'https://github.com/selenium-saikrishna/TestingOnLinux.git'
  }  
  }
  stage('ContinuousDelivery') 
  {
  steps {
    
    sh 'scp /var/lib/jenkins/workspace/test/webapp/target/webapp.war ubuntu@172.31.52.40:/var/lib/tomcat8/webapps/test.war'
  }
  }
}
