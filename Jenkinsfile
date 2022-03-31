pipeline {
  agent any

  stages {
      stage('Build Artifact') {
            steps {
              sh "mvn clean package -DskipTests=true"
              archive 'target/*.jar'  // hello Rizwan
            }
        }  
      stage('Unit Tests -Junit and Jacoco') {
            steps {
              sh "mvn test"
            }
            post{
              always{
                  junit '  target/surefire-report/*.xml'
                  Jacoco execPatter: 'target/jacoco.exec'
                  }
        
                }
        
    }
}
