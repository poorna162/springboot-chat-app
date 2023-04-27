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
          stage('code quality sonar') {
            steps {
               sh "mvn clean verify sonar:sonar \
  -Dsonar.projectKey=sonar_project \
  -Dsonar.projectName='sonar_project' \
  -Dsonar.host.url=http://182.18.184.72:9000 \
  -Dsonar.token=sqp_113c4b4f7c0a8d2d6231ce9b843022b3b881734b"
            }
        }
            
    }
    
   
}
