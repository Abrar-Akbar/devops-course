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
                    // Rsync to production server
                    sh "rsync -avz --delete ./ www@41.215.243.101:/home/www/webroot/"

                    // SSH into production server and execute commands
                    sh "ssh www@41.215.243.101 'cd /home/www/webroot/ && npm install'"
                    sh "ssh www@41.215.243.101 'cd /home/www/webroot/ && npm run build'"
                    sh "ssh www@41.215.243.101 'cd /home/www/webroot/ && pm2 restart'"
                }
            }
        }
    }
}
