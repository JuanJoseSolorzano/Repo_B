pipeline {

    agent {
        label 'windows11_machine'
    }

    stages {

        stage('Repo2 Build') {
            steps {
                powershell'''
                    Write-Host $env:WORKPACE
                    git clone https://github.com/JuanJoseSolorzano/Powershell_Installer.git
                '''
                
            }
        }
    }
}