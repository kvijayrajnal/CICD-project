pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Poll SCM and clone the repository
                git branch: 'main', url: 'https://github.com/kvijayrajnal/CICD-project.git/'
            }
        }

        stage('Build Frontend & Backend Docker Images') {
            steps {
                script {
                    // Build the Docker images for frontend and backend
                    sh 'docker-compose build'
                }
            }
        }

        stage('Run Docker Compose') {
            steps {
                script {
                    // Bring up the services (frontend, backend, and MongoDB)
                    sh 'docker-compose up -d'
                }
            }
        }

        //  stage('Run Tests') {
        //     steps {
        //         script {
        //             // Run any tests for the backend (for example)
        //             sh 'docker-compose exec backend npm test'
        //         }
        //     }
        // }

        // stage('Cleanup') {
        //     steps {
        //         script {
        //             // Optional: Stop and remove Docker containers after tests
        //             sh 'docker-compose down'
        //         }
        //     }
        // }
    }

    post {
        always {
             // Clean up Docker containers and images after each run
            echo "pipeline is success"
        }
    }
}
