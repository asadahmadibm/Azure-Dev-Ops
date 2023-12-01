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

