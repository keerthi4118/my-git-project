pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Pull code from GitHub
                git branch: 'main',
                    url: 'https://github.com/keerthi4118/my-git-project.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Simulating build step...'
                // Add build commands here if needed
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Example: sh 'pytest tests/'
            }
        }

        stage('Run Script') {
            steps {
                sh './hello.sh'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy step placeholder...'
                // Add deployment commands here
            }
        }
    }

    post {
        success {
            emailext (
                subject: "SUCCESS: Jenkins Build #${BUILD_NUMBER}",
                body: "Build succeeded!\n\nJob: ${JOB_NAME}\nBuild Number: ${BUILD_NUMBER}\nStatus: SUCCESS",
                to: "krithika4118@gmail.com"
            )
        }
        failure {
            emailext (
                subject: "FAILURE: Jenkins Build #${BUILD_NUMBER}",
                body: "Build failed!\n\nJob: ${JOB_NAME}\nBuild Number: ${BUILD_NUMBER}\nStatus: FAILURE",
                to: "krithika4118@gmail.com"
            )
        }
    }
}

