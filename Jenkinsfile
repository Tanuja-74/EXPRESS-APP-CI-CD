pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                dir('backend-express') {
                    sh 'npm install'
                }
            }
        }

        stage('Run App') {
            steps {
                dir('backend-express') {
                    sh '''
                    /usr/bin/pm2 restart express-app || /usr/bin/pm2 start server.js --name express-app
                    '''
                }
            }
        }
    }
}
