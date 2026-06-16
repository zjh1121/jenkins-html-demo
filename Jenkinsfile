pipeline {
    agent any

    stages {
        stage('查看工作目录') {
            steps {
                sh 'pwd'
                sh 'ls -la'
            }
        }

        stage('部署到服务器') {
            steps {
                sshagent(credentials: ['server-root-ssh']) {
                    sh '''
                        ssh -o StrictHostKeyChecking=no root@8.136.188.3 "mkdir -p /var/www/html/jenkins-demo"
                        scp -o StrictHostKeyChecking=no index.html root@8.136.188.3:/var/www/html/jenkins-demo/index.html
                    '''
                }
            }
        }

        stage('验证服务器文件') {
            steps {
                sshagent(credentials: ['server-root-ssh']) {
                    sh '''
                        ssh -o StrictHostKeyChecking=no root@8.136.188.3 "ls -la /var/www/html/jenkins-demo && cat /var/www/html/jenkins-demo/index.html"
                    '''
                }
            }
        }
    }
}