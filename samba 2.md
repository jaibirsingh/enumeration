# Samba 2

* To check which ports are running SMB ---> `nmap [IP] -sV`
* Then run a null session in rpcclient: `rpcclient [IP] -U "" -N`  ---> where we passes an empty string for the username and tell the processor that it is a null session and start RPC client without asking for any credentials.
*  **enum4linux** : `enum4linux [IP] -o` ---> -o for the information about operating system.
*  To know about the SMB protocol and dialects: `nmap [IP] -p 445 --script smb-protocols`
*  Better way to know the SMB and dialects' version is through : msfconsole --> use auxiliary/scanner/smb/smb2 --> set rhosts [IP] --> run

## Different ways to enumerate users
*  Scripts for enumerating users with SMB and nmap: `nmap [IP] -p 445 --script smb-enum-users`
*  With enum4linux: `enum4linux -U [IP]`
*  With rpcclient: `rpcclient -U "" -N [IP] and then inside rpcclient: `enumdomusers`
*  **Way to find admins on the target system:** Inside the rpcclient ---> `lookupnames admin`
