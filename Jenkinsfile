pipeline {
    agent any
   
    stages {
        
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
      
      //  stage('deploy'){
      //      steps{
      //          sh 'mvn deploy'
            
        
       
   }
}
