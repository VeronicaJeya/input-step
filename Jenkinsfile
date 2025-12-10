pipeline {
    agent any
    stages {

         stage('Git Checkout') { 
            steps {                     
                   
                 git branch: 'build1', credentialsId: 'ssh_dec5_v_ID', url: 'https://github.com/VeronicaJeya/input-step.git'                 
                   
                   
            }
        }  
        stage('Input secret file') {
            steps {
                script {
                    def userInput = input message: 'Select the credential', parameters: [credentials(credentialType: 'org.jenkinsci.plugins.plaincredentials.impl.FileCredentialsImpl', defaultValue: 'secretfile_global_v_sep15_ID', description: 'secret_file', name: 'secret_file', required: false)]
                    echo "User selected build: ${userInput}"
                }
            }
        }
        stage('Input secret text') {
            steps {
                script {
                    def userInput = input message: 'Select the credential', parameters: [credentials(credentialType: 'org.jenkinsci.plugins.plaincredentials.impl.StringCredentialsImpl', defaultValue: 'secrettext_global_v_sep15_ID', name: 'secrettext', required: false)]
                echo "User selected build: ${userInput}"   
                
                }
            }
        }
    stage('Input ssh') {
            steps {
                script {
                    def userInput = input message: 'Select the credential', parameters: [credentials(credentialType: 'com.cloudbees.jenkins.plugins.sshcredentials.impl.BasicSSHUserPrivateKey', defaultValue: 'ssh_global_sep15_v_ID', description: 'ssh_global_sep15_v_ID', name: 'username', required: false)]
                    echo "User selected: ${userInput}"
                }
            }
        } 
     stage('Input Certificate') {
            steps {
                script {
                    def userInput = input message: 'Select the credential', parameters: [credentials(credentialType: 'com.cloudbees.plugins.credentials.impl.CertificateCredentialsImpl', defaultValue: 'certificate_global_v_ID', description: 'certificate_global_v_sep15_ID', name: 'certificate', required: false)]
                    echo "User selected: ${userInput}"
                    
                }
            }
        } 
     stage('Username') {
            steps {
                script {
                    def userInput = input message: 'Select the username credential', parameters: [credentials(credentialType: 'com.cloudbees.plugins.credentials.impl.UsernamePasswordCredentialsImpl', defaultValue: 'username_global_v_sep15_ID', description: 'username', name: 'username', required: false)]
                    echo "User selected: ${userInput}"
                }
            }
        }
      
    }
    
}
