pipeline{
    agent any

    tools {
        nodejs "nodejs"  // the name you set in Jenkins NodeJS config
    }

    stages{
        stage("Checkout"){
            steps{
                echo "checkout step"
                git branch: 'master', url: "https://github.com/Skhulbe76/node-js-sample"
            }
        }

        stage("Install Dependencies"){
            steps{
                echo "Install Dependencies step"
                sh "npm install"
            }
        }

        stage("Test"){
            steps{
                echo "Test step"
            }
        }

        stage('Build') {
            steps {
                cho "build step"
                sh 'npm run build'
            }
        }

        stage("Deploy"){
            steps{
                echo "Deploy step"
                sh '''
                pkill -f "node index.js" || true
                nohup node index.js > app.log 2>&1 &
                '''
                }
        }
    }

     post {
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
    }

}