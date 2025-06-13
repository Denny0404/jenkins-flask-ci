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

    post {
        success {
            echo 'Notification: Build pipeline completed.'
            // mail to: 'dakbari1001@conestogac.on.ca',
            //      subject: '✅ Build Success',
            //      body: 'CI pipeline finished successfully!'
        }
        failure {
            echo 'Notification: Build pipeline not completed.'
            // mail to: 'dakbari1001@conestogac.on.ca',
            //      subject: '❌ Build Failed',
            //      body: 'Something went wrong in Jenkins pipeline.'
        }
    }
}
