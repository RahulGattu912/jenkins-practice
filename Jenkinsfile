pipeline {
    // agent any 
    // if we want to run this pipeline in agent-1
    agent{
        label 'AGENT-1'
    }
    options{
        timeout(time:10,unit:'MINUTES') // means if the build time exceeds 10 minutes, automatically stop the pipeline.
        // disableConcurrentBuilds() // disable concurrent execution of builds
        // retry(3) // retries the build for specific number of times if build fails
    }
    parameters{
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Hello')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage('Build') {
            steps {
                echo "This is build"
                // sh 'sleep 10'
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
        stage('Print Params'){
            steps{
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params. TOGGLE}"
                echo "Choice: ${params. CHOICE}"
                // echo "Password: ${params.PASSWORD}"
            }
        }
    }

    post{
        always{
            echo "This section run irrespective of success or failure"
            deleteDir() // this will create the workspace files in jenkins agent
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
