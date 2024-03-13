pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                build 'PES2UG21CS911-1'
                sh 'g++ main1.cpp -o output'
                archiveArtifacts artifacts: 'output', fingerprint: true
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployed'
                sh 'g++ main1.cpp -o output'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
