pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Denny0404/jenkins-flask-ci.git',
                    credentialsId: 'github-pat'
            }
        }
        stage('Install Dependencies') {
            steps {
                bat 'pip install -r requirements.txt'
            }
        }
        stage('Build') {
            steps {
                echo 'Simulating build...'
            }
        }
        stage('Test') {
            steps {
                echo 'Running test...'
                bat 'curl --version'
            }
        }
    }

  
}
