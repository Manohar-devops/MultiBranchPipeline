pipeline {
    agent any
    environment {
        Deploy_To = "Prod"
    }
    stages {
        stage ("When Stage") {
            when {
                environment name: 'Deploy_To', value: 'Something'
            }
            steps {
                echo "Deploying when Stage to Prod"
            }
        }
    }
}
