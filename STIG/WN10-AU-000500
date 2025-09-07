<#
.SYNOPSIS
    This PowerShell script ensures that the maximum size of the Windows Application event log is at least 32768 KB (32 MB).

.NOTES
    Author          : Sir William
    LinkedIn        : linkedin.com/in/-----------/
    GitHub          : https://github.com/sirwilliam1
    Date Created    : 2025-09-06
    Last Modified   : 2025-09-06
    Version         : 1.0
    CVEs            : N/A
    Plugin IDs      : N/A
    STIG-ID         : WN10-AU-000500

.TESTED ON
    Date(s) Tested  : 
    Tested By       : 
    Systems Tested  : 
    PowerShell Ver. : 

.USAGE
    Put any usage instructions here.
    Example syntax:
    PS C:\> .\STIG-ID-WN10-AU-000500.ps1 
#>

# Define the registry path
$regPath = "HKLM:\SOFTWARE\Policies\Microsoft\Windows\EventLog\Application"

# Ensure the registry key exists
if (-not (Test-Path $regPath)) {
    New-Item -Path $regPath -Force
}

# Set the MaxSize value to 0x8000 (32768 in decimal)
Set-ItemProperty -Path $regPath -Name "MaxSize" -Value 32768 -Type DWord

# Confirm the change
Get-ItemProperty -Path $regPath | Select-Object MaxSize
