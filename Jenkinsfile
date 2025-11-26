pipeline {
    // agent any 
    // if we want to run this pipeline in agent-1
    agent{
        label 'AGENT-1'
    }
    stages {
        stage('Build') {
            steps {
                echo "This is build"
            }
        }
        stage('Test') {
            steps {
                echo "This is test"
            }
        }
        stage('Deploy') {
            steps {
                echo "This is deploy"
            }
        }
    }

    post{
        always{
            echo "This section run irrespective of success or failure"
        }
        success{
            echo "This section runs when pipeline is success"
        }
        failure{
            echo "This section runs when pipeline fails"
            // we can integrate slack or any other message service, so when the Build fails it notifies in slack. 
        }
    }
}
