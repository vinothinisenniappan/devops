pipeline {
    agent any

    stages {

        stage('Source Code') {
            steps {
                echo 'Cloning...'
                git branch: 'main', url: 'https://github.com/Marvel-k23/jenkins-nginix.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker Image...'
                sh 'docker build -t job-11 .'
            }
        }

        stage('Deploy Container') {
            steps {
                echo 'Deploying Container...'
                 sh 'docker stop job-11'
                 sh 'docker rm job-11'
                
                sh 'docker run -d -p 80:80 --name job-11 job-11'
            }
        }
    }
}
