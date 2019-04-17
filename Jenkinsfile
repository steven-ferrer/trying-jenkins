pipeline {
    agent any

    environment {
        DISABLE_AUTH = 'true'
        DB_ENGINE = 'sqlite'
    }

    options {
        skipStagesAfterUnstable()
    }

    stages {
        stage('No-op') {
            steps {
                sh 'ls'
            }
        }

        stage('Build') {
            steps {
                echo 'Building...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
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
           //  mail to: 'steven.r.ferrer@gmail.com',
           //         subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
           //         body: "Something is wrong with ${env.BUILD_URL}"
        }
        unstable {
            echo 'I am unstable :/'
        }
        changed {
            echo 'Things were different before... :/'
        }
    }
}
