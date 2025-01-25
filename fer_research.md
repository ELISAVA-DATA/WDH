Para relacionar la información de un formulario (CSV) con las fotos que están en una carpeta, puedes usar Python con la librería pandas para leer el archivo CSV y la librería os para trabajar con los archivos en el sistema de archivos. Aquí te dejo un ejemplo de cómo podrías hacerlo:

Leer el archivo CSV con los nombres de las fotos.
Verificar si las fotos mencionadas en el CSV están presentes en la carpeta.
Relacionar los nombres de las fotos con su ubicación en la carpeta.
Requisitos:
pandas: para leer y manejar el archivo CSV.
os: para interactuar con los archivos en el sistema operativo.
Primero, instala la librería pandas si no la tienes:

bash
pip install pandas
Código de ejemplo:
python
import os
import pandas as pd

# Ruta del archivo CSV y la carpeta de fotos
ruta_csv = 'ruta/a/tu/archivo.csv'  # Cambia esto con la ruta real del CSV
ruta_fotos = 'ruta/a/la/carpeta/de/fotos'  # Cambia esto con la ruta real de la carpeta de fotos

# Leer el archivo CSV
df = pd.read_csv(ruta_csv)

# Asegúrate de que el nombre de la columna en el CSV coincida con el nombre de la columna que contiene los nombres de las fotos
# Supongamos que la columna se llama "foto_nombre"
nombres_fotos = df['foto_nombre'].tolist()

# Lista de todos los archivos en la carpeta de fotos
archivos_en_carpeta = os.listdir(ruta_fotos)

# Crear un diccionario para almacenar la relación entre los nombres del CSV y las fotos que existen en la carpeta
relacion_fotos = {}

# Recorremos los nombres de las fotos en el CSV
for nombre_foto in nombres_fotos:
    # Verificamos si el archivo con ese nombre existe en la carpeta
    if f"{nombre_foto}.jpg" in archivos_en_carpeta:  # Ajusta la extensión de archivo si es necesario
        # Si la foto existe, la agregamos al diccionario
        relacion_fotos[nombre_foto] = os.path.join(ruta_fotos, f"{nombre_foto}.jpg")
    else:
        # Si la foto no se encuentra, se agrega como 'No encontrado'
        relacion_fotos[nombre_foto] = 'No encontrado'

# Imprimir la relación
for nombre_foto, ruta_foto in relacion_fotos.items():
    print(f"{nombre_foto}: {ruta_foto}")
Explicación:
Lectura del CSV: Usamos pandas para leer el archivo CSV. Asegúrate de reemplazar 'foto_nombre' por el nombre real de la columna que contiene los nombres de las fotos.
Lista de archivos en la carpeta: Con os.listdir(ruta_fotos) obtenemos todos los archivos en la carpeta de fotos.
Búsqueda y relación: Recorremos la lista de nombres de fotos en el CSV y verificamos si existe un archivo con ese nombre en la carpeta. Si es así, guardamos la ruta completa del archivo; si no, indicamos que no se encontró.
Notas:
Asegúrate de que las fotos en la carpeta tengan el mismo nombre que en el CSV y de tener la extensión correcta (como .jpg, .png, etc.).
Si la extensión de las fotos es diferente, ajusta el código para que coincida con el formato adecuado.

YOLOv10: Real-Time End-to-End Object Detection

Codigo que detecta los objetos en un foto

Link de git hub con instrucciones de uso y ejemplos
https://github.com/THU-MIG/yolov10
