<div align="center">

# GADGETS · SUPPORT_CX

Índice de utilidades GUI para soporte IT en Windows.

<sub>Scripts: <a href="https://github.com/4leX-42/SCRIPTS-SUPPORT_CX">SCRIPTS-SUPPORT_CX</a></sub>

</div>

<br>

| | Gadget | Qué hace | Hecho con |
|:-:|---|---|---|
| <img src="https://api.iconify.design/lucide/printer.svg?color=%238b949e" width="20"> | [**PrintDeploy**](https://github.com/4leX-42/PrintDeploy) | Detecta marca y modelo de una impresora de red e instala su driver, con página de prueba confirmada. | C# · .NET 4.8 |
| <img src="https://api.iconify.design/lucide/lock-open.svg?color=%238b949e" width="20"> | [**DocUnlock**](https://github.com/4leX-42/DocUnlock) | Quita protecciones, firmas y metadatos de PDF y Office, y comprime. Local, sin admin. | Python · PySide6 |
| <img src="https://api.iconify.design/lucide/receipt.svg?color=%238b949e" width="20"> | [**Conversor LEDES 98BI**](https://github.com/4leX-42/LEDES-Converter) | Convierte facturas en PDF al formato LEDES 98BI. | Python · tkinter |
| <img src="https://api.iconify.design/lucide/square-terminal.svg?color=%238b949e" width="20"> | [**Vorterm**](https://github.com/4leX-42/Vorterm) | Deja la consola lista en un comando: PowerShell 7, Windows Terminal, fuentes y tema. | PowerShell · WPF |
| <img src="https://api.iconify.design/lucide/folder-tree.svg?color=%238b949e" width="20"> | [**PathShrink**](https://github.com/4leX-42/PathShrink) | Encuentra rutas de OneDrive y SharePoint de más de 400 caracteres y propone el mínimo de cambios, reversibles. | PowerShell · WPF |
| <img src="https://api.iconify.design/lucide/download.svg?color=%238b949e" width="20"> | [**PastDow**](https://github.com/4leX-42/PastDow) | Pega un enlace y descarga el vídeo o el audio a la mejor calidad. Con yt-dlp. | C# · WebView2 |
| <img src="https://api.iconify.design/lucide/monitor.svg?color=%238b949e" width="20"> | [**FastRemote**](https://github.com/4leX-42/FastRemote) | Lanzador de Escritorio remoto: sedes con sus servidores, disponibilidad al abrir, estado real de las sesiones e importación de mRemoteNG. Cada conexión en su mstsc. | C# · WPF |

<br>

## Instalar

En PowerShell. Cada línea descarga la última versión y la abre.

<details>
<summary><b>PrintDeploy</b> · perfil del usuario y menú Inicio, pide elevación</summary>

```powershell
Set-ExecutionPolicy -Scope Process Bypass -Force; [Net.ServicePointManager]::SecurityProtocol=3072; $ProgressPreference='SilentlyContinue'; $d="$env:LOCALAPPDATA\Programs\PrintDeploy"; New-Item -ItemType Directory -Force $d | Out-Null; $f="$d\PrintDeploy.exe"; irm https://github.com/4leX-42/PrintDeploy/releases/latest/download/PrintDeploy.exe -OutFile $f; $s=(New-Object -ComObject WScript.Shell).CreateShortcut("$env:APPDATA\Microsoft\Windows\Start Menu\Programs\PrintDeploy.lnk"); $s.TargetPath=$f; $s.Save(); Start-Process $f
```
</details>

<details>
<summary><b>DocUnlock</b> · ábrelo sin elevar, o Windows bloquea arrastrar y soltar</summary>

```powershell
$f="$env:TEMP\DocUnlock.exe"; [Net.ServicePointManager]::SecurityProtocol=3072; irm https://github.com/4leX-42/DocUnlock/releases/latest/download/DocUnlock.exe -OutFile $f; explorer.exe "$f"
```
</details>

<details>
<summary><b>Conversor LEDES 98BI</b></summary>

```powershell
$f="$env:TEMP\LEDES98BI.exe"; [Net.ServicePointManager]::SecurityProtocol=3072; irm https://github.com/4leX-42/LEDES-Converter/releases/latest/download/Conversor.LEDES.98BI.exe -OutFile $f; explorer.exe "$f"
```
</details>

<details>
<summary><b>Vorterm</b></summary>

```powershell
Set-ExecutionPolicy -Scope Process Bypass -Force; [Net.ServicePointManager]::SecurityProtocol=3072; $f="$env:TEMP\vorterm-bootstrap.ps1"; irm https://raw.githubusercontent.com/4leX-42/Vorterm/main/bootstrap.ps1 -OutFile $f; & $f
```
</details>

<details>
<summary><b>PathShrink</b> · para el usuario, sin admin, comprueba el SHA-256</summary>

```powershell
$f="$env:TEMP\install-pathshrink.ps1"; [Net.ServicePointManager]::SecurityProtocol=3072; irm https://raw.githubusercontent.com/4leX-42/PathShrink/main/install.ps1 -OutFile $f; powershell -NoProfile -ExecutionPolicy Bypass -File $f
```
</details>

<details>
<summary><b>PastDow</b> · se instala solo, sin admin, y prepara el motor la primera vez</summary>

```powershell
$f="$env:TEMP\PastDow.exe"; [Net.ServicePointManager]::SecurityProtocol=3072; irm https://github.com/4leX-42/PastDow/releases/latest/download/PastDow.exe -OutFile $f; Start-Process $f
```
</details>

<details>
<summary><b>FastRemote</b> · perfil del usuario y menú Inicio, sin admin</summary>

```powershell
[Net.ServicePointManager]::SecurityProtocol=3072; $ProgressPreference='SilentlyContinue'; $d="$env:LOCALAPPDATA\Programs\FastRemote"; New-Item -ItemType Directory -Force $d | Out-Null; $f="$d\FastRemote.exe"; irm https://github.com/4leX-42/FastRemote/releases/latest/download/FastRemote.exe -OutFile $f; $s=(New-Object -ComObject WScript.Shell).CreateShortcut("$env:APPDATA\Microsoft\Windows\Start Menu\Programs\FastRemote.lnk"); $s.TargetPath=$f; $s.Save(); Start-Process $f
```
</details>

<br>

## Añadir un gadget

Repo propio con `README.md` · ejecutable como asset de una release, nunca en git · una fila arriba y una entrada en [`gadgets.json`](gadgets.json).

---

<sub><b>EN</b> — Index of Windows IT-support tools with their own UI. Each one lives in its own repo; this one only lists them. The install lines download the latest release and open it.</sub>
