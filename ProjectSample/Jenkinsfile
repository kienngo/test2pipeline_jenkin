pipeline {
    agent any

    environment {
        dotnet = 'C:\\Program Files\\dotnet\\dotnet.exe'
    }

    stages {
        stage('Build') {
            steps {
				bat 'dotnet nuget add source https://pkgs.dev.azure.com/PJC-Dev-Organization/PJC-Dev-Prj/_packaging/PJC-Dev-Artifacts/nuget/v3/index.json -n PJC-Dev-Artifacts -u ngo.duc.kien@vhec.vn -p Kien@1996 --store-password-in-clear-text'
                bat 'dotnet build ProjectSample\\Wiseman.PJC.Service.GroupSettings.sln --configuration Release'
            }
        }

        stage('Test') {
            steps {
                bat 'dotnet test ProjectSample\\Wiseman.PJC.Service.GroupSettings.WebApi\\Wiseman.PJC.Service.GroupSettings.WebApi.csproj'
            }
        }

        stage('Release') {
            steps {
                bat 'dotnet build ProjectSample\\Wiseman.PJC.Service.GroupSettings.sln /p:PublishProfile=" ProjectSample\\Properties\\PublishProfiles\\FolderProfile.pubxml" /p:Platform="Any CPU" /p:DeployOnBuild=true /m'
            }
        }
    }
}
