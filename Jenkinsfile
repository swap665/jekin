pipeline{
    agent any
    stages{
        stage("CHECKOUT COSE"){
            steps{
                git url:'https://github.com/swap665/jekin.git', branch:'main'
            }

        }
        stage("remove stage"){
            steps{
                sh 'docker rm -f $(docker ps -aq)'
                sh 'docker rmi myimage'
            }
        }
        stage('Build docker image'){
            steps{
                sh 'docker build -t myimage .'
            }
        }
        stage('conatiner'){
            steps{
                sh 'docker run -d -p 8501:8501 myimage'
            }
        }
    }
}
