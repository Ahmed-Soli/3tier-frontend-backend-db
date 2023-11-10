pipeline {
    agent any
    
    
    stages{
        stage('Build frontend docker image'){
            steps{
                script{
                    sh 'docker build -t ahmedsoliman202/3tier-frontend-app  -f ./frontend/Dockerfile .'
                }
            }
        }
        stage('Push frontend image to Hub'){
            steps{
                script{
                   sh 'docker login -u ahmedsoliman202 -p Do42615185' 
                // this is production way to define secret_text variable in Jenkins instead of using plain text
                //    withCredentials([string(credentialsId: 'dockerhub-pwd', variable: 'dockerhubpwd')]) { 
                //    sh 'docker login -u ahmedsoliman202 -p ${dockerhubpwd}' 
                   }
                   sh 'docker push ahmedsoliman202/3tier-frontend-app'
                }
            }
        stage('Build backend docker image'){
            steps{
                script{
                    sh 'docker build -t ahmedsoliman202/3tier-backend-app  -f ./backend/Dockerfile .'
                }
            }
        }
        stage('Push backend image to Hub'){
            steps{
                script{
                   sh 'docker login -u ahmedsoliman202 -p Do42615185' 
                // this is production way to define secret_text variable in Jenkins instead of using plain text
                //    withCredentials([string(credentialsId: 'dockerhub-pwd', variable: 'dockerhubpwd')]) { 
                //    sh 'docker login -u ahmedsoliman202 -p ${dockerhubpwd}' 
                   }
                   sh 'docker push ahmedsoliman202/3tier-backend-app'
                }
            }
        }
        
    }
