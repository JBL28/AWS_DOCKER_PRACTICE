node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    withSonarQubeEnv('MySonarQube') {
      withCredentials([string(credentialsId: 'SONAR_TOKEN', variable: 'SONAR_TOKEN')]) {
          sh "./gradlew sonar -Dsonar.token=$SONAR_TOKEN"
      }
    }
  }
}