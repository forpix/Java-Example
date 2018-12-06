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
    timestamps()
   
 
node {
       
stage '\u2756  git checkout scm'
     cleanWs()  
    sh 'ls -a'
     
        echo'______________________________________________________________________________________________________'
        def scmVars = checkout scm
       
        echo'______________________________________________________________________________________________________'
        echo 'scm : the commit id is ' +scmVars.GIT_COMMIT
        echo 'scm : the commit branch  is ' +scmVars.GIT_BRANCH
        echo 'scm : the previous commit id is ' +scmVars.GIT_PREVIOUS_COMMIT
       sh 'ls -a'
       sh '''
       git log --oneline -1 ${GIT_COMMIT} 
       git log --format="medium" -1 ${GIT_COMMIT} 
       '''
       echo '========= ================== ================== =============== =========== = ===================='
       echo '${BRANCH_NAME}'
       sh  '${GIT_COMMIT}'
         
           sh '$GIT_BRANCH'
       
stage '\u2756 Second stage'
         sh 'ls -a'
       echo'====  This is other form ===='
       def shrtCommit = sh(returnStdout: true, script: "git log -n 1 --pretty=format:'%h'")
       echo " the commit is'${shrtCommit}' "
        
       def commitBranch = sh(returnStdout: true, script: "git name-rev --name-only HEAD")
       echo " the Branch is'${commitBranch}'"
        
       def commitEmail = sh(returnStdout: true, script: "git --no-pager show -s --format=\'%ae\'")
       echo " the commiter email is'${commitEmail}'"
        
       def commitName = sh(returnStdout: true, script: "git --no-pager show -s --format=\'%an\'")
       echo " the commiter name is'${commitName}'"
        
stage '\u2756 Third stage'
       
       echo'===  This is from shell command in to varible ===='
       sh 'git rev-parse HEAD > GIT_COMMIT'
       def shortCommite = readFile('GIT_COMMIT')
       echo "new way of fetching the Commit Id:'${shortCommite}'"
        
       sh "git rev-parse --abbrev-ref HEAD > GIT_BRANCHH"
       def GIT_BRANCHH = readFile('GIT_BRANCHH')
       echo "new way of fetching the Commit Id:'${GIT_BRANCHH}'"
        
stage '\u2756 Fourth stage'
            echo 'simple stage'    
      }
