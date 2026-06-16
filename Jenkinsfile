pipeline {
    agent any

    stages {
        stage('查看工作目录') {
            steps {
                sh 'pwd'
                sh 'ls -la'
            }
        }

        stage('部署静态页面') {
            steps {
                sh 'mkdir -p /tmp/jenkins-html-demo'
                sh 'cp index.html /tmp/jenkins-html-demo/index.html'
            }
        }

        stage('验证部署结果') {
            steps {
                sh 'ls -la /tmp/jenkins-html-demo'
                sh 'cat /tmp/jenkins-html-demo/index.html'
            }
        }
    }
}