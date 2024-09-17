pipeline{
    agent any

    stages{
        stage('Checkout code'){
            steps{
                checkout scmGit (branches: [[name:'*/master']], extensions: [], userRemoteConfigs:[[url: 'https://github.com/yrrk/addressbook.git']])
            }           
        }
        // stage('Install Maven Build Tool'){
        //     steps{
        //         dir('/home/jenkins'){
        //             sh 'wget --no-check-certificate https://dlcdn.apache.org/maven/maven-3/3.9.4/binaries/apache-maven-3.9.4-bin.tar.gz'
        //             sh 'tar -xzvf /home/jenkins/apache-maven-3.9.4-bin.tar.gz'
        //         }
        //     }
        // }
        stage('Compile Sample application'){
            steps{
                dir('/home/jenkins/workspace/project1'){
                    sh '/home/jenkins/apache-maven-3.9.4/bin/mvn compile -Dmaven.wagon.http.ssl.insecure=true -Dmaven.wagon.http.ssl.allowall=true'
                }
            }
        }
        // stage('Package Sample Application'){
        //     steps{
        //         dir('/home/jenkins/workspace/project1'){
        //             sh '/home/jenkins/apache-maven-3.9.4/bin/mvn package'
        //         }
        //     }
        // }
        // stage('Install tomcat'){
        //     steps{
        //         dir('/home/jenkins'){
        //             //sh 'wget https://archive.apache.org/dist/tomcat/tomcat-8/v8.5.24/bin/apache-tomcat-8.5.24.tar.gz'
        //             //sh 'tar -xzvf apache-tomcat-8.5.24.tar.gz'
        //         }
        //     }
        // }
        // stage("Deploy Sample Application to Tomcat Server") {
        //     steps {
        //         sh 'sudo cp /home/jenkins/workspace/project1/target/addressbook-2.0.war /home/jenkins/apache-tomcat-8.5.24/webapps/'
                
        //     }
        // }
    }
}