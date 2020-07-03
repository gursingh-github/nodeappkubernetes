pipeline{
    agent any
    environment{
        DOCKERTAG = getDockerTag()
        registry = "gurpartapsingh88/k8simage"
        registryCredential = 'dockerhub'
    }
    stages{
        stage("Build docker image"){
            steps{
                script{
                    docker.build registry + ":$BUILD_NUMBER"
                }
            }

        }
        stage("Docker Push"){
            steps{
                withDockerRegistry(credentialsId: 'dockerhub', url: 'https://registry.hub.docker.com') {
                    sh "docker push registry + ":$BUILD_NUMBER" "
                }
            }

        }
    }
}
