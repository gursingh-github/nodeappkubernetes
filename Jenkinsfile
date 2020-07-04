pipeline{
    agent any
    environment{
        registry = "gurpartapsingh88/k8simage"
        registryCredential = 'dockerhub'
    }
    stages{
        stage("Build Docker Image"){
            steps{
                sh "docker build . -t gurpartapsingh88/kuber:v1"
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
