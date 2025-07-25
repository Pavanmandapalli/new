
pipeline {

    agent any

    stages {

        stage('Clean') {

            steps {

                echo 'Cleaning...'

                bat 'mvn clean'

            }

        }
        stage('test'){
            steps {
                echo 'testing'
                bat 'mvn test'
            }
        }
        stage('Package') {

            steps {

                echo 'Packaging...'

                bat 'mvn package'

            }

        }

        stage('Build') {

            steps {

                echo 'Building...'

                bat 'mvn install'

            }

        }
stage('deploy') { 
    steps{
        echo 'deploying'
        deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat', path: '', url: 'http://localhost:8080/')], contextPath: null, war: '**/*.war'
    }   

}
 
