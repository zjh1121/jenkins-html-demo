pipeline {
    agent any

    stages {
        stage('查看工作目录') {
            steps {
                bat 'cd'
                bat 'dir'
            }
        }

        stage('部署静态页面') {
            steps {
                bat 'if not exist C:\\jenkins-html-demo mkdir C:\\jenkins-html-demo'
                bat 'copy index.html C:\\jenkins-html-demo\\index.html'
            }
        }

        stage('验证部署结果') {
            steps {
                bat 'dir C:\\jenkins-html-demo'
                bat 'type C:\\jenkins-html-demo\\index.html'
            }
        }
    }
}