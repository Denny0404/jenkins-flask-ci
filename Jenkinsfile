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
                sh 'pip install -r requirements.txt'
            }
        }
        stage('Build') {
            steps {
                echo 'Simulating Flask app build...'
            }
        }
        stage('Test') {
            steps {
                echo 'Running dummy test...'
                sh 'curl --version'  // Example of test command
            }
        }
    }

    post {
        success {
            mail to: 'yourcollegeemail@conestogac.on.ca',
                 subject: '✅ Jenkins Build Success',
                 body: 'CI Pipeline completed successfully!'
        }
        failure {
            mail to: 'yourcollegeemail@conestogac.on.ca',
                 subject: '❌ Jenkins Build Failed',
                 body: 'CI Pipeline failed. Please check Jenkins.'
        }
    }
}
