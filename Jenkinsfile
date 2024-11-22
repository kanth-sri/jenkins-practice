pipeline{
    agent {label 'AGENT-1'}
    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 20, unit: 'SECONDS')
        // disableConcurrentBuilds()
        // retry(2)
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages{
        stage("build")
        {
            steps{
                echo "Building app......"
            }
        }
        stage('Test'){
            steps{
                sh 'echo "Testing app...."'
                //sleep 10
            }
        }
        stage('Deploy'){
            steps{
                sh 'echo "Deployed..."'
            }
        }
        stage('print_para'){
            steps{
                echo "name: ${params.PERSON}"
            }
        }
    }
    post {
    always{
       cleanWs()
    }
    failure{
         echo "script failed"
    }
    success{
        echo "deployed successfully"
    }
}
}
