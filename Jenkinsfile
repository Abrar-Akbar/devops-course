pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Deploy to Production') {
            steps {
                script {
                    sh "rsync -avz --delete ./ www@41.215.243.101:/home/www/webroot/"
#                    sh "ssh user@41.215.243.101 'cd /home/www/webroot/ && npm install'"
#                    sh "ssh user@41.215.243.101 'cd /home/www/webroot/ && npm run build'"
#                    sh "ssh user@41.215.243.101 'cd /home/www/webroot/ && pm2 restart'"
                }
            }
        }
    }
}
