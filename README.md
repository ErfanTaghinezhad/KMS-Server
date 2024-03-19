# KMS-Server
### Setting up the KMS-activation server:
A KMS (Key Management Service) server is a software service provided by Microsoft for activating Microsoft software products, especially Windows and Office. This service runs within your organizational network (usually LAN) and helps various clients on the network to automatically activate Windows and Office without the need to enter product keys manually.

In essence, the KMS Server is responsible for managing product keys of software products, and clients within the network can utilize this service to activate products automatically without the need for manual product key entry.


## Windows activation using KMS
To activate Windows products, first run cmd/PowerShell with admin store access and then use the following commands to activate Windows:
Cmd/PoweShell (run as administrator):
### Command 1: 'Slmgr /skms <KMS-Server-IP>'
### Command 2: Slmgr /ato
## To activate Office,activation using KMS
Cmd/PoweShell (run as administrator):
### Command 1:
Office 2010: cd C:\Program Files\Microsoft Office\Office14 && Office 2013: cd C:\Program Files\Microsoft Office\Office15 && Office 2016 and 2019: CD C:\Program Files\Microsoft Office\Office16
### Command 2: cscript ospp.vbs /sethst: KMS_Server_IP
### Command 3: cscript ospp.vbs /act

## Common errors:
If this is the first time you are activating the desired Windows, please first install the product key specific to your Windows version. To install, first get the Product Key for your Windows version from the Microsoft site and then install it on your system using the following command.
Cmd/PoweShell (run as administrator):
Cammand: slmgr /ipk <Product-key>

## Error code 0x800704CF):
Because the activation mechanism works differently in Evaluation version Windows, you must first change your Windows version to Pro or Enterprise versions and then proceed to activate Windows. To do this, please do the following in order
Cmd/PoweShell (run as administrator):
### Command 1: slmgr /upk
### Command 2: slmgr.vbs /cpky
### Command 3: slmgr /ckms
### Command 4: slmgr.vbs /ckms
### Command 5: slmgr /ipk NPPR9-FWDCX-D2C8J-H872K-2YT43 &&  <Product-key>
### Command 6: slmgr.vbs /skms KMS_Server_IP
### Command 7: slmgr.vbs /ato


## Error code: 0xC004F074
According to the error, it seems that your system is unable to connect to the KMS server and it is not accessible. To fix this problem, please first make sure that the connection to the KMS server is correct and that port 1688 of the KMS server is open. Also, make sure that your system's firewall is not blocking access to this port.

## According to the above errors, if the problem is not solved, you can diagnose and solve your problem through the following link.
https://learn.microsoft.com/en-us/troubleshoot/windows-server/licensing-and-activation/troubleshoot-activation-error-codes
