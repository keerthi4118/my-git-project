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

        stage('Run Script') {
            steps {
                // Execute your hello.sh script
                sh './hello.sh'
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

