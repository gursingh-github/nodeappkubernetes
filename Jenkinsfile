pipeline{
    agent any
    environment{
        registry = "gurpartapsingh88/k8simage"
        registryCredential = 'dockerhub'
    }
    stages{
        stage("Build docker image"){
            steps{
                script{
                    docker.build registry
                }
            }

        }
        stage("Docker Push"){
            steps{
                withDockerRegistry(credentialsId: 'dockerhub', url: 'https://registry.hub.docker.com') {
                    sh "docker push gurpartapsingh88/k8simage "
                }
            }

        }
        stage("Deploy to k8s"){
            steps{
                script{
                    try{
                        sh "sudo kubectl apply -f . "
                    }catch(error){
                        sh "sudo kubectl create -f ."
                    }
                }
        
            }
        }
        
    }
}
