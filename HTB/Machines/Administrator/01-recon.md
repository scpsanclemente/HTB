1: Ldap enum

2:- Active Directory

3: Pass the hash

4: privileges escalated

---
## Information Recon

Ports tcp open in nmap format

```bash
PORT      STATE SERVICE          REASON
21/tcp    open  ftp              syn-ack ttl 127
53/tcp    open  domain           syn-ack ttl 127
88/tcp    open  kerberos-sec     syn-ack ttl 127
135/tcp   open  msrpc            syn-ack ttl 127
139/tcp   open  netbios-ssn      syn-ack ttl 127
389/tcp   open  ldap             syn-ack ttl 127
445/tcp   open  microsoft-ds     syn-ack ttl 127
464/tcp   open  kpasswd5         syn-ack ttl 127
593/tcp   open  http-rpc-epmap   syn-ack ttl 127
636/tcp   open  ldapssl          syn-ack ttl 127
3268/tcp  open  globalcatLDAP    syn-ack ttl 127
3269/tcp  open  globalcatLDAPssl syn-ack ttl 127
5985/tcp  open  wsman            syn-ack ttl 127
9389/tcp  open  adws             syn-ack ttl 127
47001/tcp open  winrm            syn-ack ttl 127
49664/tcp open  unknown          syn-ack ttl 127
49665/tcp open  unknown          syn-ack ttl 127
49666/tcp open  unknown          syn-ack ttl 127
49667/tcp open  unknown          syn-ack ttl 127
49668/tcp open  unknown          syn-ack ttl 127
51915/tcp open  unknown          syn-ack ttl 127
51918/tcp open  unknown          syn-ack ttl 127
51923/tcp open  unknown          syn-ack ttl 127
51926/tcp open  unknown          syn-ack ttl 127
51943/tcp open  unknown          syn-ack ttl 127
51975/tcp open  unknown          syn-ack ttl 127
```

Ports services and versions nmap format

```bash
➜  nmap sudo nmap -sCV -p 21,53,88,135,139,389,445,464,593,636,3268,3269,5985,9389,47001,49664,49665,49666,49667,49668,51915,51918,51923,51926,51943,51975 administrator.htb 
Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-12-17 16:20 CET
Stats: 0:00:38 elapsed; 0 hosts completed (1 up), 1 undergoing Service Scan
Service scan Timing: About 61.54% done; ETC: 16:21 (0:00:23 remaining)
Stats: 0:01:00 elapsed; 0 hosts completed (1 up), 1 undergoing Service Scan
Service scan Timing: About 96.15% done; ETC: 16:21 (0:00:02 remaining)
Stats: 0:01:08 elapsed; 0 hosts completed (1 up), 1 undergoing Script Scan
NSE Timing: About 98.50% done; ETC: 16:21 (0:00:00 remaining)
Nmap scan report for administrator.htb (10.10.11.42)
Host is up (0.040s latency).

PORT      STATE SERVICE       VERSION
21/tcp    open  ftp           Microsoft ftpd
| ftp-syst: 
|_  SYST: Windows_NT
53/tcp    open  domain        Simple DNS Plus
88/tcp    open  kerberos-sec  Microsoft Windows Kerberos (server time: 2024-12-17 22:20:51Z)
135/tcp   open  msrpc         Microsoft Windows RPC
139/tcp   open  netbios-ssn   Microsoft Windows netbios-ssn
389/tcp   open  ldap          Microsoft Windows Active Directory LDAP (Domain: administrator.htb0., Site: Default-First-Site-Name)
445/tcp   open  microsoft-ds?
464/tcp   open  kpasswd5?
593/tcp   open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
636/tcp   open  tcpwrapped
3268/tcp  open  ldap          Microsoft Windows Active Directory LDAP (Domain: administrator.htb0., Site: Default-First-Site-Name)
3269/tcp  open  tcpwrapped
5985/tcp  open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
9389/tcp  open  mc-nmf        .NET Message Framing
47001/tcp open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
49664/tcp open  msrpc         Microsoft Windows RPC
49665/tcp open  msrpc         Microsoft Windows RPC
49666/tcp open  msrpc         Microsoft Windows RPC
49667/tcp open  msrpc         Microsoft Windows RPC
49668/tcp open  msrpc         Microsoft Windows RPC
51915/tcp open  msrpc         Microsoft Windows RPC
51918/tcp open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
51923/tcp open  msrpc         Microsoft Windows RPC
51926/tcp open  msrpc         Microsoft Windows RPC
51943/tcp open  msrpc         Microsoft Windows RPC
51975/tcp open  msrpc         Microsoft Windows RPC
Service Info: Host: DC; OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:
|_clock-skew: 7h00m16s
| smb2-security-mode: 
|   3:1:1: 
|_    Message signing enabled and required
| smb2-time: 
|   date: 2024-12-17T22:21:49
|_  start_date: N/A


```


---
para empezar con la maquina nos dan credenciales de acceso principal:
![[Pasted image 20241217162401.png]]

