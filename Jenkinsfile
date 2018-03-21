pipeline {
    agent {
        label 'win-vs2017bt'
    }
    stages {
        stage('Test') {
            steps {
                echo "${BRANCH_NAME}"
            }
        }
    }
    post {
        always {
            pkiDeleteDir()
        }
    }
}
