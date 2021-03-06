# Update-CWCSessionName
## SYNOPSIS
Updates the name of a session.
## SYNTAX
```powershell
Update-CWCSessionName -Server <String> -GUID <Guid> -User <String> -Password <String> -NewName <String> [-Group <String>] [<CommonParameters>]



Update-CWCSessionName -Server <String> -GUID <Guid> -NewName <String> [-Group <String>] -Credentials <PSCredential> [<CommonParameters>]
```
## DESCRIPTION
Updates the name of a session on the control server.
## PARAMETERS
### -Server &lt;String&gt;
The address to your Control server. Example 'https://control.labtechconsulting.com' or 'http://control.secure.me:8040'
```
Required                    true
Position                    named
Default value
Accept pipeline input       false
Accept wildcard characters  false
```
### -GUID &lt;Guid&gt;
The GUID/SessionID for the machine you wish to connect to.

You can retreive session info with the 'Get-CWCSessions' commandlet



On Windows clients, the launch parameters are located in the registry at:

    HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ScreenConnect Client (xxxxxxxxxxxxxxxx)\ImagePath

On Linux and Mac clients, it's found in the ClientLaunchParameters.txt file in the client installation folder:

    /opt/screenconnect-xxxxxxxxxxxxxxxx/ClientLaunchParameters.txt
```
Required                    true
Position                    named
Default value
Accept pipeline input       false
Accept wildcard characters  false
```
### -User &lt;String&gt;
User to authenticate against the Control server.
```
Required                    true
Position                    named
Default value
Accept pipeline input       false
Accept wildcard characters  false
```
### -Password &lt;String&gt;
Password to authenticate against the Control server.
```
Required                    true
Position                    named
Default value
Accept pipeline input       false
Accept wildcard characters  false
```
### -NewName &lt;String&gt;
The new name for the session.
```
Required                    true
Position                    named
Default value
Accept pipeline input       false
Accept wildcard characters  false
```
### -Group &lt;String&gt;

```
Required                    false
Position                    named
Default value                All Machines
Accept pipeline input       false
Accept wildcard characters  false
```
### -Credentials &lt;PSCredential&gt;
[PSCredential] object used to authenticate against Control.
```
Required                    true
Position                    named
Default value
Accept pipeline input       false
Accept wildcard characters  false
```
## EXAMPLES
### EXAMPLE 1
```powershell
PS C:\>Update-CWCSessionName -Server $Server -GUID $GUID -User $User -Password $Password -NewName 'Session1'

Will rename the session to Session1
```

## NOTES
Version:        1.1

Author:         Chris Taylor

Creation Date:  10/25/2018

Purpose/Change: Initial script development 
