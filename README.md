# printnightmare
# This is a group of Powershell scripts I used to block the printnightmare vulnerability.


# spooler-stop-disable-printnightmare.ps1
# The first script stops and disables the print spooler service. This should be run on member servers. Can be used remotely by running the following PS command:
# PS> Invoke-Command -FilePath .\spooler-stop-disable-printnightmare.ps1 -ComputerName *server01, server02*

# Deny-system-spooler-driver-directory.ps1
# This script should be run on the Windows print server. What it does is set DENY access to SYSTEM to the c:\windows\system32\spool\driver directory which is used to expolit this
# vulnerability. For more information, please see: https://blog.truesec.com/2021/06/30/fix-for-printnightmare-cve-2021-1675-exploit-to-keep-your-print-servers-running-while-a-patch-is-not-available/
# credit: Fabio Viggiani

# allow-system-spooler-driver-directory.ps1
# This script reverses the one mentioned above in case access needs to be restored.
# credit: Fabio Viggiani