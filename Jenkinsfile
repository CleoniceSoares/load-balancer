pipeline {
    agent {
        docker {
            image 'node:19-alpine3.15'
            args '-p 3000:3000' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
                sh 'npm run build'
            }
        }
        stage("Deploy") {
            steps {
                sh "rm -rf /home/usuario/load-balancer/build"
                sh "mkdir /home/usuario/load-balancer/build"
                sh "cp -r /home/usuario/jenkins/jenkins_home/jobs/load-balancer-jenkins/builds /home/usuario/load-balancer/build/"
            }
        }
    }
    
}
