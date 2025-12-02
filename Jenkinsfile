node(){
    def mavenHome = tool name: 'maven3.9.11'
    //properties([[$class: 'RebuildSettings', autoRebuild: false, rebuildDisabled: false], pipelineTriggers([pollSCM('* * * * *')])])
    stage('CheckoutCode'){
        git branch: 'development', url: 'https://github.com/Suresh-DevOps-Learning/maven-web-application.git'
    }
    stage('Build'){
        sh "${mavenHome}/bin/mvn clean package"
    }
    /*
    stage('ExecureSonarQubeReport'){
        sh "${mavenHome}/bin/mvn clean sonar:sonar"
    }
    stage('UploadArtifactsintoNexus'){
        sh "${mavenHome}/bin/mvn clean deploy"
    }
    stage('DeployintoTomcat'){
        sshagent(['c991194c-2644-4fde-a65e-6ef05a5ade3a']) {
        sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@172.31.4.1:/opt/apache-tomcat-9.0.108/webapps/"
    }
    }
    */
}
