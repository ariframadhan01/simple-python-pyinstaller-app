node {
    stage('Clone Repository') {
        git branch: 'main', url: 'https://github.com/ariframadhan01/simple-python-pyinstaller-app.git'
    }

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

    stage('Package') {
        docker.image('python:3.9-slim').inside {
            sh 'pyinstaller --onefile main.py'
        }
    }

    stage('Archive Artifact') {
        archiveArtifacts artifacts: 'dist/main', fingerprint: true
    }
}

