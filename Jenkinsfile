pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
          	sshagent(credentials: ['pipeline']) {
           	  sh '''
               		 [ -d ~/.ssh ] || mkdir ~/.ssh && chmod 0700 ~/.ssh
               		 ssh-keyscan -t rsa,dsa pipelinetest.emaginelc.com >> ~/.ssh/known_hosts
               		 ssh -t pipelinetestemag@pipelinetest.emaginelc.com 'ls -al'
                     rsync -vrzhe "ssh -o StrictHostKeyChecking=No" --exclude .git/ --exclude Jenkinsfile . pipelinetestemag@pipelinetest.emaginelc.com:/home2/pipelinetestemag/public_html
            '''
          }
                echo 'Deploying....'
            }
        }
    }
}
