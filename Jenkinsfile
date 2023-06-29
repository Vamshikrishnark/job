node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'm3';
    withSonarQubeEnv('mysonar') {
      sh "${mvn}/bin/mvn -X clean verify sonar:sonar -Dsonar.host.url= http://localhost:9000 -Dsonar.login=admin -Dsonar.password=sonar -Dsonar.projectKey=vasu -Dsonar.projectName='vasu' "
    }
  }
}
