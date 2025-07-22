pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/snehalkedia05/task-devops-practice.git'
            }
        }

        stage('Deploy to Apache') {
            steps {
                sh 'cp -r * /var/www/html/'
            }
        }
    }
}
