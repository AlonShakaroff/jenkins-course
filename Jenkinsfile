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
            echo 'Running tests...'
            steps {
                parallel(
                    stage('Test Add') {
                        steps {
                            echo 'Testing add...'
                            sh 'pytest test_add.py'
                        }
                    }

                    stage('Test Subtract'){
                        steps {
                            echo 'Testing subtract...'
                            sh 'pytest test_subtract.py'
                        }
                    }
                )
            }
        }
    }
}
