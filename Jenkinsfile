pipeline {
    agent any
    stages {
        stage('Super Stage Testing') {
            when {
                    expression {
                        BRANCH_NAME == 'super'
                    }
                }
            steps {
                script {
                    echo "it is super branch testing ... ${BRANCH_NAME}"
                }
            }
        }
        stage('2NDBRANCH Stage Testing') {
            when {
                    expression {
                        BRANCH_NAME == '2ndbranch'
                    }
                }
            steps {
                script {
                    echo "it is 2ndbranch branch testing ... ${BRANCH_NAME}"
                }
            }
        }
    }
    post {
        always {
            // Clean up Docker images to free up space after each run
            // sh 'docker image rm $DOCKER_IMAGE_NAME:0.0.6 || true'
            echo "always portion will always run ..."
        }
        success {
            echo 'version checkout Pipeline executed successfully!'
        }
        failure {
            echo 'version checkout Pipeline failed. Check logs for errors.'
        }
    }
}