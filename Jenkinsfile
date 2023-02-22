pipeline {
    agent any

    stages {
        stage('git clone ') {
            steps {
                sh 'https://github.com/Laxman-gaur/nodejs-sample-app.git' 
            }
        }
        stage('change directory') {
            steps {
                sh 'cd /var/lib/jenkins/workspace/nodejs-sample-app'
                sh 'pwd'
            }
        }
        stage('install the dependencies') {
            steps {
                sh 'npm install'
                sh 'npm audit fix --force'
                sh 'npm fund'
            }
        }
        stage('deploy to production') {
            steps {
                sh 'pm2 start index.js' 
            }
        }
    }
}
