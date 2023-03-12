pipeline {
    agent { label 'docker' }
    triggers { 
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/PrakashReddy2525/StudentCoursesRestAPI.git',
                    branch: 'develop'
            }
        }
        stage('build') {
            steps {
                sh 'docker image build -t prakashreddy2525/spc:latest .'
            }
        }
        stage('scan and push') {
            steps {
                sh 'echo docker scan prakashreddy2525/spc:latest'
                sh 'docker image push prakashreddy2525/spc:latest'
            }
        }
    }
}
