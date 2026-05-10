pipeline {

    agent {
        label 'windows11_machine'
    }

    stages {

        stage('Repo2 Build') {
            steps {
                powershell'''
                    Write-Host "Workspace: Test"
                    Write-Host $env:WORKSPACE
                    git clone https://github.com/JuanJoseSolorzano/Powershell_Installer.git
                '''
                
            }
        }
    }
}