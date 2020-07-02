pipeline{
    agent any
    environment{
        DOCKER_TAG = getDockerTag()
    }
    stages{
        stage('Build Docker Image'){
            steps{
                sh "docker build . -t gurpartapsingh88/kuber:v1"
            }
        }
    }
}
