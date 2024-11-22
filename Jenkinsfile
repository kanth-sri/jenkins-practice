pipeline{
    agent {label 'AGENT-1'}
    stages{
        stage("build")
        {
            steps{
                echo "Building app......"
            }
        }
        stage('Test'){
            steps{
                sh echo "Testing app...."
            }
        }
        stage('Deploy'){
            steps{
                sh echo "Deployed..."
            }
        }
    }
    post {
    always{
        sh echo "Running always"
    }
    failure{
        sh echo "script failed"
    }
}
}
