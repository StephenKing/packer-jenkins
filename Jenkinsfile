pipeline {
    agent {
        docker {
            image 'hashicorp/packer:1.3.1'
            label 'docker'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh "packer build shell.json"
            }
        }
    }
    options {
        timestamps()
    }
}