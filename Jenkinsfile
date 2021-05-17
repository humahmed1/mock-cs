pipeline {
    agent any
    tools {
        maven 'maven_3_8_1'
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package -f cmp-mock-customer-cs/pom.xml'
            }
        }
        stage('Unit Test') {
            steps {
                sh 'mvn -Dtest=RetailCustomerApplicationTest test -f cmp-mock-customer-cs/pom.xml'
            }
            post {
                always {
                    junit 'cmp-mock-customer-cs/target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deploy and Run') {
            steps {

            }
        }
        stage('Integration Test') {
            steps{
                sh 'mvn -Dtest=api-automation/src/test/java/com/example/cs/CsKarateRunner -DfailIfNoTests=false test -f api-automation/pom.xml'
            }
        }
    }
}