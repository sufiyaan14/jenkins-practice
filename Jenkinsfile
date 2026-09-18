pipeline {
    agent any 
    
    stages {
        stage('Build') {
            steps {
                sh '''
                mkdir -p message
                echo 'Hello from Jenkins!' > message/output.txt
                echo 'Hello from Github!' >> message/output.txt
                echo 'Hello from Sufiyaan' >> message/output.txt
                echo 'Hello from Coolify' >> message/output.txt
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''
                grep -i 'Sufiyaan' message/output.txt
                cat message/output.txt
                '''
            }
        }
        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'message/output.txt'
            }
        }
    }
}
