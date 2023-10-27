pipeline {
    
    agent any
    
    tools {
        jdk 'jdk11' 
        maven 'maven3' 
    }

    stages {
        stage("Git Checkout") {
            steps {
                // Clone the Git repository
                git url: 'https://github.com/priscillaclark/Jenkins_CI_CD_Pipeline'
            }
         }

       
        stage("Compile") {
            steps {
                sh 'mvn compile'
            }
        }
     

        stage("Build Docker Image") {
            steps {
        		    script {
            		    def dockerImageName = 'your-docker-image-name'  
                    // Replace with your desired image name

            	      def dockerFile = 'Dockerfile'  
                    // Replace with the path to your Dockerfile

                    // Build a Docker image using Dockerfile
                    sh "docker build -t ${dockerImageName} -f ${dockerFile} ."      
    		        }
            }
        }
    }
}
