pipeline {
    agent { label 'master' }
    stages {
        
        stage('Git pull code') {
            steps {
            git 'https://github.com/kudaykiran/expressCart.git'
            }
        }
        stage('Build') {
            steps{
                bat  'npm install'
                bat  'npm install express'
            }
        }
        stage('test') {
            steps{
             bat 'npm test'
            }
        }
        stage('sonarQube') {
            steps{
            bat 'sonar-scanner'
            }
        }
        stage('deploy') {
            steps{
             bat 'npm run'
             bat 'npm start'
            }
        }
    }
}
