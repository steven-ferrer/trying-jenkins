pipeline {
    agent any

    environment {
        DISABLE_AUTH = 'true'
        DB_ENGINE = 'sqlite'
    }

    stages {
        stage('No-op') {
            steps {
                sh 'ls'
            }
        }

        stage('Build') {
            steps {
                sh './gradlew build'
            }
        }

        stage('Test') {
            steps {
                sh './gradlew check'
            }
        }
    }
    post {
        always {
            echo 'One way or another, I have finished!'
            // archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
            // junit 'build/reports/**/*.xml'
        }
        success {
            echo 'I succeeded!'
        }
        failure {
            echo 'I failed :('
        }
        unstable {
            echo 'I am unstable :/'
        }
        changed {
            echo 'Things were different before... :/'
        }
    }
}
