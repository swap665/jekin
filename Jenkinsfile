pipeline{
    agent: any
    stages{
        stage("CHECKOUT COSE"){
            steps{
                git url:'https://github.com/swap665/jekin.git' branch:'main'
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