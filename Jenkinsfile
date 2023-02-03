pipeline{
    agent any
    tools{
        maven 'MAVEN'
    }
    stages{
        stage('github-webhook'){
            steps{
                script{
                    properties([pipelineTriggers([githubPush()])])
                }
            }
        }
        stage('checkout'){
            steps{
                git branch: 'FIRST', url: 'https://github.com/chaithanya1812/test1.git'
            }
        }
        stage('BUILD'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('SonarQube Report'){
            steps{
                sh 'mvn sonar:sonar'
            }
        }
        stage('upload Artifact to nexus'){
            steps{
                sh 'mvn deploy'
            }
        }
        stage('Deployment approval'){
            options{
                timeout(time: 1, unit: 'MINUTES')
            }
            steps{
                input "please give request to Deploy"
            }
        }

        stage('Deploy into Tomcat'){
            steps{
                deploy adapters: [tomcat9(credentialsId: 'new', path: '', url: 'http://43.205.116.193:8080/')], contextPath: 'cloud-website', war: '**/*.war'
            }
        }
    }
    
    
}
