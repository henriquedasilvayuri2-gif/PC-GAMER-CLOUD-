# Instalador do Sunshine para Windows
$ErrorActionPreference = "Stop"

Write-Host "PC GAMER CLOUD - Sunshine" -ForegroundColor Cyan

$winget = Get-Command winget.exe -ErrorAction SilentlyContinue

if (-not $winget) {
    Write-Host "WinGet nao encontrado."
    exit 1
}

Write-Host "Verificando Sunshine..."

winget show --id LizardByte.Sunshine --exact

if ($LASTEXITCODE -ne 0) {
    Write-Host "Pacote nao encontrado. Consulte a documentacao oficial."
    exit 1
}

$confirmacao = Read-Host "Digite SIM para instalar"

if ($confirmacao -cne "SIM") {
    Write-Host "Instalacao cancelada."
    exit 0
}

winget install --id LizardByte.Sunshine --exact --accept-package-agreements --accept-source-agreements

if ($LASTEXITCODE -ne 0) {
    Write-Host "Erro durante a instalacao."
    exit 1
}

Write-Host "Instalacao finalizada!" -ForegroundColor Green
