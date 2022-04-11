pipeline {
    agent any
    stages {
        stage('npm install') { 
            steps {

                CMD "npm install"
            }
        }
        /*stage('android') {
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
       stage('Clean Build') {
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

