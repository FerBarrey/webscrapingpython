# webscrapingpython

Proyecto de Extracción, Verificación y Resumen de Hipervínculos en Documentos Word
Este proyecto en Python automatiza el proceso de extracción de hipervínculos de documentos de Microsoft Word (.docx), verifica su validez y, para los enlaces a noticias (sitios web generales, excluyendo redes sociales), extrae el texto principal y genera un resumen utilizando técnicas de Procesamiento del Lenguaje Natural (PLN). Los resultados se organizan y guardan en archivos Excel para facilitar su análisis.

Objetivo:

El objetivo principal de este proyecto es agilizar la revisión de documentos que contienen múltiples hipervínculos, permitiendo identificar rápidamente el estado de cada enlace y obtener un resumen conciso del contenido de las noticias enlazadas. Esto es particularmente útil para investigadores, periodistas o cualquier persona que necesite procesar información de múltiples fuentes web referenciadas en documentos.

Funcionalidades:

Extracción de Hipervínculos: Identifica y extrae todas las URLs incrustadas como hipervínculos dentro de un documento Word.
Clasificación de Enlaces: Categoriza los hipervínculos básicos en 'Facebook', 'X' (anteriormente Twitter) u 'Otro'.
Verificación de Validez: Comprueba si cada hipervínculo es accesible y devuelve su estado ('Válido', 'No Válido', 'Error'). Se utiliza un requests.head con un timeout corto para verificar la cabecera de la URL de manera eficiente.
Extracción y Resumen de Texto (para enlaces 'Otro'): Para los hipervínculos que no son de redes sociales, intenta acceder al contenido de la página web, extrae el texto principal de la noticia y genera un resumen utilizando el algoritmo LSA (Latent Semantic Analysis) de la librería sumy.
Procesamiento Paralelo: Utiliza ThreadPoolExecutor para verificar la validez de los enlaces y extraer/resumir texto de forma concurrente, mejorando significativamente la velocidad del procesamiento en documentos con muchos enlaces.
Generación de Informes en Excel: Guarda los resultados (URL, Categoría, Validez, Resumen) en archivos .xlsx separados para cada documento Word procesado.
Manejo de Múltiples Documentos: El script está diseñado para procesar una lista de documentos Word, generando un archivo de salida en Excel por cada documento de entrada.
Tecnologías Utilizadas:

Python 3.x: Lenguaje de programación principal.
python-docx: Para interactuar y extraer información de archivos .docx.
requests: Para realizar solicitudes HTTP y verificar la validez de los enlaces.
pandas: Para la manipulación y almacenamiento de datos en DataFrames y exportar a Excel.
beautifulsoup4: Para parsear el contenido HTML de las páginas web y extraer texto.
sumy: Una librería para resumen automático de texto, utilizando el método LSA.
nltk: La Natural Language Toolkit, utilizada por sumy para tokenización y procesamiento de texto en español.
concurrent.futures: Para implementar el procesamiento paralelo y acelerar las tareas de red.

###############################################################################################################################################3
Hyperlink Extraction, Verification, and Summarization Project in Word Documents
This Python project automates the process of extracting hyperlinks from Microsoft Word (.docx) documents, verifies their validity, and for news links (general websites, excluding social media), extracts the main text and generates a summary using Natural Language Processing (NLP) techniques. The results are organized and saved in Excel files for easy analysis.

Objective:

The main objective of this project is to streamline the review of documents containing multiple hyperlinks, allowing for quick identification of each link's status and obtaining a concise summary of the content of linked news articles. This is particularly useful for researchers, journalists, or anyone who needs to process information from multiple web sources referenced in documents.

Functionalities:

Hyperlink Extraction: Identifies and extracts all URLs embedded as hyperlinks within a Word document.
Link Classification: Categorizes basic hyperlinks into 'Facebook', 'X' (formerly Twitter), or 'Other'.
Validity Verification: Checks if each hyperlink is accessible and returns its status ('Valid', 'Invalid', 'Error'). It uses requests.head with a short timeout for efficient URL header checking.
Text Extraction and Summarization (for 'Other' links): For hyperlinks that are not social media links, it attempts to access the content of the web page, extracts the main news text, and generates a summary using the LSA (Latent Semantic Analysis) algorithm from the sumy library.
Parallel Processing: Utilizes ThreadPoolExecutor to verify link validity and extract/summarize text concurrently, significantly improving processing speed for documents with many links.
Excel Report Generation: Saves the results (URL, Category, Validity, Summary) into separate .xlsx files for each processed Word document.
Handling Multiple Documents: The script is designed to process a list of Word documents, generating one Excel output file for each input document.
Technologies Used:

Python 3.x: Main programming language.
python-docx: For interacting with and extracting information from .docx files.
requests: For making HTTP requests and verifying link validity.
pandas: For data manipulation and storage in DataFrames and exporting to Excel.
beautifulsoup4: For parsing HTML content from web pages and extracting text.
sumy: A library for automatic text summarization, using the LSA method.
nltk: The Natural Language Toolkit, used by sumy for Spanish tokenization and text processing.
concurrent.futures: To implement parallel processing and speed up network tasks.
