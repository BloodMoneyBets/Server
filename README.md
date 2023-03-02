# Server
Server side code for the gambling app on bloodmoneybets.com

Virtualbox & gns3 installer for win10 powersell admin.

$ProgressPreference = 'SilentlyContinue'
Invoke-WebRequest "https://download.virtualbox.org/virtualbox/6.1.30/VirtualBox-6.1.30-145467-Win.exe" -OutFile "$env:TEMP\VirtualBox-6.1.30-145467-Win.exe"
Start-Process -FilePath "$env:TEMP\VirtualBox-6.1.30-145467-Win.exe" -ArgumentList "/s" -Wait -NoNewWindow -PassThru | ForEach-Object { while(!$_.HasExited) { Write-Progress -Activity "Installing VirtualBox..." -Status "Please wait." -PercentComplete -1 } }
Invoke-WebRequest "https://github.com/GNS3/gns3-gui/releases/download/v2.2.27/GNS3-2.2.27-all-in-one.exe" -OutFile "$env:TEMP\GNS3-2.2.27-all-in-one.exe"
Start-Process -FilePath "$env:TEMP\GNS3-2.2.27-all-in-one.exe" -ArgumentList "/S /DesktopIcon=0 /QuickLaunchIcon=0 /StartMenuIcon=0 /Components=1,5,6" -Wait -NoNewWindow -PassThru | ForEach-Object { while(!$_.HasExited) { Write-Progress -Activity "Installing GNS3..." -Status "Please wait." -PercentComplete -1 } }
