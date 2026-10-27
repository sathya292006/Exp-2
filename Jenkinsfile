pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build the application...'
                bat '"C:\\Users\\Gowsalya\\AppData\\Local\\Programs\\Python\\Python313\\python.exe" -m py_compile app.py'
            }
        }

        stage('Test') {
            steps {
                echo 'tests...'
                bat '"C:\\Users\\Gowsalya\\AppData\\Local\\Programs\\Python\\Python313\\python.exe" -m unittest test_app.py'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                bat '''
                    if not exist deploy mkdir deploy
                    copy /Y app.py deploy\\app.py
                '''
            }
        }
    }

    post {
        success {
            echo 'completed successfully!'
        }

        failure {
            echo 'Pipeline failed.'
        }
    }
}


