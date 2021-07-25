pipeline {
    agent any
   
    stages {
        
         stage('SonarQube Analysis') {
      environment {
        SCANNER_HOME = tool 'sonarqube1'
        ORGANIZATION = "sonarqube-job1"
        PROJECT_NAME = "sonarqube-job1"
      }
      steps {
        withSonarQubeEnv('sonarqube') {
            sh '''$SCANNER_HOME/bin/sonar-scanner -Dsonar.organization=$ORGANIZATION \
            -Dsonar.projectKey=$PROJECT_NAME \
            -Dsonar.sources=.'''
        }
      }
    }
        
        
        
        stage('Compile'){
            steps{
            sh 'mvn compile'
            }
        }

        stage('Test'){
            steps{
            sh 'mvn test'
            }
        }
        stage('Build'){
            steps{
            sh 'mvn install'
            }
        }
      
        stage('deploy'){
            steps{
                sh 'mvn deploy'
            }
        }
               
   }
}
