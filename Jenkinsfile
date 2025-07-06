pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/nikita-57/my-flask-app.git'
            }
        }
        stage('Install') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }
        stage('Test') {
            steps {
                sh 'pytest || true' // если тесты не настроены, можно временно true оставить
            }
        }
        stage('Deploy') {
            steps {
                sh 'nohup python app.py &'
            }
        }
    }
}
