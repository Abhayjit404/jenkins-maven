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
        stage('deploy'){
            steps{
            nexusArtifactUploader artifacts: [
                [
                    artifactId: 'my-app', 
                    classifier: '', 
                    file: 'target/my-app-1.0.war', 
                    type: 'war'
                ]
            ],
                credentialsId: 'nexus3', 
                groupId: 'com.mycompany.app', 
                nexusUrl: ' 34.150.203.18', 
                nexusVersion: 'nexus3', 
                protocol: 'http', 
                repository: 'http://34.150.203.18:8081/repository/app-1-repo', 
                version: '1.0'
            }
        }
   }
}
