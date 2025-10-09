
pipeline {

    agent any

    stages {

        stage('Clean') {

            steps {

                echo 'Cleaning...'

                sh 'mvn clean'

            }

        }
        stage('test'){
            steps {
                echo 'testing'
                sh 'mvn test'
            }
        }
        stage('Package') {

            steps {

                echo 'Packaging...'

                sh 'mvn package'

            }

        }

        stage('Build') {

            steps {

                echo 'Building...'

                sh 'mvn install'

            }

        }
stage('deploy') { 
    steps{
        echo 'deploying'
        deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat', path: '', url: 'http://65.1.145.44:8081/')], contextPath: null, war: '**/*.war'


    }   

}
 
    }
}

