pipeline{
    agent any
    options {
        skipDefaultCheckout true
    }
    stages{
        stage('SCM'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/jyotissingh14/maven-multi-module-example.git']]])
                
            }
        }
     stage('BUILD'){
            steps{
                sh '/opt/maven/bin/mvn clean package -Dmaven.test.skip=true'
                }
                }
              
        stage('RELEASE') {
            steps{
                sh '/opt/maven/bin/mvn --batch-mode release:clean release:prepare release:perform'
                            }
        }
        stage('GIT PUSH'){
            steps{  
               sh 'git push https://jyotissingh14:Brooklyn1412@github.com/jyotissingh14/maven-multi-module-example.git HEAD:master'
            }}
            }}
