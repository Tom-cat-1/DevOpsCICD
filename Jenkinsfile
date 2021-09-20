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
               gradle 'compileJava'
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
