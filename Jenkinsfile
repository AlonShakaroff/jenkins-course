pipeline {
    agent any

    stages {
        stage('Consuming dependencies') {
            steps {
                echo 'Installing dependencies...'
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Testing') {
            steps {
                echo 'Running tests...'
                parallel(
                    "test_add": {
                        echo 'Testing add...'
                        sh 'pytest test_add.py'
                    },
                    "test_subtract": {
                        echo 'Testing subtract...'
                        sh 'pytest test_subtract.py'
                    }
                )
            }
        }
    }
}
