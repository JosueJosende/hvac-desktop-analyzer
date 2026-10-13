# Publicaciones de HVAC Desktop Analyzer

Este repositorio distribuye los instaladores públicos para Windows y Linux y sus metadatos de publicación; no publica el código fuente de la aplicación. Las descargas son públicas y se pueden inspeccionar. Consulta [README.md](README.md) para saber qué hace la aplicación y cómo instalarla.

## Versión actual: 0.62.0

- Aplicación: HVAC Desktop Analyzer (`com.hvac.analizer`)
- [Todas las publicaciones](https://github.com/JosueJosende/hvac-desktop-analyzer/releases)

| Plataforma | Archivo | Tamaño | SHA-256 |
| --- | --- | --- | --- |
| Windows 10 o posterior (x64) | [HVAC-Desktop-Analyzer-0.62.0-win-x64.exe](https://github.com/JosueJosende/hvac-desktop-analyzer/releases/download/v0.62.0/HVAC-Desktop-Analyzer-0.62.0-win-x64.exe) | 124.816.292 bytes | `444be538d3cbdb4d0ed3d1aab4ae137a447520ec09a9914d5fbc921bd036874f` |
| Linux (x86_64) | [HVAC-Desktop-Analyzer-0.62.0-linux-x86_64.AppImage](https://github.com/JosueJosende/hvac-desktop-analyzer/releases/download/v0.62.0/HVAC-Desktop-Analyzer-0.62.0-linux-x86_64.AppImage) | 160.819.907 bytes | `d45475269f0131ca23a0a8b6ab8e664c9ca17a8e66447f1015c43b28c8caf926` |

Ninguno de los dos instaladores está firmado digitalmente. El binario de Windows lleva la tabla de firma Authenticode vacía, así que SmartScreen avisa de un editor desconocido y la forma de comprobar lo que has descargado es el SHA-256 de la tabla anterior.

## Qué es esta versión

La primera publicación pública de la aplicación de escritorio, en la versión a la que había llegado el repositorio privado de código. La aplicación importa un conjunto de mediciones, grafica cada variable y cada circuito junto con las alarmas del rango analizado, calcula estadísticas por variable, correlaciones y valores fuera de banda, y exporta el resultado como un archivo HTML independiente o como informe PDF. Las pruebas guardadas, la telemetría y las anotaciones se pueden conservar, compartir y mover entre equipos; las cuentas son opcionales y el modo invitado lo mantiene todo en local.

La versión 0.62.0 incorpora el informe de IA en su forma de informe de campo —objeto del informe, diagnóstico técnico con la reproducción del fallo, alarmas del rango analizado, actuación realizada en campo, pruebas y verificación, observaciones adicionales, acciones recomendadas, estado del equipo antes y después, y conclusión— junto con entradas opcionales del técnico y un razonamiento diferencial que cuantifica el cambio, nombra la banda de referencia que se ha cruzado y registra cada causa descartada con el dato que la descarta. Ofrece Gemini 3.5 Flash-Lite como modelo rápido y de bajo coste, y distingue en sus mensajes un modelo saturado, una cuota agotada y un límite de velocidad momentáneo. También corrige que la lista de modelos de IA ofrezca solo lo que la API sirve en ese momento, que el informe se truncara por el límite de salida, que el error en crudo del proveedor llegara a la pantalla y que los totales de alarmas y la caché de diagnóstico pudieran contradecir los datos que describen.

## Metadatos de actualización

La aplicación empaquetada lee `latest.yml` (Windows) y `latest-linux.yml` (Linux) de este repositorio al arrancar, descarga automáticamente una versión más reciente y comprueba el SHA-512 registrado en esos metadatos antes de aplicarla.

## Migración

No hay ninguna publicación pública anterior de la versión de escritorio, así que esto es una instalación nueva. Dos notas para quien haya ejecutado una compilación previa:

- El nombre del producto ha cambiado de «HVAC Analyzer» a «HVAC Desktop Analyzer». En Windows el instalador coloca la aplicación en `%ProgramFiles%\HVAC Desktop Analyzer` y la entrada del menú Inicio cambia de nombre, así que una instalación hecha con el nombre antiguo no se actualiza en el sitio; desinstálala después de comprobar dónde están tus datos, o instala la versión nueva junto a ella.
- El directorio de datos de aplicación por usuario no cambia, porque deriva del nombre del paquete de la aplicación, que no se ha renombrado. La base de datos, la configuración y los registros locales pasan a la instalación nueva.
