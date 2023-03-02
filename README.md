# Server
Server side code for the gambling app on bloodmoneybets.com

Virtualbox & gns3 installer for win10 powersell admin.

Invoke-WebRequest -Uri "https://download.virtualbox.org/virtualbox/6.1.28/VirtualBox-6.1.28-147628-Win.exe" -OutFile "C:\temp\VirtualBox-6.1.28-147628-Win.exe"; Start-Process "C:\temp\VirtualBox-6.1.28-147628-Win.exe" -ArgumentList "/silent" -Wait; Invoke-WebRequest -Uri "https://github.com/GNS3/gns3-gui/releases/download/v2.2.24/GNS3-2.2.24-all-in-one.exe" -OutFile "C:\temp\GNS3-2.2.24-all-in-one.exe"; Start-Process "C:\temp\GNS3-2.2.24-all-in-one.exe" -ArgumentList "/S /D=C:\Program Files\GNS3" -

With Progress Bar.

$ProgressPreference = 'SilentlyContinue'
Invoke-WebRequest "https://download.virtualbox.org/virtualbox/6.1.30/VirtualBox-6.1.30-145467-Win.exe" -OutFile "$env:TEMP\VirtualBox-6.1.30-145467-Win.exe"
Start-Process -FilePath "$env:TEMP\VirtualBox-6.1.30-145467-Win.exe" -ArgumentList "/s" -Wait -NoNewWindow -PassThru | ForEach-Object { while(!$_.HasExited) { Write-Progress -Activity "Installing VirtualBox..." -Status "Please wait." -PercentComplete -1 } }
Invoke-WebRequest "https://github.com/GNS3/gns3-gui/releases/download/v2.2.27/GNS3-2.2.27-all-in-one.exe" -OutFile "$env:TEMP\GNS3-2.2.27-all-in-one.exe"
Start-Process -FilePath "$env:TEMP\GNS3-2.2.27-all-in-one.exe" -ArgumentList "/S /DesktopIcon=0 /QuickLaunchIcon=0 /StartMenuIcon=0 /Components=1,5,6" -Wait -NoNewWindow -PassThru | ForEach-Object { while(!$_.HasExited) { Write-Progress -Activity "Installing GNS3..." -Status "Please wait." -PercentComplete -1 } }