Empezamos con el user ==Olivia==  y pass ==ichliebedich== 
## Enumeration

## LDAP

```java
El **Lightweight Directory Access Protocol (LDAP)** 
es un protocolo utilizado para administrar informacion dentro del direcotio activo, se usa principalmente para buscar o modificar data dentro del Active Directory.
```

Vamos a enumerar el servidor ldap, gracias a que tenemos credenciales podemos ver a que carpetas tenemos acceso en el directorio activo.

### Crackmapexec

```bash
map sudo  crackmapexec smb 10.10.11.42 -u Olivia -p 'ichliebedich' --shares   
```

SMB         10.10.11.42     445    DC               [*] Windows Server 2022 Build 20348 x64 (name:DC) (domain:administrator.htb) (signing:True) (SMBv1:False)
SMB         10.10.11.42     445    DC               [+] administrator.htb\Olivia:ichliebedich 
SMB         10.10.11.42     445    DC               [+] Enumerated shares
SMB         10.10.11.42     445    DC               Share           Permissions     Remark
SMB         10.10.11.42     445    DC               -----           -----------     ------
SMB         10.10.11.42     445    DC               ADMIN$                          Remote Admin
SMB         10.10.11.42     445    DC               C$                              Default share
SMB         10.10.11.42     445    DC               IPC$            READ            Remote IPC
SMB         10.10.11.42     445    DC               NETLOGON        READ            Logon server share 
SMB         10.10.11.42     445    DC               SYSVOL          READ            Logon server share 

### Winrm
otro buen reconocimiento es ver si tenemos acceso a Winrm (remote windows manager) Depende de como este configurado el directorio activo  podemos tener permisos para acceder a dispositivos en remoto

```bash
netexec winrm 10.10.11.42 -u olivia -p ichliebedich
```

[*] First time use detected
[*] Creating home directory structure
[*] Creating missing folder logs
[*] Creating missing folder modules
[*] Creating missing folder protocols
[*] Creating missing folder workspaces
[*] Creating missing folder obfuscated_scripts
[*] Creating missing folder screenshots
[*] Creating default workspace
[*] Initializing LDAP protocol database
[*] Initializing FTP protocol database
[*] Initializing WINRM protocol database
[*] Initializing WMI protocol database
[*] Initializing SSH protocol database
[*] Initializing SMB protocol database
[*] Initializing RDP protocol database
[*] Initializing MSSQL protocol database
[*] Initializing NFS protocol database
[*] Initializing VNC protocol database
[*] Copying default configuration file
WINRM       10.10.11.42     5985   DC               [*] Windows Server 2022 Build 20348 (name:DC) (domain:administrator.htb)
/usr/lib/python3/dist-packages/spnego/_ntlm_raw/crypto.py:46: CryptographyDeprecationWarning: ARC4 has been moved to cryptography.hazmat.decrepit.ciphers.algorithms.ARC4 and will be removed from this module in 48.0.0.
  arc4 = algorithms.ARC4(self._key)
WINRM       10.10.11.42     5985   DC               [+] administrator.htb\olivia:ichliebedich (Pwn3d!)

Tenemos acceso por winrm a la maquina

Vamos a usar evil-winrm para acceder a la maquina con las credenciales proporcionadas

```java
evil-winrm -u Olivia -p ichliebedich -i 10.10.11.42
                                        
Evil-WinRM shell v3.7
                                        
Warning: Remote path completions is disabled due to ruby limitation: quoting_detection_proc() function is unimplemented on this machine
                                        
Data: For more information, check Evil-WinRM GitHub: https://github.com/Hackplayers/evil-winrm#Remote-path-completion
                                        
Info: Establishing connection to remote endpoint
*Evil-WinRM* PS C:\Users\olivia\Documents> whoami
administrator\olivia
*Evil-WinRM* PS C:\Users\olivia\Documents> 

```

Con evil-winrm podemos obtener recon de usuarios con la herramienta bloodhound
```java

netexec ldap 10.10.11.42 -u Olivia -p ichliebedich --bloodhound --collection All --dns-server 10.10.11.42



SMB         10.10.11.42     445    DC               [*] Windows Server 2022 Build 20348 x64 (name:DC) (domain:administrator.htb) (signing:True) (SMBv1:False)
LDAP        10.10.11.42     389    DC               [+] administrator.htb\Olivia:ichliebedich 
LDAP        10.10.11.42     389    DC               Resolved collection methods: objectprops, trusts, dcom, localadmin, session, psremote, container, group, rdp, acl
[16:40:31] ERROR    Unhandled exception in computer dc.administrator.htb processing: The NETBIOS connection with the remote host timed out.                                                  computers.py:269
LDAP        10.10.11.42     389    DC               Done in 00M 07S
LDAP        10.10.11.42     389    DC               Compressing output into /home/kali/.nxc/logs/DC_10.10.11.42_2024-12-17_164024_bloodhound.zip


```

---

