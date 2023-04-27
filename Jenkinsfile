pipeline {
    agent any
    stages {
        stage('code from scm') {
            steps {
               git 'https://github.com/poorna162/springboot-chat-app.git'
            }
        }
        stage('building the code') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('unit test') {
            steps {
                sh 'mvn test'
            }
        }
       
            
    }
    
    
}
