# 🎨 Representación Gráfica

En esta carpeta se encuentra el código utilizado para la creación de prompts descriptivos que permiten la representación visual de los datos obtenidos, así como la descripción de cada elemento gráfico.

## 📝 Descripción

A partir de las fotos enviadas y la información extraída del análisis de datos, desarrollamos ilustraciones que reflejan de manera fiel los elementos visuales más relevantes. Cada forma, color y detalle complementario fue cuidadosamente seleccionado para representar patrones emergentes de la investigación. De esta manera, las visualizaciones generadas ofrecen una interpretación estructurada y significativa de la información recopilada.

## ✨ Generación de Prompts

Para traducir los datos en representaciones visuales, definimos una serie de reglas que determinan los atributos de cada ilustración:

**1️⃣ Forma:**
   - La forma de cada gráfico está determinada por la relación entre las personas que aparecen en la imagen.
   
**2️⃣ Color:**
   - La paleta de colores se asigna según la temática predominante de la foto.
   
**3️⃣ Contorno:**
   - Se añade un contorno específico dependiendo de la ubicación de la imagen (interior o exterior).
   
**4️⃣ Sparkle:**
   - Si las personas en la foto están sonriendo, se incorpora un efecto "sparkle" en la ilustración.

Con base en estas categorías, se desarrolló un código en Python que lee la información procesada en formato CSV y la traduce en prompts descriptivos para la generación automática de visualizaciones.

### 📌 Ejemplo de Prompt Generado:
   *"Couple graph green pink orange add contour with sparkle!"*

