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
                echo 'Deploying....'
		sh 'rsync -vrzhe "ssh -o StrictHostKeyChecking=No pipelinetestemag@pipelinetest.emaginelc.com" . pipelinetestemag@pipelinetest.emaginelc.com:/home2/pipelinetestemag/public_html'
            }
        }
    }
}
