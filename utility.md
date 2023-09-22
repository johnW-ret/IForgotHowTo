
# PowerShell to remove JSON from Google Photos Google Takeout export and copy them to all destination
```powershell
$ExportRoot = ""
$ResultPath = ($ExportRoot + "\Takeout\all")

Get-ChildItem -Path $ResultPath -Recurse -Include *.json | Remove-Item -Force

mkdir all;

Get-ChildItem -Path ($ExportRoot + "\Takeout\Google Photos") -Recurse -File | Copy-Item -Destination $ResultPath
```