pipeline {
    tools{
        jdk 'myjdk'
    }
    agent none
    stages{
        stage('Git clone'){
            agent any
            steps{
               git 'https://github.com/Tom-cat-1/DevOpsClassCodes.git'
            }
        }
        
        stage('Gradle Compile') {
            steps {
               sh 'sudo chmod 777 ./gradlew' 
               sh './gradlew compileJava' 
            }

            agent any
          }
        
        stage('Gradle pmd') {
            steps {
               sh 'sudo chmod 777 ./gradlew' 
               sh './gradlew pmdMain' 
            }

            agent any
          }
        
        stage('Gradle test') {
            steps {
               sh 'sudo chmod 777 ./gradlew' 
               sh './gradlew test' 
            }

            agent any
          }
         
        stage('Gradle cc') {
            steps {
               sh 'sudo chmod 777 ./gradlew' 
               sh './gradlew jacocoTestReport'
               sh './gradlew jacocoTestCoverageVerification' 
            }

            agent any
          }
		
		
        stage('Gradle package') {
            steps {
               sh 'sudo chmod 777 ./gradlew' 
               sh './gradlew jar'
            }

            agent any
          }
    }
}
