pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Deploy') {
            steps {
                sh 'sudo mkdir -p /var/www/html/teams-summarizer'
                sh 'sudo cp index.html /var/www/html/teams-summarizer/'
                sh 'sudo cp icon-color.png /var/www/html/teams-summarizer/'
                sh 'sudo cp icon-outline.png /var/www/html/teams-summarizer/'
                sh 'sudo systemctl reload nginx || true'
            }
        }
    }

    post {
        success {
            echo '✅ 배포 완료!'
        }
        failure {
            echo '❌ 배포 실패'
        }
    }
}
