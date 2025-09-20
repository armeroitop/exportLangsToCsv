Perfecto 😃, aquí tienes una versión **extendida del README.md** adaptada para instalar el script en `/usr/local/bin` y que incluya **generación directa del CSV** con ejemplo de salida:

````markdown
# exportLangsToCsv

`exportLangsToCsv` es un script en PHP que convierte archivos de traducción de un directorio `lang` en un archivo CSV. Está diseñado para trabajar con subdirectorios de idiomas (`en`, `es`, `ca`, etc.), y genera una tabla con todas las claves y sus traducciones.

---

## Instalación

1. Copia el script al directorio `/usr/local/bin` para que sea accesible desde cualquier usuario:

```bash
sudo cp exportLangsToCsv /usr/local/bin/
sudo chmod +x /usr/local/bin/exportLangsToCsv
````

2. Verifica que `/usr/local/bin` está en tu `PATH`:

```bash
echo $PATH
```

Deberías ver `/usr/local/bin` incluido. Ahora podrás ejecutar el script desde cualquier directorio:

```bash
exportLangsToCsv
```

---

## Uso

```bash
exportLangsToCsv [DIRECTORIO] [--help]
```

* **DIRECTORIO**: ruta al directorio `lang` que contiene los subdirectorios de idiomas.

  * Si se omite, se utiliza el directorio actual (`getcwd()`).
* **--help**: muestra la ayuda del script.

---

### Ejemplos

1. Ejecutar en el directorio actual:

```bash
cd /var/www/htdoc/Moodle/pluginX/lang
exportLangsToCsv
```

2. Ejecutar en un directorio específico:

```bash
exportLangsToCsv /var/www/htdoc/Moodle/pluginX/lang
```

3. Mostrar ayuda:

```bash
exportLangsToCsv --help
```

---

## Requisitos

* PHP 7 o superior.
* Archivos de traducción en formato PHP dentro de subdirectorios de idiomas, por ejemplo:

```
lang/
├── en/
│   ├── messages.php
├── es/
│   ├── messages.php
├── ca/
│   ├── messages.php
```

---

## Funcionamiento

1. El script detecta el directorio `lang` (ya sea el actual o el pasado como argumento).
2. Recorre cada subdirectorio de idioma (`en`, `es`, `ca`, etc.).
3. Lee los archivos PHP de traducción y extrae las claves y valores.
4. Combina todas las claves en un **array de filas**, donde cada fila contiene:

```
key | en | es | ca | ...
```

5. Genera un archivo CSV llamado `messages_langs.csv` en el directorio "Descargas o Downloads", con el siguiente formato de ejemplo:

```
key,en,es,ca
title,Hello,Hola,Títol
description,This is a test,Esto es una prueba,Això és una prova
button_submit,Submit,Enviar,Envia
```

* Si alguna clave falta en un idioma, se rellena con cadena vacía `''`.

---

## Personalización

* Orden de idiomas: puedes cambiar el orden de las columnas editando la lista de idiomas en el script, por ejemplo `['en','es','ca']`.
* Valores faltantes: el script rellena automáticamente con `''` si no hay traducción.
* Argumentos opcionales:

  * `--help` → muestra este mensaje de ayuda.
  * `[DIRECTORIO]` → permite especificar un directorio `lang` distinto al actual.

---

## Contacto

Creado por David Gerardo Martínez Armero
Correo: [armeroitop@gmail.com](mailto:armeroitop@gmail.com)

```

---


```
