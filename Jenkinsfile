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
                    def repo_root_path = "${env.WORKSPACE}\\${env.REPO_NAME}"
                    echo "Repository path: ${repo_root_path}"
                    if (fileExists(repo_root_path)) {
                        echo "[!] - '${repo_root_path}' already exists. Removing..."
                        powershell """
                        Remove-Item -Path '${repo_root_path}' -Recurse -Force
                        """
                    }
                    powershell """
                    Set-Location '${env.WORKSPACE}'
                    git clone https://github.com/JuanJoseSolorzano/Powershell_Installer.git '${env.REPO_NAME}'
                    Set-Location '${repo_root_path}'
                    git checkout develop
                    gcc -g .\\main.c .\\lib\\fileio.c .\\lib\\helpers.c .\\lib\\sources\\icon.o -o powershell_installer.exe
                    """
                }
            }
        }
    }
}