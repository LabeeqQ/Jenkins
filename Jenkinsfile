pipeline {

    /* 1️⃣ Docker agent definition */
    agent {
        docker {
            image 'node:18-alpine'
            args '-u root:root'
        }
    }

    /* 2️⃣ Global environment variables */
    environment {
        APP_NAME = "sample-node-app"
        APP_ENV  = "dev"
    }

    /* 3️⃣ Pipeline-level options */
    options {
        timestamps()
        disableConcurrentBuilds()
    }

    /* 4️⃣ Stages */
    stages {

        stage('Checkout Code') {
            steps {
                echo "📥 Checking out source code"
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                echo "📦 Installing dependencies"
                sh '''
                  node --version
                  npm --version
                  npm install
                '''
            }
        }

        stage('Run Tests') {
            steps {
                echo "🧪 Running tests"
                sh '''
                  echo "Simulating tests..."
                  sleep 2
                '''
            }
        }

        stage('Build Application') {
            steps {
                echo "🏗️ Building application"
                sh '''
                  mkdir -p build
                  echo "Build completed for ${APP_NAME}" > build/output.txt
                '''
            }
        }
    }

    /* 5️⃣ Post-build actions */
    post {
        success {
            echo "✅ Pipeline completed successfully"
        }
        failure {
            echo "❌ Pipeline failed"
        }
        always {
            echo "🧹 Cleaning workspace"
            cleanWs()
        }
    }
}
