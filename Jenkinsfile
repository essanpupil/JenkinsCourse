pipeline {
    agent any
    stages {
        stage("Stage 1") {
            steps {
                echo "Hello World!"
                echo "We will print all built in environment variable."
            }
        }
        stage("Stage 2") {
            steps {
                echo "BUILD_ID: ${env.BUILD_ID}"
                echo "BUILD_NUMBER: ${env.BUILD_NUMBER}"
                echo "BUILD_TAG: ${env.BUILD_TAG}"
            }
        }
        stage("Stage 3") {
            steps {
                echo "EXECUTOR_NUMBER: ${env.EXECUTOR_NUMBER}"
                echo "JAVA_HOME: ${env.JAVA_HOME}"
                echo "JENKINS_URL: ${env.JENKINS_URL}"
            }
        }
        stage("Stage 4") {
            steps {
                echo "JOB_NAME: ${env.JOB_NAME}"
                echo "NODE_NAME: ${env.NODE_NAME}"
                echo "WORKSPACE: ${env.WORKSPACE}"
            }
        }
    }
}
