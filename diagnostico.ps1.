Write-Host "=== PC GAMER CLOUD ===" -ForegroundColor Cyan

$os = Get-CimInstance Win32_OperatingSystem
$pc = Get-CimInstance Win32_ComputerSystem
$cpu = Get-CimInstance Win32_Processor

Write-Host "`nSISTEMA: $($os.Caption)"
Write-Host "CPU: $($cpu.Name)"
Write-Host "RAM: $([math]::Round($pc.TotalPhysicalMemory / 1GB, 2)) GB"

Write-Host "`nPLACA DE VIDEO:"
Get-CimInstance Win32_VideoController |
ForEach-Object {
    Write-Host $_.Name
}

Write-Host "`nARMAZENAMENTO:"
Get-CimInstance Win32_LogicalDisk -Filter "DriveType=3" |
ForEach-Object {
    Write-Host "$($_.DeviceID) - $([math]::Round($_.Size / 1GB, 2)) GB"
}

Write-Host "`nDiagnostico concluido!"
