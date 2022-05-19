def imageName = 'dpt3demo.jfrog.io/default-docker-local/valaxy-rtp'
def registry  = 'https://dpt3demo.jfrog.io/'
def app
pipeline {
    agent {
       node {
         label "valaxy"
      }
    }
    stages {

      
        stage('Build') {
            steps {
                echo '<--------------- Building --------------->'
                sh 'printenv'
                sh 'mvn clean deploy -Dmaven.test.skip=true'
                echo '<------------- Build completed --------------->'
            }
        }


        stage('Unit Test') {
            steps {
                echo '<--------------- Unit Testing started  --------------->'
                sh 'mvn surefire-report:report'
                echo '<------------- Unit Testing stopped  --------------->'
            }
        }
    }
}
