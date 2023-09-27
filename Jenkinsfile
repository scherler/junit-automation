pipeline {

    agent any
    stages {

        stage('Checkout Codebase'){
            steps{
                checkout scm: [$class: 'GitSCM', branches: [[name: '*/main']],userRemoteConfigs:
                [[credentialsId: 'github-ssh-key', url: 'git@github.com:scherler/junit-automation.git']]]
            }
        }
    }
post {
      always {
          junit '**/reports/*.xml'
      }
   } 
}
