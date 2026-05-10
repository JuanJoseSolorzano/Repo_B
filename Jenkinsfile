pipeline {

    agent {
        label 'windows11_machine'
    }

    environment {
        REPO_NAME = 'Powershell_Installer'
    }

    stages {

        stage('Repo2 Build') {
            steps {
                script {
                    def repo_root_path = "${env.WORKSPACE}/${env.REPO_NAME}"
                    if (fileExists(repo_root_path)){
                        deleteDir()
                    }
                    else {
                        powershell'''
                            git clone https://github.com/JuanJoseSolorzano/Powershell_Installer.git
                        '''
                    }
                }
            }
        }
    }
}