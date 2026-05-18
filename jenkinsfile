pipeline {
   agent { label 'jenkins-Agent'}
   tools {
       jdk 'java-jdk'
       maven 'maven3'
   }
   stages{
      stage("Cleanup Workspace"){
          steps{
            cleanWs()
          }
      }
    stage("Checkout From SCM"){
          steps{
            git branch: 'main', credentialId: 'github', url: 'https://github.com/Raj-551995/register-app.git'
          }
      }
    stage("Build Application"){
          steps{
            sh "mvn clean package"
          }
      }
    stage("Test Application"){
          steps{
            sh "mvn clean test"
          }
      }
   }
   
}
