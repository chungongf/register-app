pipeline {
  agent { label 'jenkins-Agent' }
  tools {
    jdk 'Java17'
    maven 'Maven3'
  }
  stages{
      stage("Cleanup Workspace"){
              steps {
              cleanWs()
              }
      }
      stage("Checkout from SCM"){
              steps {
                  git branch: 'main', credentialsId: 'github', url: 'https://github.com/chungongf/register-app'
              }
      }

      stage("Build Application"){
             steps {
                 ssh "mvn clean package"
             }
      }

      stage("Test Application"){
             steps {
                 ssh "mvn test"
            }
      }
   }
    
}
