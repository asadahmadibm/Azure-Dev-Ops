# Azure-Dev-Ops

    1- zulu8  must version 8
    2- full-text in sql
    3- install  azuredevops
        a- no participate
        b- new azure
        c- sql server instance test
        d- accout for azure devops  note : math with active directory
        e- edit ip and port for site setting
        f- add user for azure service


    new project
    copy repo link
    make directory in local
    cmd : git clone Linkaddress
    cmd : dotnet new sln --name ifb.FirstProject
    open vs
    new class library
    push

        
    new pipline
    other git
    empty job
    add new agent 
    goto project setting -> Agent Pool  -> default -> new agent
        download agent
        make directory agent -> cd agent
        cmd : Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$HOME\Downloads\vsts-agent-win-x64-2.213.2.zip", "$PWD")
        cmd : .\config.cmd
        cmd : .\run.cmd
    
    new pipline
    for make without yaml
        1-other git
        2- continue 
        3- emplty job
        4- save & run

        5- download .net 8 binary -> extract & copy to agent Directory
        6- for build that project by this .net : add task  powershell -> set to inline copy $(Agent.HomeDirectory)\dotnet-sdk-8.0.100-win-x64\dotnet.exe build "$(Build.SourcesDirectory)\ClassLibrary1\ClassLibrary1.csproj" --configuration Release -p:Version=1.0.$(Build.BuildNumber)
            for see all predinine azure seach this word in googgle
            note : sett pathproject in C:\agent\_work\1\s\ClassLibrary1

    for make nuget package from my project
        1- download nuget.exe & copy To c:\agent
        2- add task in job kind powershell -> inline -> $(Agent.HomeDirectory)\nuget\nuget.exe pack "$(Build.SourcesDirectory)\ClassLibrary1\ClassLibrary1.csproj" -OutputDirectory $(Build.SourcesDirectory)\Output\nugetPack\ClassLibrary1 -Properties Configuration=Release -Version4.0.$(Build.BuildNumber)

        to copy Copy-Item -Path C:\agent\_work\3\s\ConsoleApp1\bin\Debug -Destination C:\Backup -Recurse
        
     new pipline for .netframework 4.8
        for make without yaml
            1-other git
            2- continue 
            3- emplty job
            4- save & run        

            5- make msbuild job
            6- make powershell
                Copy-Item -Path "$(Build.SourcesDirectory)\IfbBrokersWebsite\App_Code" -Destination C:\publish_Azure$(Build.BuildNumber)\\App_Code -Recurse
                Copy-Item -Path "$(Build.SourcesDirectory)\IfbBrokersWebsite\Areas" -Destination C:\publish_Azure$(Build.BuildNumber) -Recurse
                Copy-Item -Path "$(Build.SourcesDirectory)\IfbBrokersWebsite\assets" -Destination C:\publish_Azure$(Build.BuildNumber) -Recurse
                Copy-Item -Path "$(Build.SourcesDirectory)\IfbBrokersWebsite\bin" -Destination C:\publish_Azure$(Build.BuildNumber) -Recurse
                Copy-Item -Path "$(Build.SourcesDirectory)\IfbBrokersWebsite\BourseReports" -Destination C:\publish_Azure$(Build.BuildNumber) -Recurse
                Copy-Item -Path "$(Build.SourcesDirectory)\IfbBrokersWebsite\Content" -Destination C:\publish_Azure$(Build.BuildNumber) -Recurse
                Copy-Item -Path "$(Build.SourcesDirectory)\IfbBrokersWebsite\css" -Destination C:\publish_Azure$(Build.BuildNumber) -Recurse
                Copy-Item -Path "$(Build.SourcesDirectory)\IfbBrokersWebsite\fonts" -Destination C:\publish_Azure$(Build.BuildNumber) -Recurse
                Copy-Item -Path "$(Build.SourcesDirectory)\IfbBrokersWebsite\Images" -Destination C:\publish_Azure$(Build.BuildNumber) -Recurse
                Copy-Item -Path "$(Build.SourcesDirectory)\IfbBrokersWebsite\Plugins" -Destination C:\publish_Azure$(Build.BuildNumber) -Recurse
                Copy-Item -Path "$(Build.SourcesDirectory)\IfbBrokersWebsite\Scripts" -Destination C:\publish_Azure$(Build.BuildNumber) -Recurse
                Copy-Item -Path "$(Build.SourcesDirectory)\IfbBrokersWebsite\Templates" -Destination C:\publish_Azure$(Build.BuildNumber) -Recurse
                Copy-Item -Path "$(Build.SourcesDirectory)\IfbBrokersWebsite\Views" -Destination C:\publish_Azure$(Build.BuildNumber) -Recurse
                Copy-Item -Path "$(Build.SourcesDirectory)\IfbBrokersWebsite\wwwroot" -Destination C:\publish_Azure$(Build.BuildNumber) -Recurse
                Copy-Item -Path "$(Build.SourcesDirectory)\IfbBrokersWebsite\favicon.ico" -Destination C:\publish_Azure$(Build.BuildNumber) -Recurse
                Copy-Item -Path "$(Build.SourcesDirectory)\IfbBrokersWebsite\Global.asax" -Destination C:\publish_Azure$(Build.BuildNumber) -Recurse
                Copy-Item -Path "$(Build.SourcesDirectory)\IfbBrokersWebsite\libman.json" -Destination C:\publish_Azure$(Build.BuildNumber) -Recurse

        
        
