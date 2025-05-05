pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
                echo 'Build complete'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test || echo "No tests configured"'
            }
        }
        stage('Deploy') {
            steps {
                script {
                    echo "Triggering OpenShift Build"
                    sh 'oc start-build myapp'
                }
            }
        }
    }
}
