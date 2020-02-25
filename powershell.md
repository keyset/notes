|Command|Comments|
|---|---|
|`Get-WinEvent -FilterHashTable @{LogName='Application';Level='2'} \| Format-Table -wrap \| Out-Host -Paging`|Get Errors from the Application event log|
|`Get-PSDrive`|List attached drives|
|`net use`|List network drives|
|`Compress-Archive`|Zip|
|`Expand-Archive`|Unzip|
|`Invoke-WebRequest -Uri "https://foo.com/file.zip" -UseBasicParsing -OutFile .\file.zip`|Download file via HTTP|
