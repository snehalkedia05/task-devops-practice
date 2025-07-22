pipeline {
    agent any

    stages {
        stage('Clone GitHub Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/snehalkedia05/task-devops-practice.git'
            }
        }

        stage('Deploy to Apache Server via SSH') {
            steps {
                sshagent(credentials: ['apache-ssh']) {
                    sh '''
                        echo "Deploying to Apache server..."
                        ssh -o StrictHostKeyChecking=no jenkins@172.178.56.107 "sudo rm -rf /var/www/html/*"
                        scp -o StrictHostKeyChecking=no -r * jenkins@172.178.56.107:/var/www/html/
                    '''
                }
            }
        }
    }
}

