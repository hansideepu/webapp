pipeline {
  agent any
  tools {
    maven 'Maven'
    jdk 'Java11'
  }
  stages {
    stage('Build') {
      steps {
        bat 'mvn -Dmaven.test.failure.ignore=true clean package' 
      }
    }
    stage ('Deploy') {
            steps{
              deploy adapters: [tomcat9(credentialsId: 'd1cf148a-5f2e-4d3d-8cdb-b5bae39d0ab8', path: '', url: 'http://localhost:8090/')], contextPath: 'helloworld', war: '**/*.war'
              echo "Deploy successful";
            }
        }
    }
}
