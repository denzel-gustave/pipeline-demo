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
		sh 'rsync -av . pipelinetestemag@pipelinetest.emaginelc.com:/public_html'
            }
        }
    }
}
