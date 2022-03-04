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
        stage('android') {
            steps {
                sh "rm -rf android"
                sh "npx cap add android"
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
       stage('gradle') {
            steps {
                sh "cd android"
                /*sh "chmod +x gradlew"*/
                sh "./gradlew clean"  
                sh "./gradlew assembleDebug"
            }
        }
       /*stage('Clean Build') {
           dir("android") {
               sh "pwd"
               sh 'ls -al'
               sh './gradlew clean'
           }
        }
       stage('open android') {
         dir("android") {
             sh './gradlew assembleRelease'
            }
           steps {
           
                sh "gradle clean assembleRelease"
            }
        }*/
        
      }
   }

