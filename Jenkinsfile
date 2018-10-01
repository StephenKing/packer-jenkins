pipeline {
    agent {
        docker {
            image 'hashicorp/packer:1.3.1'
            label 'terraform' // just because this has EC2 API permissins
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
        ansiColor('xterm')
    }
}