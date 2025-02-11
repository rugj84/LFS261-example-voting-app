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
    }
}
