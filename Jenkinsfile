pipeline {
    agent any
    stages {
        stage('change directory') {
            steps {
                sh 'cd /var/lib/jenkins/workspace'
                sh 'pwd'
            }
        }

        stage('git clone') {
            steps {
                sh 'git clone https://github.com/Laxman-gaur/nodejs-sample-app.git'
                sh 'cd ./nodejs-sample-app'
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
                sh 'npm start index.js' 
            }
        }
    }
}
