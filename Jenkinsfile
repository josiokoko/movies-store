pipeline{
    agent none
    
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
                        label 'm${imageName}-test'
                    }
                }
                            steps{
                script {
                    imageTest.inside {
                        sh 'npm run lint'
                    }
                }
            }
        }
        
        
    }
    
    
}
