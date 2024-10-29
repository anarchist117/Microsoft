# Geoblock
```
Command not supported
We're sorry, we can't continue because we weren't able to download a required file. Please make sure you're connected to the internet or connect to a different network, then try again.
```

# Solution
```
reg add "HKCU\Software\Microsoft\Office\16.0\Common\ExperimentConfigs\Ecs" /v "CountryCode" /t REG_SZ /d "std::wstring|US" /f
```
