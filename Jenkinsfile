pipeline {
    agent any
    stages {
        stage('code from scm') {
            steps {
                git 'https://github.com/poorna162/G_cloud4c.git'
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
  -Dsonar.token=sqp_36821827cfbc52164cd2289eb1c441615b84a5d8"
            }
        }
        
    }
    
    
}
