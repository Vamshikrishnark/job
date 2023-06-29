node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'm3';
    withSonarQubeEnv('sonarqube') {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=vasu -Dsonar.projectName='vasu'"
    }
  }
}
