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
                '''
            }
        }
        stage('Test') {
            steps {
                sh "grep -i 'Jenkins' message/output.txt"
            }
        }
        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'message/output.txt'
            }
        }
    }
}
