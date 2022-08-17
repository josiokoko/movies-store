pipeline{
    agent any
    
    environment {
        imageName = 'josiokoko/movies-store'
    }
    
    stages{
        
        
        stage("Checkout") {
            steps{
                checkout scm
            }
        }
        
        
         stage("Quality Testing") {
             agent {
                    // Equivalent to "docker build -f Dockerfile.build --build-arg version=1.0.2 ./build/
                    dockerfile {
                        filename 'Dockerfile.test'
                        label '${imageName}-test'
                    }
                }
                            steps{
                script {
                   sh 'npm run lint'
                }
            }
        }
        
        
    }
    
    
}
