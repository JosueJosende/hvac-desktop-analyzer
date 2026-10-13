<h1 align="center">HVAC Desktop Analyzer</h1>

<p align="center">Analiza mediciones de equipos HVAC en un escritorio Windows o Linux: importa un conjunto de datos, grafícalo por circuito, detecta lo que queda fuera de rango y conviértelo en un informe que puedas entregar.</p>

<p align="center">
  <a href="https://github.com/JosueJosende/hvac-desktop-analyzer/releases/latest">Descargar el instalador más reciente</a> ·
  <a href="https://github.com/JosueJosende/hvac-desktop-analyzer/releases">Historial de versiones</a> ·
  <a href="CURRENT_RELEASE.md">Detalles de la versión actual</a>
</p>

Este repositorio distribuye los instaladores y los metadatos de publicación de la aplicación de escritorio. No publica el código fuente, que es privado.

## Descargas

| Plataforma                   | Archivo                                                 | Notas                                                                                                                                  |
| ---------------------------- | ------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Windows 10 o posterior (x64) | `HVAC-Desktop-Analyzer-<version>-win-x64.exe`           | Instalador. Se instala para todos los usuarios, así que Windows pide permisos de administrador, y puedes elegir la carpeta de destino. |
| Linux (x86_64)               | `HVAC-Desktop-Analyzer-<version>-linux-x86_64.AppImage` | Portable. Dale permisos de ejecución y ejecútalo.                                                                                      |

Ambos archivos aparecen en la [página de publicaciones](https://github.com/JosueJosende/hvac-desktop-analyzer/releases). El nombre incluye la versión, así que enlaza a esa página y no a un archivo concreto.

## Qué hace la aplicación

| Capacidad            | Qué te da                                                                                                                                                                                                                                                                                              |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Importar y graficar  | Carga un archivo de mediciones y revisa cada variable y cada circuito en una gráfica, con las alarmas del rango analizado al lado.                                                                                                                                                                     |
| Análisis             | Estadísticas por variable, correlaciones entre variables y detección de valores fuera de su banda esperada.                                                                                                                                                                                            |
| Diagnóstico          | Contrasta los hallazgos con el equipo y, opcionalmente, redacta un informe de diagnóstico asistido por IA.                                                                                                                                                                                             |
| Informe de campo     | Redacta el objeto del informe, el diagnóstico técnico con la reproducción del fallo, las alarmas del rango analizado, la actuación realizada en campo, las pruebas y la verificación, las observaciones adicionales, las acciones recomendadas, el estado del equipo antes y después, y la conclusión. |
| Exportación          | Guarda el análisis como un archivo HTML independiente o como informe PDF.                                                                                                                                                                                                                              |
| Pruebas y telemetría | Conserva las pruebas guardadas, la telemetría registrada y las anotaciones, y compártelas o muévelas entre equipos.                                                                                                                                                                                    |
| Cuentas              | Trabaja como invitado con todo almacenado en local, o inicia sesión para sincronizar entre máquinas y organizaciones.                                                                                                                                                                                  |
| Idiomas              | Inglés, español y catalán, con tema oscuro.                                                                                                                                                                                                                                                            |

## Instalación

### Windows

1. Descarga el `.exe` desde la página de publicaciones.
2. Ejecútalo. Windows pedirá permisos de administrador, porque el instalador es para todos los usuarios, y te ofrecerá elegir la carpeta de destino.
3. La compilación no está firmada digitalmente, así que SmartScreen puede avisar de que el editor es desconocido. Comprueba antes el SHA-256 en [CURRENT_RELEASE.md](CURRENT_RELEASE.md) y continúa con **Más información** → **Ejecutar de todas formas**.

### Linux

```bash
chmod +x HVAC-Desktop-Analyzer-<version>-linux-x86_64.AppImage
./HVAC-Desktop-Analyzer-<version>-linux-x86_64.AppImage
```

La AppImage necesita FUSE. En un sistema que no lo tenga, ejecuta el mismo archivo con `--appimage-extract-and-run`.

## Actualizaciones

La aplicación empaquetada consulta este repositorio al arrancar y descarga automáticamente una versión más reciente, comprobando antes el SHA-512 registrado en los metadatos de actualización. No hace falta descargar nada a mano para estar al día.

## Dónde están tus datos

La aplicación guarda su base de datos, su configuración y sus registros en el directorio de datos de aplicación de tu usuario. Nada sale de la máquina salvo que inicies sesión y uses las funciones de sincronización en la nube.

## Comprueba lo que has descargado

[CURRENT_RELEASE.md](CURRENT_RELEASE.md) registra el tamaño y el SHA-256 de los instaladores publicados. Los archivos `latest.yml` y `latest-linux.yml` son los metadatos que lee la propia aplicación; contienen el SHA-512 del archivo al que apuntan.

## Alcance de este repositorio

Solo los instaladores y los metadatos de los que se actualiza la aplicación. Aquí no hay código fuente.
