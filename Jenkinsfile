node {
    stage('Checkout') {
        git branch: 'main', url: 'https://github.com/ariframadhan01/simple-python-pyinstaller-app.git'
    }

    stage('Install Dependencies') {
        sh 'pip install -r requirements.txt'
    }

    stage('Build') {
        sh 'pyinstaller --onefile main.py'
    }

    stage('Test') {
        sh 'pytest'
    }

    stage('Deploy') {
        sh 'echo "Deploying Python App..."'
    }
}

