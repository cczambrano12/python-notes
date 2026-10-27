# Python desde cero: guía rápida con cuadernos interactivos

Colección de cuadernos de Jupyter en español para aprender los conceptos básicos de Python. Están pensados como una **hoja de referencia (cheatsheet)** con explicaciones breves y ejemplos que puedes ejecutar y modificar. No necesitas experiencia previa en programación.

Donde ayuda a entender mejor, los cuadernos incluyen controles interactivos (`ipywidgets`) marcados con 🎛️.

## Contenido

Se recomienda seguir el orden numérico: cada cuaderno usa lo visto en los anteriores.

| # | Cuaderno | Temas |
|---|----------|-------|
| 01 | [Variables y tipos de datos](notebooks/01_variables_y_tipos_de_datos.ipynb) | variables, `int`, `float`, `str`, `bool`, `None`, conversión de tipos |
| 02 | [Operadores](notebooks/02_operadores.ipynb) | aritméticos, comparación, asignación, `in`, operadores sobre texto |
| 03 | [Comentarios, documentación y nombres](notebooks/03_comentarios_documentacion_y_nombres.ipynb) | `#`, docstrings, PEP 8, nombres de variables |
| 04 | [Booleanos y condicionales](notebooks/04_booleanos_y_condicionales.ipynb) | `and`, `or`, `not`, `if`, `elif`, `else` |
| 05 | [Funciones](notebooks/05_funciones.ipynb) | `def`, `return`, parámetros posicionales, por nombre, por defecto, `*args`, `**kwargs` |
| 06 | [Cadenas de texto](notebooks/06_cadenas_de_texto.ipynb) | indexación, codificación, caracteres de control, métodos vs. funciones, f-strings |
| 07 | [Ciclos `while` y `for`](notebooks/07_ciclos_while_y_for.ipynb) | `range`, `break`, `continue`, `pass`, `input()` |
| 08 | [Listas](notebooks/08_listas.ipynb) | creación, métodos, recorrido, comprensión, pilas y colas |
| 09 | [Tuplas](notebooks/09_tuplas.ipynb) | inmutabilidad, desempaquetado |
| 10 | [Diccionarios](notebooks/10_diccionarios.ipynb) | métodos, histogramas, tablas de búsqueda, dict de dicts |
| 11 | [Paso de parámetros: valor vs. referencia](notebooks/11_parametros_valor_vs_referencia.ipynb) | mutables vs. inmutables, copias |
| 12 | [Estructuras anidadas](notebooks/12_estructuras_anidadas.ipynb) | lista de dicts, dict de listas, JSON |
| 13 | [Programas, módulos y biblioteca estándar](notebooks/13_modulos_y_programas.ipynb) | ejecutar un `.py`, módulos propios, `import`, `math`, `random` |
| 14 | [Archivos](notebooks/14_archivos.ipynb) | `open`, `with`, `csv`, `json` |
| 15 | [Matrices e imágenes RGB](notebooks/15_matrices_e_imagenes.ipynb) | listas de listas, Matplotlib, `imshow` |
| 16 | [Análisis de datos con pandas](notebooks/16_pandas_analisis_de_datos.ipynb) | `DataFrame`, filtros, `groupby`, CSV |
| 17 | [Gráficas con pandas](notebooks/17_graficas_con_pandas.ipynb) | líneas, barras, pastel, histograma, dispersión |

## Cómo ejecutarlo

### Opción A: en tu computadora

Necesitas Python 3.9 o superior ([descargar](https://www.python.org/downloads/)).

```bash
# 1. Entra a la carpeta del proyecto
cd python-notes

# 2. Crea un entorno virtual (recomendado)
python3 -m venv .venv

# 3. Actívalo
source .venv/bin/activate        # macOS / Linux
.venv\Scripts\activate           # Windows (PowerShell o CMD)

# 4. Instala las dependencias
pip install -r requirements.txt

# 5. Abre JupyterLab
jupyter lab
```

Se abrirá el navegador. En el panel izquierdo entra a la carpeta `notebooks/` y abre el cuaderno `01_...`.

**Alternativas locales**
- **VS Code:** instala las extensiones *Python* y *Jupyter*, abre un `.ipynb` y elige el entorno `.venv` como kernel.
- **Anaconda:** ya incluye Jupyter, pandas y Matplotlib; solo falta `pip install ipywidgets` si no lo trae.

### Opción B: en el navegador, sin instalar nada

| Servicio | Cómo |
|----------|------|
| **Google Colab** | Entra a [colab.research.google.com](https://colab.research.google.com), menú *Archivo → Subir cuaderno* y elige un `.ipynb`. Si subes este proyecto a GitHub, también puedes usar *Archivo → Abrir cuaderno → GitHub*. Colab ya incluye pandas, Matplotlib y ipywidgets. |
| **Binder** | Sube el proyecto a un repositorio público de GitHub y abre [mybinder.org](https://mybinder.org) con la URL del repositorio. Instala automáticamente `requirements.txt`. |
| **GitHub Codespaces** | En el repositorio: *Code → Codespaces → Create*. Luego `pip install -r requirements.txt` y abre los cuadernos en VS Code web. |
| **JupyterLite** | Versión de Jupyter que corre 100 % en el navegador ([jupyter.org/try-jupyter](https://jupyter.org/try-jupyter)). Algunas funciones (como `input()` o `!python`) pueden comportarse distinto. |

> Los cuadernos 13 y 14 crean archivos de ejemplo (`.py`, `.txt`, `.csv`) en la carpeta donde se ejecutan. En Colab y Binder esos archivos son temporales y desaparecen al cerrar la sesión.

## Cómo usar los cuadernos

1. Ejecuta cada celda de código con **`Shift + Enter`**.
2. **Cambia los valores** y vuelve a ejecutar: experimentar es la mejor forma de aprender.
3. Ejecuta las celdas **en orden**; muchas dependen de las anteriores.
4. Si algo se rompe: menú *Kernel → Restart Kernel* (o *Runtime → Restart* en Colab) y empieza de nuevo.
5. Los errores no son un problema: lee el mensaje, suele indicar qué falló.

## Problemas frecuentes

- **Los controles interactivos 🎛️ no aparecen** (solo se ve un texto como `IntSlider(...)`): comprueba que `ipywidgets` esté instalado (`pip install ipywidgets`) y reinicia el kernel. En JupyterLab muy antiguo, actualiza con `pip install -U jupyterlab`.
- **`ModuleNotFoundError: No module named 'pandas'`**: instala las dependencias con `pip install -r requirements.txt` dentro del entorno virtual activo.
- **`input()` no responde**: escribe en el cuadro que aparece junto a la celda y pulsa `Enter`.
- **En Windows `python3` no existe**: usa `python` o `py`.

## Estructura del proyecto

```
python-notes/
├── README.md
├── requirements.txt
└── notebooks/
    ├── 01_variables_y_tipos_de_datos.ipynb
    ├── ...
    └── 17_graficas_con_pandas.ipynb
```
