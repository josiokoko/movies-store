pipeline{
    agent any
    
    environment {
        imageName='josiokoko/movies-store'
    }
    
    stages{
        
        
        stage("Checkout") {
            steps{
                checkout scm
            }
        }
        
        
         stage("Quality Testing") {
              steps{
                script {
                   def imageTest= docker.build("${imageName}-test", "-f Dockerfile.test .")
                    
                    imageTest.inside{
                        sh 'npm run lint'
                    }
                   
                }
            }
        }
        
        
    }
    
    
}
