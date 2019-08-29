stage('Build & Unit Test'){
  sh 'mvn clean verify -DskipITs=true';
  junit '**/target/surefire-reports/TEST-*.xml'
  archive 'target/*.jar'
}
