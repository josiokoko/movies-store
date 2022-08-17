def imageName = 'josiokoko/movies-store
def imageTest = docker.build("${imageName}-test", "-f Dockerfile.test
pipeline{
    agent any
    
    stages{
        
        
        stage("Checkout") {
            steps{
                checkout scm
            }
        }
        
        
         stage("Quality Testing") {
            steps{
                script {
                    imageTest.inside {
                        sh 'npm run lint
                    }
                }
            }
        }
        
        
    }
    
    
}
