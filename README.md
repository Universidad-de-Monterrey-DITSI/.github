# Instrucciones para creacion de ETLs

## Version de Python
La version de Python que se usa para ejecutar los ETLs es la `3.6.9` por lo que deben asegurarse que las liberias que utilizan funcionen con esa version.

## Creacion de repositorio
Al crear el repositorio utilizar el prefijo "**etl_**" y sustituir por "**_**" los espacios del nombre del proyecto. Ejemplo: **etl_segmentacion_de_condicionados**

## Archivos a excluir en .gitignore
Excluir todos los archivos que no sean necesarios para la ejecucion del etl, incluyendo archivos con informacion sensible. Ejemplo: Ambientes virtuales, carpetas con cache, carpetas con archivos generados por la ejecucion del etl, archivos de configuracion.

## Archivo de requerimientos
Generar un [archivo de requerimientos](https://pip.pypa.io/en/stable/user_guide/#requirements-files) de nombre `requerimientos.txt` que contenga todas las librerias que estan utilizando en su proyecto y que sera utilizado para instalar en el ambiente virtual.

## Archivo de configuracion
Guardar todas los datos sensibles o datos que se tienen que cambiar en el ambiente productivo en [archivos de configuracion](https://docs.python.org/3/library/configparser.html).

## README.md
Este archivo debe estar en la raiz del proyecto y debe incluir los siguientes datos:
1. Nombre del ETL.
2. Descripcion del ETL.
3. Proyecto para el cual se esta desarrollando el ETL.
4. Direccion y Gerencia para la cual se esta desarrollando el ETL.
5. Persona para la cual se esta desarrollando el ETL.
6. Incluir una seccion con las consultas que se hacen a base de datos y breve descripcion de la consulta.

Pueden usar [esta guia](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

## Log
Todo lo que se imprima en `print()` se guardara automaticamente en un log, solo imprimir lo necesario para no llenar de basura el log.

## Codigo
Seguir las siguientes reglas, de lo contrario se pedira corregir el codigo:
* Todas las variables y nombres de metodos seran en español y en minusculas sustituyendo los espacios por "**_**".
* Todas las constantes seran en español y en mayusculas sustituyendo los espacios por "**_**".
* Crear variables con nombres representativos a lo que se esta haciendo. Ejemplo correcto: `nombre_alumno`, `matricula_alumno`, `nombre_de_materia`, `evento`. Ejemplo incorrecto: `a`, `b`, `c`, `x`, `y`, `z`.
* Incluir documentacion al inicio de cada archivo donde se incluya:
``` python
# Nombre del archivo:
# Descripcion del archivo:

#############
# Historial #
#############

# -----------------
# Fecha:
# Desarrollador:
# Cambios:
# -----------------

```
* Incluir documentacion al inicio de cada metodo donde se incluya:
``` python
# Nombre del metodo:
# Descripcion del metodo:
# Variables de entrada:
# Variables de salida:

#############
# Historial #
#############

# -----------------
# Fecha:
# Desarrollador:
# Cambios:
# -----------------

```
* Al [iterar un dataframe en Pandas](https://medium.com/swlh/why-pandas-itertuples-is-faster-than-iterrows-and-how-to-make-it-even-faster-bc50c0edd30d) tratar de usar `itertuples()`.
* Utilizar la libreria [requests](https://pypi.org/project/requests/) para consumir APIs.


En general seguir las recomendaciones de la [guia de Python](https://peps.python.org/pep-0008/).

## Ejecucion
Al ejecutar el ETL siempre se ejecutara el archivo `__main__.py`, pueden usar este template para iniciar:

``` python
# app.py
import app

if __name__ == '__main__':
    # app.py contiene un metodo run() donde esta la logica del ETL.
    app.run()
```
