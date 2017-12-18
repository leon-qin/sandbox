pipeline {
    agent {
        label 'win-vs2017bt'
    }
    environment {
        NOTIFY_LIST = "leon.qin@perkinelmer.com"
        CHECKOUT_BRANCH = "${GIT_BRANCH}"
        BUILD_SOLUTION = ""
        OUTPUT_SPK1 = ""
        OUTPUT_SPK2 = ""
    }
    options {
        timestamps()
        buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '1', daysToKeepStr: '', numToKeepStr: '10'))
    }
    stages {
        stage('Checkout') {
            steps {
                echo "${GIT_BRANCH}"
                pkiCheckout("https://github.com/lqin-pki/sandbox@${env.CHECKOUT_BRANCH}");
            }
        }
        stage('Build & Package') {
            steps {
                //pkiMsbuild2017 "Rebuild", "${BUILD_SOLUTION}", "Configuration=Release"
                bat "dir /S"
            }
        }
        stage('Sign') {
            steps {
                echo "Placeholder for signing stage"
                //pkiSign "${env.OUTPUT_SPK1}"
                //pkiSign "${env.OUTPUT_SPK2}"
            }
        }
        stage('Archive') {
            steps {
                echo "Archive ${env.OUTPUT_SPK1}"
                echo "Archive ${env.OUTPUT_SPK2}"
            }
        }
    }
    post {
        always {
            pkiCheckConsoleWarnings "MSBuild"
            pkiSendBuildResult("${env.NOTIFY_LIST}")
        }
    }
}
