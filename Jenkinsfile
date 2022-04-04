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
          	sshagent(['pipeline']) {
    		sh 'rsync -vrzhe . pipelinetestemag@pipelinetest.emaginelc.com:/home2/pipelinetestemag/public_html'
	}
                echo 'Deploying....'
            }
        }
    }
}
