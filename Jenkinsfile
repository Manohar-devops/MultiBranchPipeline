 pipeline {
    agent any
    stages {
        stage ('Build') {
            steps {
                echo "Building app"
            }
        }
        stage ('Sonar') {
            steps {
                echo "code quality"
            }
        }
        stage ('DockerImage') {
            steps {
                echo "creating docker image"
            }
        }
        stage ('DockerPush') {
            steps {
                echo "pushing docker image to docker hub"
            }
        }
        stage ('stage') {
            when {
                branch 'release/*'
            }
            steps {
                echo "Deploying app in stage"
            }
        }
        stage ('production') {
            when {
                // Application should only deploy to prod if the app is going through tag
                //vx.x.x ==> v1.2.3 is the tag version
                tag pattern: "v\\d{1,2}\\.\\d{1,2}\\.\\d{1,2}\\", comparator: "REGEXP"
            }
            steps {
                echo "Deploying app in production"
            }
        }
    }
 }
