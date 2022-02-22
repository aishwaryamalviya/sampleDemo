pipeline {
    agent any
    options {
        buildDiscarder logRotator(daysToKeepStr: '5', numToKeepStr: '10')
    }
    stages {
        stage('npm install') { 
            steps {

                sh "npm install"
            }
        }
       stage('build') {
            steps {

                sh "npm run build"
            }
        }
       stage('sync') {
            steps {

                sh "npx cap sync"
            }
        }
       stage('open android') {
            steps {

                sh "npx cap open android"
            }
        }

      }
   }

