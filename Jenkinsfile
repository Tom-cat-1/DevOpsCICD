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
               sh './gradlew compile' 
            }

            agent {
              label 'linux_agent'
            }

            tools {
              gradle 'mygradle'
            }
          }
    }
}
