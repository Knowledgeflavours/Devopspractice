#!/usr/bin/env groovy
import hudson.model.*
import hudson.EnvVars
import java.net.URL

node{
    stage('Code checkout'){
       git 'https://github.com/Knowledgeflavours/Devopspractice.git'
        
    }
    stage('Build'){
         withMaven(maven:'MyMaven'){
             sh 'mvn compile'
         }
        
    }
    stage('Package'){
         withMaven(maven:'MyMaven'){
             sh 'mvn package'
         }
        
    }
}
