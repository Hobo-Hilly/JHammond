In this series I will be following the John Hammond Windows Active Directory series via YouTube.
I do not have the resources he has so my resource allocation will be different
He is using VM-Workstation pro. I will be using windows Hyper-V
# Goals
We are looking to build our own home lab for Pentesting and Ethical hacking. 

# Video #1
-   Setting up Environent

1. Best Practice to make a folder for all of your VM's to stay organized
''
- This PC > Files > NFS > ISO's
- The ISO's I am using: Windows Server 2019
                        Windows 11 Demo Version (Included with Hyper-V)

# Optionally you can put your VM's up in a network file share or on a hardrive/Jump Drive etc.. 

''

2. Creating a local admin user. Just wanted to create an admin user other than the one that Windows Auto creates for us.

NOTE: That in the installation that comes with Hyper-V(As in I used Quick add and selected the Windows 11 Dev Env.) Has multiple users already created. I am guessing this is because this is a "DEVELOPERS'" Image (ISO)
''

$Password = Read-Host -AsSecureString
New-LocalUser "User03" -Password $Password -FullName "Third User" -Description "Description of this account."
Name    Enabled  Description
----    -------  -----------
User03  True     Description of this account. 

''


01 Installing the Domain Controller
Use sconfig to:

Change the hostname
Change the IP address to static
Change the DNS server to our own IP address
Install the Active Directory Windows Feature

  Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
# Get-NetIPAddress
  Joining the Workstation to the domain
# Add-Computer -Domainname xyz.com -Credential xyz\Administrator -Force -Restart





