pipeline{
    agent any
    stages{
        stage('SCM'){
            steps{
                git 'https://github.com/jyotissingh14/maven-multi-module-example.git'
            }
        }
     stage('BUILD'){
            steps{
                sh '/opt/maven/bin/mvn clean package -Dmaven.test.skip=true'
                }
                }
              
        stage('RELEASE') {
            steps{
                sh '/opt/maven/bin/mvn --batch-mode release:clean release:prepare release:perform -DreleaseVersion=6.2 -DdevelopmentVersion=1.7-SNAPSHOT'
                            }
        }
        stage('GIT PUSH'){
            steps{  
               sh 'git push https://jyotissingh14:Brooklyn1412@github.com/jyotissingh14/maven-multi-module-example.git HEAD:master'
            }}
            }}
