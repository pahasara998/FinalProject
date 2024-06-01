pipeline {
    agent any
    stages{
        stage('build project'){
            steps{
                git url:'https://github.com/pahasara998/FinalProject', branch: "master"
                sh 'mvn clean package'
              
            }
        }
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t pahasara998/finalpro:v1 .'
                    sh 'docker images'
                }
            }
        }
         
        
     stage('Deploy') {
            steps {
                sh 'sudo docker run -itd --name FinalProjectContainer -p 8083:8081 pahasara998/finalpro:v1'
                  
                }
            }
        
    }
}
