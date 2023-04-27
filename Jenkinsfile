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
  -Dsonar.projectKey=sonar_a \
  -Dsonar.projectName='sonar_a' \
  -Dsonar.host.url=http://182.18.184.72:9000 \
  -Dsonar.token=sqp_03461f808eb945b24195cba17ec01cde820a0de9"
            }
        }
            
    }
    
   
}
