pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/soufa26/devops1.git'
            }
        }

        stage('Setup Python') {
            steps {
                sh '''
                python3 --version

                # Installer pip si absent
                if ! command -v pip3 &> /dev/null; then
                    echo "pip3 not found, installing..."
                    sudo dnf install -y python3-pip
                fi

                pip3 --version
                pip3 install --upgrade pip
                '''
            }
        }

        stage('Run Script') {
            steps {
                sh '''
                python3 main.py
                '''
            }
        }

    }
}
