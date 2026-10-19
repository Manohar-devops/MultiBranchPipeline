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
                submitter "manohar"
            }
            steps {
                echo "Deploying to prod"
            }
        }
    }
}
