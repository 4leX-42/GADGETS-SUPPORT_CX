# GADGETS · SUPPORT_CX

Herramientas de soporte IT para Windows con interfaz propia: ejecutables y apps con GUI. Cada una vive en
**su propio repo**; esto es el índice. Los scripts sueltos están en
[SCRIPTS-SUPPORT_CX](https://github.com/4leX-42/SCRIPTS-SUPPORT_CX).

| Gadget | Qué hace | Hecho con | Repo |
|---|---|---|---|
| **PrintDeploy** | Detecta marca y modelo de cualquier impresora de red e instala el driver adecuado. Escáner de la red, impresoras instaladas, página de prueba confirmada en la impresora. | C# · WinForms · .NET 4.8 | [PrintDeploy](https://github.com/4leX-42/PrintDeploy) |
| **DocUnlock** | Quita protecciones, permisos, firmas y metadatos de PDF y Office, y comprime. Local, sin admin. | Python · PySide6 | [DocUnlock](https://github.com/4leX-42/DocUnlock) |
| **Conversor LEDES 98BI** | Convierte facturas en PDF al formato LEDES 98BI de las plataformas de facturación legal. | Python · tkinter | [LEDES-Converter](https://github.com/4leX-42/LEDES-Converter) |
| **Vorterm** | Deja la consola de PowerShell lista en un comando: PowerShell 7, Windows Terminal, fuentes, tema, multipanel. | PowerShell · WPF | [Vorterm7.0](https://github.com/4leX-42/Vorterm7.0) |
| **PathShrink** | Encuentra las rutas de OneDrive y SharePoint de más de 400 caracteres y propone el mínimo de cambios de nombre, con plan, comparación antes y después y reversión comprobada. EN/ES/PT. | PowerShell · WPF | [PathShrink](https://github.com/4leX-42/PathShrink) |

## Instalar

En PowerShell. Cada línea descarga la última versión y la abre.

**DocUnlock** (ábrelo sin elevar: si no, Windows bloquea arrastrar y soltar)

```powershell
$f="$env:TEMP\DocUnlock.exe"; [Net.ServicePointManager]::SecurityProtocol=3072; irm https://github.com/4leX-42/DocUnlock/releases/latest/download/DocUnlock.exe -OutFile $f; explorer.exe "$f"
```

**Conversor LEDES 98BI**

```powershell
$f="$env:TEMP\LEDES98BI.exe"; [Net.ServicePointManager]::SecurityProtocol=3072; irm https://github.com/4leX-42/LEDES-Converter/releases/latest/download/Conversor.LEDES.98BI.exe -OutFile $f; explorer.exe "$f"
```

**Vorterm**

```powershell
Set-ExecutionPolicy -Scope Process Bypass -Force; [Net.ServicePointManager]::SecurityProtocol=3072; $f="$env:TEMP\vorterm-bootstrap.ps1"; irm https://raw.githubusercontent.com/4leX-42/Vorterm7.0/main/bootstrap.ps1 -OutFile $f; & $f
```

**PathShrink** (instala para el usuario, sin admin, comprueba el SHA-256)

```powershell
$f="$env:TEMP\install-pathshrink.ps1"; [Net.ServicePointManager]::SecurityProtocol=3072; irm https://raw.githubusercontent.com/4leX-42/PathShrink/main/install.ps1 -OutFile $f; powershell -NoProfile -ExecutionPolicy Bypass -File $f
```

**PrintDeploy** se compila (`dotnet build -c Release`): lleva drivers de fabricante que no se
redistribuyen. Detalle en su repo.

## Añadir un gadget

1. Repo propio con `README.md` (qué hace, cómo se instala o compila, qué no está en git).
2. Ejecutable como asset de una release, nunca dentro de git.
3. Una fila en la tabla de arriba y una entrada en [`gadgets.json`](gadgets.json).

---

**EN** — Index of Windows IT-support tools with their own UI (executables and GUI apps). Each one lives
in its own repo; this repo only lists them. Scripts live in SCRIPTS-SUPPORT_CX. Install lines above
download the latest release and open it.
