pipeline{
    agent any
    environment{
    }
    stages{
        stage('Build Docker Image'){
            steps{
                sh "docker build . -t gurpartapsingh88/kuber:v1"
            }
        }
    }
}
