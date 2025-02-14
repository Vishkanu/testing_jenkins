pipeline {
    agent {
        label 'DevWin' // Ensures this runs on a Windows node
    }
    stages {
        stage('Clone Repository') {
            steps {
                git credentialsId: '1', branch: 'main', url: 'https://github.com/YOUR_GIT/my_project.git'
            }
        }
        stage('Build') {
            steps {
                bat '''
                echo "== Starting Build =="
                cd "%WORKSPACE%"
                mkdir build // Ensures build folder exists
                npm install
                echo "== Build Completed! =="
                '''
            }
        }
        stage('Test') {
            steps {
                bat '''
                echo "== Running Tests =="
                cd "%WORKSPACE%"
                npm test
                echo "== Tests Completed! =="
                '''
            }
        }
        stage('Deploy') {
            steps {
                bat '''
                echo "== Deploying Application =="
                echo "== Deploying Successful! =="
                '''
            }
        }
    }
}
