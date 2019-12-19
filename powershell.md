|Command|Comments|
|---|---|
|`Get-WinEvent -FilterHashTable @{LogName='Application';Level='2'} \| Format-Table -wrap \| Out-Host -Paging`|Get Errors from the Application event log|
