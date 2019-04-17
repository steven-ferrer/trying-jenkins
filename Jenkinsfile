pipeline {
    agent any

    environment {
        DISABLE_AUTH = 'true'
        DB_ENGINE = 'sqlite'
    }

    stages {
        stage('Build') {
            steps {
                sh 'printenv'
            }
        }

        stage('Test') {
            steps {
                sh 'echo "Fail!"; exit 1'
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
            echo 'This will only run if the run was marked unstable'
        }
        changed {
            echo 'This will only run if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
