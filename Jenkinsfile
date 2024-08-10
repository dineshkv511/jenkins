pipeline {
    agent any
    stages {
        stage('Welcome') { 
            steps {
                echo 'Hi , You are inside the pipeline'
            }
        }
        stage('build') {
            steps {
                script {
                    docker.build('hello-world-app')
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    docker.image('hello-world-app').run()
                }
            }

    }
}
}