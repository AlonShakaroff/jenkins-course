pipeline {
    agent any

    stages {
        stage('install dependencies') {
            steps {
                echo 'Installing dependencies...'
                sh 'python -m pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing....'
                sh 'pytest test_add.py'
            }
        }
    }
}
