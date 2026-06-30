FROM mcr.microsoft.com/vs/buildtools:latest

RUN powershell -Command \
    Set-ExecutionPolicy Bypass -Scope Process -Force ; \
    Invoke-WebRequest https://aka.ms/vs/17/release/vs_buildtools.exe -OutFile vs_buildtools.exe ; \
    Start-Process vs_buildtools.exe -ArgumentList '--quiet --wait --norestart --nocache \
        --add Microsoft.VisualStudio.Workload.VCTools \
        --add Microsoft.VisualStudio.Component.Windows10SDK.19041 \
        --add Microsoft.VisualStudio.Workload.ManagedDesktop \
        --add Microsoft.VisualStudio.Workload.NetCoreTools' -NoNewWindow -Wait ; \
    Remove-Item vs_buildtools.exe

SHELL ["powershell.exe", "-Command"]
