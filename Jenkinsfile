pipeline{
    agent any
    // agent {
    //     label 'slave1'
    // }
    stages{
        stage('checkout'){
            steps{
                git 'https://github.com/saipavan-12/jenkins-java-project-1.git'
            }
        }
        stage('build'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('test'){
            steps{
                sh 'mvn test'
            }
        }
        stage('artifact'){
            steps{
                sh 'mvn package'
            }
        }
        stage('code quality'){
            steps{
                sh '''
                mvn sonar:sonar \
                 -Dsonar.projectKey=saipavan-pipeline1_saipavan-pipeline1 \
                 -Dsonar.host.url=https://sonarcloud.io/projects \
                 -Dsonar.login=834dd5fb923f7a28a92899330eb31ac048111f79
                '''
            }
        }
    }
}
