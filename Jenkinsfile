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
if (env.BRANCH_NAME == 'master') {
echo 'we are in master branch'
     } 
stage ('build the Job') {
if (env.BRANCH_NAME == 'working') {
echo 'we are in working branch'
    }
stage("test") {
       echo 'jobs are completed'
    }
}
