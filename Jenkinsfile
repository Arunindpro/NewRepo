pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Checkout') {
            steps {
                echo "Checking out develop branch..."
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Building develop branch..."
                // Example build command:
                // sh 'mvn clean install'
                // sh 'npm install && npm run build'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                // Example:
                // sh 'mvn test'
                // sh 'npm test'
            }
        }

        stage('Deploy') {
            when {
                branch 'develop'
            }
            steps {
                echo "Deploying develop branch..."
                // Example deploy script:
                // sh './deploy.sh'
            }
        }
    }

    post {
        success {
            echo "✅ Build succeeded on develop branch"
        }
        failure {
            echo "❌ Build failed on develop branch"
        }
    }
}