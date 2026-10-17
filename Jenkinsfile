pipeline {
    agent any 
    environment {
        Deploy_To = "Prod"
    }
    stages {
        stage ("When Stage") {
            when {
                anyOf {
                    environment name: 'Deploy_To', value: 'Something'
                    expression { BRANCH_NAME ==~ /(production|staging)/ }
                }
            }
            steps {
                echo "Deploying when Stage to Prod"
            }
        }
    }
}
