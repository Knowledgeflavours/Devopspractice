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
    stage('Review'){
       withMaven(maven:'MyMaven'){
             sh 'mvn pmd:pmd'
         }
    }
    stage('Test'){
       withMaven(maven:'MyMaven'){
             sh 'mvn test'
         }
    }
    stage('Coverage'){
       withMaven(maven:'MyMaven'){
             sh 'mvn cobertura:cobertura -Dcobertura.report.format=xml'
         }
    }
    stage('Package'){
         withMaven(maven:'MyMaven'){
             sh 'mvn package'
         }
        
    }
}
