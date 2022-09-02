pipeline {
    // add your slave label name
   //agent { label 'my_slave1'}
   agent any
    tools{
        maven '/opt/apache-maven-3.8.6'
    }
    stages {
        stage ('Checkout SCM') {

            steps {
                            git branch: 'main', url: 'https://github.com/ravirekha/Devops_July.git'
            }
        }

        stage ('Build') {

            steps {
               sh 'mvn clean package'
            }
        }

        stage ('deploy') {

            steps {
               // update your tomcat server ip accordingly in below command
               sh "scp target/maven-web-application.war  ec2-user@13.126.156.225:/opt/tomcat9/webapps/"


            }
        }


    }
}

