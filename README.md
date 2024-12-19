# configuration_active_directory_ansible

# Prerequisites for Executing the Playbook: Configuring SSH on Windows Server
Before executing the playbook, you need to configure SSH on your Windows Server using the following PowerShell commands:
#1-Get-WindowsCapability -Online | Where-Object Name -like 'OpenSSH*'
#2-Add-WindowsCapability -Online -Name OpenSSH.Client~~~~0.0.1.0

#3-Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0
#4-Start-Service sshd
#5 
if (!(Get-NetFirewallRule -Name "OpenSSH-Server-In-TCP" -ErrorAction SilentlyContinue | Select-Object Name, Enabled)) {
    Write-Output "Firewall Rule 'OpenSSH-Server-In-TCP' does not exist, creating it..."
    New-NetFirewallRule -Name 'OpenSSH-Server-In-TCP' -DisplayName 'OpenSSH Server (sshd)' -Enabled True -Direction Inbound -Protocol TCP -Action Allow -LocalPort 22
} else {
    Write-Output "Firewall rule 'OpenSSH-Server-In-TCP' has been created and exists."
}


