pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3000:3000'
            args '-v /home/ec2-user/caches2:/var/jenkins_home/caches:rw'
            }
    }
    environment {
        CI = 'true' 
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
        stage('Test') { 
            steps {
                sh './jenkins/scripts/test.sh' 
            }
        }
    }
}
