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
                commonLib.buildPythonEnvironment()
            }
        }
    }
}