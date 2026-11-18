# Kidz Labz — English & Fun for Kids

> Cuaderno de trabajo interactivo de inglés (Nivel A1) diseñado para niños de 9 a 12 años, maquetado íntegramente en LaTeX.

Puedes visualizar y descargar el cuaderno compilado directamente en [build/kids.pdf][kids-workbook-pdf].

## ¿En qué consiste el proyecto?

**Kidz Labz — English & Fun for Kids** es un *workbook* educativo bilingüe (Inglés–Español) enfocado en el aprendizaje práctico, visual y conversacional del idioma inglés en nivel básico (**A1**).

A diferencia de los libros de texto tradicionales con bloques densos de teoría, este proyecto implementa un sistema de diseño pedagógico en LaTeX (`template/kids/theme.tex`) adaptado a lectores infantiles:
- **Diseño visual amigable y codificado por colores**: Cada módulo tiene su propia identidad cromática (Azul Eléctrico, Verde Esmeralda, Amarillo Cálido y Rosa Neón) que se refleja en las portadas de sección y barras laterales.
- **Tipografía pensada para niños**: Uso de fuentes sin serifa limpias y redondeadas (`Segoe UI` y `Bahnschrift`) sin cortes de palabras con guiones al final de línea (`\hyphenpenalty=10000`) para facilitar la lectura.
- **Componentes didácticos interactivos**: Tarjetas de vocabulario bilingües (`vocabcard`), cápsulas de gramática (`grammartip`), cajas de ejercicios prácticos con líneas de escritura amplias (`activity`), lecturas guiadas (`readingbox`), canciones (`songbox`) y rúbricas de autoevaluación con estrellas (`\selfcheck`).

## Propósito

El objetivo principal del cuaderno es guiar a niños hispanohablantes de **9 a 12 años** en sus primeros pasos con el inglés, logrando que puedan:
1. **Comunicarse en situaciones cotidianas**: Saludar, presentarse, expresar emociones, hablar de su familia, mascotas, gustos y rutinas.
2. **Aprender haciendo (*Learning by Doing*)**: Consolidar cada tema mediante actividades de escritura, dibujo, asociación, juegos de rol (*roleplay*) y canciones.
3. **Desarrollar confianza oral**: Al final de cada módulo, los estudiantes aplican lo aprendido en un **Proyecto Integrador** (*Show & Tell*, póster familiar, horario diario y taller de superhéroes) con guiones guiados y listas de verificación (*checklists*).
4. **Autoevaluar su progreso**: Fomentar la reflexión al cierre de cada sesión mediante la sección *"How did I do today?"*.

## Preview del Workbook

| Portada (Estilo Bauhaus) | Tarjetas de Vocabulario | Actividades Interactivas |
| :---: | :---: | :---: |
| [![Cover][preview-cover]][kids-workbook-pdf] | [![Vocabulary][preview-vocab]][kids-workbook-pdf] | [![Activities][preview-activity]][kids-workbook-pdf] |

## Organización del Libro

El libro está estructurado en **4 módulos temáticos**, compuestos por **24 sesiones interactivas** (6 sesiones por módulo, donde la sexta sesión es siempre un proyecto práctico de cierre) más una sección de **Apéndices**:

| Módulo 1: All About Me (`kidsBlue`) | Módulo 2: Family & Animals (`kidsGreenEsmeralda`) | Módulo 3: Food, Routines & Daily Life (`kidsWarmYellow`) | Módulo 4: Superheroes, Clothes & City (`kidsPink`) |
| :--- | :--- | :--- | :--- |
| **01.** Greetings & Introductions | **07.** Family Members | **13.** Food & Drinks Vocabulary | **19.** Clothes & Accessories |
| **02.** Expressing Emotions | **08.** Describing My Family | **14.** Expressing Likes & Dislikes | **20.** Weather & Seasons |
| **03.** Colors & Numbers 1–20 | **09.** Pets & Domestic Animals | **15.** At the Restaurant – Roleplay | **21.** Places in the City |
| **04.** Big Numbers 21–100 | **10.** Wild Animals & the Zoo | **16.** Daily Routine Verbs | **22.** Prepositions of Place |
| **05.** School Supplies & Objects | **11.** Animal Abilities – Can / Can't | **17.** Days of the Week & Time | **23.** Superhero Workshop |
| **06.** *Project 1 – Show & Tell* | **12.** *Project 2 – Family & Pets Poster* | **18.** *Project 3 – My Daily Schedule* | **24.** *Grand Final – Graduation Showcase* |

- **Apéndices (`sections/appendices/wordlist.tex`)**: Incluye la sección **My Word List**, un glosario de referencia rápida con el vocabulario clave del curso.

