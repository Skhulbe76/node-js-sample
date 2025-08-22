pipeline{
    agent any

    stages{
        stage("Checkout"){
            steps{
                echo "checkout step"
                git branch: 'master', url: "https://github.com/Skhulbe76/node-js-sample"
            }
        }

        stage("Build"){
            steps{
                echo "Build step"
                sh "npm install"
            }
        }

        stage("Test"){
            steps{
                echo "Test step"

            }
        }

        stage("Deploy"){
            steps{
                echo "Deploy step"
                sh "npm start"
            }
        }
    }

}