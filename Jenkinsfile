def packer_file = "shell.json"

pipeline {
    agent {
        docker {
            image 'hashicorp/packer:1.3.1'
            label 'terraform' // just because this has EC2 API permissins
        }
    }
    stages {
        stage('Validate') {
            steps {
                sh "packer validate $packer_file"
            }
        }
        stage('Build') {
            steps {
                sh "packer build $packer_file -var branch=$BRANCH_NAME"
            }
        }
    }
    options {
        timestamps()
        ansiColor('xterm')
    }
}