pipeline {
    agent {
        node {
            label 'prod'
        }
    }

    environment {
        scannerHome = tool 'mysonar'
    }

    stages {

        stage("Code") {
            steps {
                git 'https://github.com/ashishbethi/python-code-library-app.git'
            }
        }

        stage("CQA") {
            steps {
                withSonarQubeEnv('mysonar') {
                    sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=MyProject"
                }
            }
        }

        stage("Build") {
            steps {
                sh '''
                docker build -t dbimage database/
                docker build -t authimage auth/
                docker build -t bookimage book/
                docker build -t borrowimage borrow/
                docker build -t appimage .
                '''
            }
        }

        stage("Scan") {
            steps {
                sh 'trivy image dbimage'
                sh 'trivy image authimage'
                sh 'trivy image bookimage'
                sh 'trivy image borrowimage'
                sh 'trivy image appimage'
            }
        }

        stage("Tag") {
            steps {
                sh 'docker tag dbimage ashbethi10/myproj:dbimage'
                sh 'docker tag authimage ashbethi10/myproj:authimage'
                sh 'docker tag bookimage ashbethi10/myproj:bookimage'
                sh 'docker tag borrowimage ashbethi10/myproj:borrowimage'
                sh 'docker tag appimage ashbethi10/myproj:appimage'
            }
        }

        stage("Registry") {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'dockerhub') {
                        sh 'docker push ashbethi10/myproj:dbimage'
                        sh 'docker push ashbethi10/myproj:authimage'
                        sh 'docker push ashbethi10/myproj:bookimage'
                        sh 'docker push ashbethi10/myproj:borrowimage'
                        sh 'docker push ashbethi10/myproj:appimage'
                    }
                }
            }
        }

        stage("Deploy") {
            steps {
                sh 'docker stack deploy flm --compose-file compose.yml'
            }
        }

    }
}
