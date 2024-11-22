pipeline{
    agent {label 'AGENT-1'}
    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 20, unit: 'SECONDS')
        disableConcurrentBuilds()
        retry(2)
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
