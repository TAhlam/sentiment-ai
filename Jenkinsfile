pipeline {
    agent any

    stages {

stage('Checkout') {
    steps {
        git branch: 'main',
            url: 'https://github.com/TAhlam/sentiment-ai.git'
    }
}

        stage('Install Dependencies') {
            steps {
                bat '''
                python -m pip install --upgrade pip
                pip install -r requirements.txt
                '''
            }
        }

        stage('Run Tests') {
            steps {
                bat 'pytest tests -v'
            }
        }

    }
}