#!/usr/bin/env groovy
/*
 *    This for comment section only !
 *    
 */
import hudson.model.*
import hudson.EnvVars
import groovy.json.JsonSlurperClassic
import groovy.json.JsonBuilder
import groovy.json.JsonOutput
import java.net.URL


node {
stage ('checkout scm') {
        cleanWs()  
        git branch: "${params.Branch}", url: 'https://github.com/forpix/Java-Example.git'
        checkout scm
    }
stage ('lets give a check') {
if (branch == 'master') {
echo 'we are in master branch'
     }else 
{
        echo 'since the job is running on not master'
        currentBuild.result = 'UNSTABLE'
        post
        
}
        
}
stage ('build the Job') {
if (branch == 'working') {
echo 'we are in working branch'
        sh 'pwd;ls -a'
        
    }
}
}
