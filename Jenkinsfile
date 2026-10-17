pipeline {
    agent any 
    environment {
        Deploy_To = "Prod"
    }
    stages {
        stage ("When Stage") {
            when {
                allOf {
                    environment name: 'Deploy_To', value: 'Prod'
                    expression { BRANCH_NAME ==~ /(production|staging)/ }
                }
            }
            steps {
                echo "Deploying when Stage to Prod"
            }
        }
    }
}
