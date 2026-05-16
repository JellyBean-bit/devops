pipeline {
    agent any

    options {
        timestamps()
    }

    stages {
        stage('Disk usage') {
            steps {
                sh '''
                    echo "===== Disk usage by partition ====="
                    df -h
                '''
            }
        }

        stage('Top memory process') {
            steps {
                sh '''
                    echo "===== Process using most memory ====="
                    ps -eo pid,comm,%mem,rss --sort=-rss | awk 'NR==1 || NR==2 {print}'
                '''
            }
        }
    }
}