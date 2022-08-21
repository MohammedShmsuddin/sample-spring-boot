pipeline {
    agent any
    environment {
        ENV_DOCKER = credentials('dockerhub')
        DOCKERIMAGE = "dummy/dummy"
        EKS_CLUSTER_NAME = "education-eks-jiHD8Gb6"
        SONAR_TOKEN = credentials('sonar_text')
    }
    stages {
        /**stage('build') {
            agent {
                docker { image 'openjdk:11-jdk' }
            }
            steps {
                sh 'chmod +x gradlew && ./gradlew build jacocoTestReport'
                jacoco( 
                    execPattern: 'target/*.exec',
                    classPattern: 'target/classes',
                    sourcePattern: 'src/main/java',
                    exclusionPattern: 'src/test*'
                )
            }
        }
        stage('sonarqube analysis') {
            agent {
                docker { image 'sonarsource/sonar-scanner-cli' } 
            }
            steps {
                sh 'echo scanning!'
                
                withSonarQubeEnv('SonarCloud') {
                    sh './gradlew sonarqube'  
                }
                
            }
        }
        stage('Quality gate') {
           steps {
                timeout(time: 5, unit: 'MINUTES') {
                    waitForQualityGate abortPipeline: true
                }
                
            }
        }*/
        /*stage('docker build') {
            steps {
                sh 'echo docker build'
                sh 'docker build -t mshmsudd/sample-spring-boot:latest .'
            }
        }
        stage('docker push') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'password', usernameVariable: 'username')]) {
                    sh 'echo docker push!'
                    sh 'docker login -u ${username} -p ${password}'
                    sh 'docker push mshmsudd/sample-spring-boot:latest'
                    sh 'docker logout'
                }
            }
        }*/
        stage('Deploy App') {
            steps {
                sh 'echo deploy to kubernetes'
                sh 'kubectl get nodes'
                               
            }
        }
    }
}
