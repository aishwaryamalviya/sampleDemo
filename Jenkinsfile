pipeline {
    agent any
    options {
        buildDiscarder logRotator(daysToKeepStr: '5', numToKeepStr: '10')
    }
    stages {
        stage('npm install') { 
            steps {

                cmd "npm install"
            }
        }
        stage('android') {
            steps {
                cmd "rm -rf android"
                cmd "npx cap add android"
            }
        }
       stage('build') {
            steps {

                cmd "npm run build"
            }
        }
      
       stage('sync') {
            steps {

                cmd "npx cap sync"
            }
        }
       stage('gradle') {
            steps {
                
                /*sh "chmod +x gradlew"*/
                cmd "../IonicApp/android/gradlew clean"  
                cmd "../IonicApp/android/gradlew assembleDebug"
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

