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
     
     stage('Username') {
            steps {
                script {
                    def userInput = input message: 'Select the username credential', parameters: [credentials(credentialType: 'com.cloudbees.plugins.credentials.impl.UsernamePasswordCredentialsImpl', defaultValue: 'username_global_v_sep15_ID', description: 'username', name: 'username', required: false)]
                    echo "User selected: ${userInput}"
                }
            }
        }

        stage('Input Password') {
            steps {
                script {
                    def userInput = input message: 'Select the password', parameters: [password(defaultValue: 'abcd', description: 'Desc-password', name: 'Password')]
                    echo "User selected: ${userInput}"
                    
                }
            }
        }
        stage('multiline') {
            steps {
                script {
                    def userInput = input message: 'Select the multiline', parameters: [text(defaultValue: '''AA
                    SS
                    DD
                    FF
                    11
                    12''', name: 'multiline')]
                    echo "User selected: ${userInput}"
                    
                }
            }
        }
        stage('choice') {
            steps {
                script {
                    def userInput = input message: 'Select the choice', parameters: [choice(choices: ['AA', 'BB', '11', '22'], description: 'Choice selected', name: 'choice')]
                    echo "User selected: ${userInput}"
                    
                }
            }
        }
        
        stage('User Input for Run Parameter') {
            steps {
                script {
                   def userInput = input message: 'Select the build', parameters: [run(filter: 'ALL', name: 'RUN PARAMETER', projectName: 'Folder-Veronica/freestyle_buildPeriodically')]
                    echo "User selected build: ${userInput}"
                }
            }
        }
     stage('Input String') {
            steps {
                script {
                    def userInput = input message: 'Select the string', parameters: [string(defaultValue: 'abcd', description: 'desc-string', name: 'string')]
                    echo "User selected: ${userInput}"
                }
            }
        }
     stage('Input Text') {
            steps {
                script {
                    // Prompt the user for text input
                    def userInput = input message: 'Please enter some text:', parameters: [
                        string(name: 'UserInput', description: 'Enter your value here')
                    ]
                    echo "You entered: ${userInput}"
                }
            }
        }
   stage('Input Boolean') {
            steps {
                script {
                   def boo = input(message: 'Click to proceed', ok: 'Continue', parameters: [booleanParam(name: 'boolean')])
                   echo "${boo}"       
               } 
            }
        }
      
    }
    
}
