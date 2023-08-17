pipeline {
    agent { label 'docker' }
    triggers { pollSCM('* * * * *') }
    stages {
        stage('VCS') {
            steps {
                git url: 'https://github.com/2023August/StudentCoursesRestAPI.git',
                    branch: 'dev'
            }
        }
        stage('build') {
            steps {
                sh 'docker image build -t tnaveen/spc:2 .'
            }
        }
        stage('scan and push') {
            steps { 
                sh 'echo docker scan build -t tnaveen/spc:2'
                sh 'docker image push tnaveen/spc:2'
            }
        }
    }
}