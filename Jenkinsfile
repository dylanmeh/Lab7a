pipeline {
    agent {
        kubernetes {
            yaml '''
apiVersion: v1
kind: Pod
spec:
  containers:
  - name: shell
    image: ubuntu
    command:
    - sleep
    args:
    - infinity
'''
            defaultContainer 'shell'
        }
    }
    stages {
        stage('echo value1') {
            steps {
                script {
                    def var1 = 'value1'
                    echo "print ${var1}"
                }    
            }        
        }
    }
}