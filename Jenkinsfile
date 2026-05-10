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
                        echo "[!] - The '${repo_root_path}' already exists. It will be removed ... "
                        deleteDir()
                    }
                    else {
                        powershell'''
                            git clone https://github.com/JuanJoseSolorzano/Powershell_Installer.git
                            Set-Location "${repo_root_path}"
                            Get-ChildItem .
                        '''

                    }
                }
            }
        }
    }
}