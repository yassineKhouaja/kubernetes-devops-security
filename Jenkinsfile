pipeline {
  agent any

  stages {
      // stage('Build Artifact') {
      //       steps {
      //         sh "mvn clean package -DskipTests=true"
      //         archive 'target/*.jar' //so that they can be downloaded later
      //       }
      //   }
      // stage('Unit Tests') {
      //       steps {
      //         sh "mvn test"
      //       }
      //   }
      stage('Docker Build and Push') {
        steps {
          withDockerRegistry([credentialsId: "dockerhub", url: ""]) {
          sh 'printenv'
          sh 'docker build -t yassinekhouaja/numeric-app:""$GIT_COMMIT"" .'
          sh 'docker push yassinekhouaja/numeric-app:""$GIT_COMMIT""'
          }
        }
      }   
  }
}