### Estructura pedagógica de cada sesión

Cada una de las 24 sesiones sigue un flujo didáctico consistente:
1. **Objective**: Meta comunicativa clara al inicio del capítulo.
2. **Vocabulary Cards**: Palabras clave en inglés con su traducción al español.
3. **Grammar / Learning Tip**: Explicación breve y sencilla de las estructuras gramaticales.
4. **Hands-on Activities (1 a 3)**: Ejercicios para completar espacios, unir conceptos, redactar oraciones o dibujar.
5. **Song / Reading Box**: Canción, rima o lectura corta para reforzar pronunciación y comprensión.
6. **Self-Assessment (*How did I do today?*)**: Evaluación formativa de 1 a 5 estrellas sobre las habilidades adquiridas.

## Compilación y Uso

Para clonar el repositorio y generar el PDF desde el código fuente en LaTeX:

```bash
# Clonar el repositorio
git clone https://github.com/dial999/eng-workbook.git && cd eng-workbook/

# Compilar el Workbook (se ejecuta dos veces para actualizar el índice y referencias)
lualatex --output-directory=build kids.tex
lualatex --output-directory=build kids.tex
```

> **Nota sobre el compilador**: Se requiere `lualatex` (o `xelatex`) debido al uso de `fontspec` para cargar fuentes del sistema (`Segoe UI`, `Bahnschrift`) y el renderizado de emojis e íconos con `HarfBuzz` y `fontawesome5`.

## Estructura del Repositorio

```bash
< PROJECT ROOT >
   |
   |-- build/                 # Carpeta de salida con el PDF compilado (kids.pdf) y archivos auxiliares
   |
   |-- images/                # Recursos gráficos e ilustraciones del documento
   |
   |-- sections/              # Contenido pedagógico dividido por módulos y sesiones
      |
      |-- module1/            # Sesiones 01-06: All About Me
      |-- module2/            # Sesiones 07-12: Family & Animals
      |-- module3/            # Sesiones 13-18: Food, Routines & Daily Life
      |-- module4/            # Sesiones 19-24: Superheroes, Clothes & City
      |-- appendices/         # Glosario final (My Word List) y material complementario
   |
   |-- template/              # Definición de diseño y estilos LaTeX
      |
      |-- book/               # Estructura base de libro (portada, índice, encabezados, páginas)
      |-- generic/            # Configuraciones generales de geometría, tablas y cajas
      |-- kids/               # Tema Kids Edition (paleta de colores, portada Bauhaus, entornos tcolorbox)
   |
   |-- context.tex            # Metadatos globales (Autora, Título, Subtítulo, Nivel A1, Año)
   |
   |-- kids.tex               # Archivo principal de entrada para compilar el Workbook
   |
   |-- main_kids.tex          # Ensamblador de los 4 módulos, 24 sesiones y apéndices
```

## Futuras Propuestas y Mejoras (Roadmap)

- **Ilustraciones y personajes propios**: Integrar vectores e ilustraciones personalizadas en las tarjetas de vocabulario, lecturas y actividades de dibujo.
- **Recursos de audio y pronunciación (QR)**: Añadir códigos QR al inicio de cada sesión y en las cajas de canciones (`songbox`) que enlacen a pistas de audio para practicar *Listening* y pronunciación en casa.
- **Guía del Docente (*Teacher's Edition*)**: Crear una variante de compilación en LaTeX con solucionario integrado (*Answer Key*), dinámicas grupales sugeridas y tiempos estimados por actividad.
- **Expansión a Nivel A2**: Desarrollar un segundo volumen con 24 nuevas sesiones que aborden tiempos pasados, comparativos, direcciones en la ciudad y narración de historias.
- **Material recortable y *Flashcards***: Incluir en los apéndices plantillas de tarjetas recortables, diplomas de graduación para la Sesión 24 y stickers de recompensa.

## Créditos y Autoría

- **Autora del Workbook y Diseño Pedagógico (*Kids Edition*)**: **Diana Lorena Muñoz Ramos** (2026).
- **Arquitectura base de plantilla LaTeX**: Adaptado a partir de [LatHeX Template][lathex-template] por [apehex][github-apehex], inspirado a su vez en *Legrand Orange Book*.

## Licencia

Este proyecto se distribuye bajo la licencia GNU [aGPL v3](LICENSE.txt).

---

[kids-workbook-pdf]: build/kids.pdf
[preview-cover]: build/page_test-001.png
[preview-vocab]: build/page_check-006.png
[preview-activity]: build/page_test2-008.png
[lathex-template]: https://github.com/apehex/lathex-template
[github-apehex]: https://github.com/apehex/
