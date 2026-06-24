pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
    steps {
        bat '''
        py -3.11 -m venv venv
        venv\\Scripts\\python -m pip install --upgrade pip
        venv\\Scripts\\pip install -r requirements.txt
        '''
    }
}

        stage('Run Tests') {
            steps {
               bat 'venv\\Scripts\\pytest tests -v'
            }
        }
    }
}