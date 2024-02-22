def buildApp() {
    // Logic to build the application
    echo "Building the application..."
}

def testApp() {
    // Logic to test the application
    echo "Testing the application..."
}

def deployApp() {
    // Logic to deploy the application
    echo "Deploying the application..."
}

pipeline {
    agent any
    parameters {
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: '')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }
    stages {
        stage("build") {
            steps {
                script {
                    buildApp()
                }
            }
        }
        stage("test") {
            when {
                expression {
                    params.executeTests
                }
            }
            steps {
                script {
                    testApp()
                }
            }
        }
        stage("deploy") {
            steps {
                script {
                    deployApp()
                }
            }
        }
    }   
}
