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
    		sh 'ls -al'
	}
                echo 'Deploying....'
            }
        }
    }
}
