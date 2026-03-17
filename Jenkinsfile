pipeline {
    agent any

    environment {
        // --- REQUIRED UPDATES ---
        // Change these to your actual details
        DOCKERHUB_USERNAME = "2023bcs0175gvivek"
        // ------------------------
        
        ROLL_NUMBER = "2023bcs0175"
        
        // Formats the image name exactly as the assignment requires
        IMAGE_NAME = "${DOCKERHUB_USERNAME}/${ROLL_NUMBER}"
        
        // Ensure you add Docker Hub credentials in Jenkins with the ID 'dockerhub-creds'
        DOCKER_CREDS = credentials('dockerhub-creds')
    }

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Checking out source code from GitHub...'
                checkout scm
            }
        }
        
        stage('Build Docker Image') {
            steps {
                echo "Building Docker image: ${IMAGE_NAME}"
                script {
                    // Builds and tags the image locally
                    appImage = docker.build("${IMAGE_NAME}")
                }
            }
        }
        
        stage('Push to Docker Hub') {
            steps {
                echo "Logging into Docker Hub and pushing image..."
                script {
                    // Login using the credentials block
                    sh "echo ${DOCKER_CREDS_PSW} | docker login -u ${DOCKER_CREDS_USR} --password-stdin"
                    
                    // Push the image to the repository
                    appImage.push('latest')
                    
                    // Optional: Push with the Jenkins build number as a tag for version control
                    appImage.push("${env.BUILD_ID}")
                }
            }
        }
    }
    
    post {
        always {
            echo "Pipeline execution completed."
            // Logout to secure credentials on the Jenkins node
            sh "docker logout"
        }
    }
}