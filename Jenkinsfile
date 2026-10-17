pipeline {
    agent any
    stages {
        stage ("When Stage") {
            when {
                expression {
                    BRANCH_NAME ==~ /(production|staging)/
                }
            }
            steps {
                echo "Deploying when Stage to Prod"
            }
        }
    }
}
