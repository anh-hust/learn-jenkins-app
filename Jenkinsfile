pipeline {
    agent any

    stages {
        stage("Build project in docker") {
            agent {
                docker {
                    image 'node:18-alpine'
                }
            }
            steps {
                sh '''
                    echo "Run with docker -- Environment version information"
                    npm --version
                    node --version
                    echo "Start to build the project"
                    npm install
                    npm run build
                    ls -la
                '''
            }
        }
    }
}