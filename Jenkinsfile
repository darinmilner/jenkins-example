def commonLib = evaluate readTrusted("pipeline/common.groovy")

pipeline {
    agent any

    stages {
        stage ("Check code") {
            steps {
                sh """
                ls -la
                pwd
                """
            }
        }
        stage("Build Python Environment") {
            steps {
                script {
                    commonLib.buildPythonEnvironment()
                }
            }
        }

        stage("Run Python File") {
            steps {
                script {
                    sh """
                    python3 main.py
                    """
                }
            }
        }
    }
}