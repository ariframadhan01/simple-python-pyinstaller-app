node {
    stage('Build') {
        docker.image('python:3.9-slim').inside {
            sh 'pip install -r requirements.txt'
        }
    }

    stage('Test') {
        docker.image('python:3.9-slim').inside {
            sh 'pytest tests/'
        }
    }
}

