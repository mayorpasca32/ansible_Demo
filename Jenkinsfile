pipeline{
  agent any  
  stages{  
     
      stage('Git checkout') {
            steps {
                git branch: 'main', credentialsId: '', url: 'https://github.com/mayorpasca32/ansible_Demo.git'
            }
        }
      stage("Run an ansible playbook"){
        steps{
          ansiblePlaybook credentialsId: 'ssh-key', disableHostKeyChecking: true, inventory: 'hosts', playbook: 'ansible_playbook.yaml', vaultTmpPath: ''
        }
      }
      stage("Print Installation Is Complete"){
        steps{
           sh"echo Your Installation Was Successful  On All Servers"
        }
      }
  }
}
