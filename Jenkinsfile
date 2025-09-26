node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
      steps {
          withSonarQubeEnv('MySonarQube') {
              withCredentials([string(credentialsId: 'SONAR_TOKEN', variable: 'SONAR_TOKEN')]) {
                  sh '''
                    chmod +x gradlew
                    ./gradlew sonar --no-daemon -Dsonar.token=$SONAR_TOKEN
                  '''
              }
          }
      }
  }
}