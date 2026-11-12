# Billing Assistant · releases

Instaladores y paquetes de actualización de **Billing Assistant**, un asistente de escritorio para armar
y verificar los soportes de facturación del sector salud en Colombia. El código fuente es privado.

*Installers and update packages for Billing Assistant, a desktop assistant that assembles and checks
healthcare billing documents (Colombia). The source code is private.*

---

## Qué hace · What it does

Al cierre de mes, cruza el Excel de admisiones con los documentos de cada paciente, que pueden estar en
carpetas locales o en Google Drive. Identifica cada documento por la cédula o por el nombre, también en
documentos escaneados gracias al OCR local, y genera un PDF por tipo de soporte. El operador solo revisa
y aprueba.

*At month-end it matches the admissions spreadsheet against each patient's documents, from local folders
or Google Drive, identifies them by ID or name (with local OCR for scans), and builds one PDF per
document type. The operator only reviews and approves.*

- OCR local con Tesseract: nada sale del equipo · *local OCR, nothing leaves the machine*
- Base de datos SQLite cifrada y bitácora de auditoría por operador · *encrypted database and audit log*
- Actualización automática incremental con Velopack · *delta auto-updates*

`C#` `.NET 8` `Blazor Server` `SQLite (SQLCipher)` `Tesseract` `Google Drive API` `Velopack`

## Instalación · Install

1. Descargar `BillingAssistant-win-Setup.exe` de la
   [última versión](https://github.com/jconeo117/billing-assistant-releases/releases/latest).
2. Ejecutarlo. No pide permisos de administrador y no necesita tener .NET instalado.
3. Abrir **Billing Assistant** desde el acceso directo. La aplicación se abre en el navegador, en
   `http://localhost:5099`.

Requiere Windows 10 u 11 (x64) y una licencia activa. Las versiones siguientes se instalan solas.

*Windows 10/11 x64. Requires an active license. Later versions install automatically.*

## Qué hay en cada versión · Release assets

| Archivo | Para qué |
|---|---|
| `BillingAssistant-win-Setup.exe` | Instalador · *installer* |
| `BillingAssistant-win-Portable.zip` | Versión portable, sin actualización automática · *portable, no auto-update* |
| `*-full.nupkg`, `*-delta.nupkg`, `RELEASES`, `releases.win.json` | Paquetes que usa la actualización automática · *auto-update feed* |

`version.json` es el manifiesto con el que la aplicación consulta si hay una versión nueva. No se edita
a mano.
