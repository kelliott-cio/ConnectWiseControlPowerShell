# Get-CWCLastContact
## SYNOPSIS
Returns the date the machine last connected to the control server.
## SYNTAX
```powershell
Get-CWCLastContact -Server <String> -GUID <Guid> -User <String> -Password <String> [-Quiet] [-Seconds <Int32>] [-Group <String>] [<CommonParameters>]



Get-CWCLastContact -Server <String> -GUID <Guid> [-Quiet] [-Seconds <Int32>] [-Group <String>] -Credentials <PSCredential> [<CommonParameters>]
```
## DESCRIPTION
Returns the date the machine last connected to the control server.
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
### -Quiet &lt;SwitchParameter&gt;
Will output a boolean result, $True for Connected or $False for Offline.
```
Required                    false
Position                    named
Default value                False
Accept pipeline input       false
Accept wildcard characters  false
```
### -Seconds &lt;Int32&gt;
Used with the Quiet switch. The number of seconds a machine needs to be offline before returning $False.
```
Required                    false
Position                    named
Default value                0
Accept pipeline input       false
Accept wildcard characters  false
```
### -Group &lt;String&gt;
Name of session group to use.
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
## OUTPUTS
[datetime] -or [boolean]

## EXAMPLES
### EXAMPLE 1
```powershell
PS C:\>Get-CWCLastContact -Server $Server -GUID $GUID -User $User -Password $Password

Will return the last contact of the machine with that GUID.
```

## NOTES
Version:        1.1

Author:         Chris Taylor

Creation Date:  1/20/2016

Purpose/Change: Initial script development



Update Date:  8/24/2018

Purpose/Change: Fix Timespan Seconds duration 
