pipeline {
    agent any  // Use any available agent

    tools {
        maven 'Maven'  // Ensure this matches the name configured in Jenkins
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Samiksha201104/MyGradleApp.git'
            }
        }

        stage('Build') {
            steps {
                sh 'chmod +x gradlew'
                sh './gradlew build --no-daemon'
            }
        }

        stage('Test') {
    steps {
        sh './gradlew test --no-daemon'
    }
}

        
        
       
        stage('Run Application') {
    steps {
        sh './gradlew run'
    }
}
        
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
