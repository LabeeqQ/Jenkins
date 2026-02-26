pipeline {

    /* Run everything inside a Docker container */
    agent {
        docker {
            image 'alpine:latest'
        }
    }

    stages {

        stage('Hello') {
            steps {
                echo 'Pipeline started 🚀'
            }
        }

        stage('Run inside Docker') {
            steps {
                sh '''
                  echo "I am running inside a Docker container"
                  uname -a
                '''
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished ✅'
        }
    }
}
