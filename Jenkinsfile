pipeline {
    agent any
    parameters {
        string {name: "PERSON", defaultValue: "Manohar", description: "Enter your name" }
    }
    stages {
        stage ("Parms Stage") {
            steps {
                echo "Welcome ${params.PERSON}"
            }
        }
    }
}
