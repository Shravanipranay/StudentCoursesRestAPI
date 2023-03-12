pipeline{
    agent{ label 'jfrog_1' }
    stages{
        stage('build'){
            steps{
                git url: 'https://github.com/Shravanipranay/StudentCoursesRestAPI.git',
                branch: 'master'
            }
        }
        stage( 'image_build'){
            steps{
                sh 'sudo docker image build -t shravanipranay/spc:latest .'
            }
        }
        stage('push'){
            steps{
              sh 'sudo docker image push shravanipranay/spc:latest'  
            }
        }
        stage(scan){
            steps{
                sh 'docker scan shravanipranay/spc -y' 
            }
        }
    }
}            