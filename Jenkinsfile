#!/usr/bin/env groovy

def app=""
def env=""

node {
    
    stage('Clone sources') {
        git url: 'https://github.com/OpenMake-Software/Uptime-Application.git'
    }
				
    stage ('Integration') {
				  def lines=readFile('Deployfile').trim().split("\n");
						app=lines[1].split(':')[1].trim()
						env=lines[2].split(':')[1].trim()						
						
      echo "**********************************************************************************"    
      echo "* Deploying $app to Integration"
      echo "**********************************************************************************"
      sh "mkdir -p output"
      
      echo "**********************************************************************************"
      echo "* Running Testcases for $app in Integration"
      echo "**********************************************************************************"
      sh "mkdir -p output"
				}		
    
    stage ('QA') {
      echo "**********************************************************************************"    
      echo "* Moving $app from Integration to QA"
      echo "**********************************************************************************"
      sh "mkdir -p output"						    
        
      echo "**********************************************************************************"        
      echo "* Deploying $app to QA"
      echo "**********************************************************************************"
      sh "mkdir -p output"

      echo "**********************************************************************************"    
      echo "* Running Testcases for $app in QA"
      echo "**********************************************************************************"    
      sh "mkdir -p output"
    }
				
    stage ('Production') {
      echo "**********************************************************************************"    
      echo "* Moving $app from QA to Prod"
      echo "**********************************************************************************"    
      sh "mkdir -p output"

      echo "**********************************************************************************"        
      echo "* Deploying $app to Prod"
      echo "**********************************************************************************"
      sh "mkdir -p output"
    }
}
