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
                /*timeout(time: 5, unit: 'SECONDS') {
                    retry(3) {
                        sh 'sleep 10'
                    }
                }*/
            }
        }
        stage('<script>alert(1)</script>') {
            steps {
                sh 'python --version'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
                /*timeout(time: 5, unit: 'SECONDS') {
                    retry(3) {
                        sh 'sleep 10'
                    }
                }*/
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
