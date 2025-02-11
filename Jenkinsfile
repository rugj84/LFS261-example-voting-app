pipeline {
    agent any

    stages {
        stage('one') {
            steps {
                echo 'Step1'
                sleep 3
            }
        }
        stage('two') {
            steps {
                echo 'Step2'
                sleep 9
            }
        }
        stage('three') {
            when {
                branch 'master'
                changeset "**/worker/**"
            }
                steps {
                   echo 'Step3'
                   sleep 5
            }
        }
    }
    post{
        always{
            echo 'This pipeline is completed.'
        }
        failure{
            slackSend (channel: "#ci-cd", message: "Build Failed: ${env.JOB_NAME} ${env.BUILD_NUMBER}")
        }
        success{
            slackSend (channel: "#ci-cd", message: "Build Success: ${env.JOB_NAME} ${env.BUILD_NUMBER}")

    }
}
