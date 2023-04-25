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
        stage('code quality') {
            steps {
                sh 'mvn checkstyle:checkstyle'
                recordIssues(tools: [checkStyle(pattern: '**/checkstyle-result.xml')])
            }
        }
        stage('code quality sonar') {
            steps {
               sh "mvn clean verify sonar:sonar \
  -Dsonar.projectKey=gopal-sonar-project \
  -Dsonar.host.url=http://3.142.94.123:9000 \
  -Dsonar.login=sqp_b5b3bf9498dcc9302ef980bc4cbdf9b4c03ab75b"
            }
        }
        
    }
    
    
}
