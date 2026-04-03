  ##### Hunting in Security Onion

To hunt in Security Onion, the below query will gather all Sysmon EID 9 logs. When looking at the logs, valuable fields will be file.directory and process.executable. Process.pid can also be used to see the full process logs, potentially leading back to an unauthorized executable.

```
event.action: RawAccessRead AND event.code: 9
```

Some normal process.executables are System, svchost.exe, SearchApp.exe, WmiPrvSE.exe, MoUsoCoreWorker.exe, DeviceCensus.exe, taskhostw.exe, MsMpEng.exe, MpCmdRun.exe, and lsass.exe. This is not a comprehensive list.

Any processes such as powershell or cmd should be investigated.