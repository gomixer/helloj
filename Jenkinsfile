pipeline {
    agent {
        docker {
            image 'maven:3'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Deliver') {
            steps {
                sh "chmod +x -R ${env.WORKSPACE}"
                sh './deliver.sh'
            }
        }
    }
}
