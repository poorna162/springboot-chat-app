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
  -Dsonar.projectKey=sonar_project1 \
  -Dsonar.projectName='sonar_project' \
  -Dsonar.host.url=http://182.18.184.72:9000 \
  -Dsonar.token=sqp_b4ceeeb9f946c41076a2a38077658760f60311fb"
            }
        }
        
    }
    
    
}
