pipeline {
    agent {
        label 'java-agent-slave'
    }
    stages {
        stage ('Build') {
            steps {
                echo "Building App"
            }
        }
        stage ('Scans') {
            parallel {
                stage ('Sonar') {
                    steps {
                       echo 'Sonar completed'
                       sleep 10
                    }
                }
                stage ('fortify') {
                    steps {
                        echo "fortify completed"
                        sleep 10
                    }
                }
                stage ('contrast') {
                    steps {
                        echo "contrast completed"
                        sleep 10
                    }
                }
            }
        }
        stage ('Prod') {
            input {
                message "Ready for deploying to Prod ?"
                ok "Yes"
                submitter "Manohar"
            }
            steps {
                echo "Deploying to prod"
            }
        }
    }
    post {
        // This will run if the current pipeline or stage has a success
        success {
            echo "Post ===> Success is called"
        }
        // This will run if the current pipeline or stage has a success
        failure {
            echo "Post ===> failure is called"
        }
        // run regardless of completion status of the pipeline or stage
        always {
            echo "Post ===> Always is called"
        }
    }
}
