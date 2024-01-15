/* Requires the Docker Pipeline plugin */
pipeline {
    agent { docker { image 'python:3.12.1-alpine3.19' } }
    stages {
        stage('build') {
            steps {
                sh 'python --version'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
                timeout(time: 5, unit: 'SECONDS') {
                    retry(3) {
                        sh 'sleep 10'
                    }
                }
            }
        }
    }
}
