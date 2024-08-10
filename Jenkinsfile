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
}
post {
            always {
                emailext (
                    subject: "Pipeline Status: ${BUILD_NUMBER}",
                    body: '''<html>
                                <body>
                                    <p>Build Status: ${BUILD_STATUS}</p>
                                    <p>Build Number: ${BUILD_NUMBER}</p>
                                    <p>Check the <a href="${BUILD_URL}">console output</a>.</p>
                                </body>
                            </html>''',
                    to: 'dineshkv511@gmail.com',
                    from: 'dineshkumar.vdp@gmail.com',
                    replyTo: 'dineshkumar.vdp@gmail.com',
                    mimeType: 'text/html'
                )
            }
        }
}