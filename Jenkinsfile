#!/usr/bin/env groovy
import hudson.model.*
import hudson.EnvVars
import java.net.URL 

node {
    stage('Git Checkout'){
        git 'https://github.com/jamunakan2307/demo-be.git'
    }
    
    stage('Compile Code'){
        withMaven(maven: 'Maven'){
            sh 'mvn compile'
        }
        
    }
    
    stage('Test Code'){
         withMaven(maven: 'Maven'){
            sh 'mvn test'
        }
    }
    post { 
        always { 
            junit 'target/surefire-reports/TEST-com.grokonez.jwtauthentication.TestBootUp.xml'
        }
    }
    
    
     stage('Test Package'){
         withMaven(maven: 'Maven'){
            sh 'mvn package'
        }
    }
}
