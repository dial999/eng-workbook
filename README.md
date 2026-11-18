# Kidz Labz — English & Fun for Kids

> An interactive A1 English Workbook for kids (ages 9–12), built with LaTeX and the LatHeX template.

You can preview the compiled workbook in [build/kids.pdf][kids-workbook-pdf].

## Curriculum Overview

| Module 1: All About Me | Module 2: Family & Animals | Module 3: Food, Routines & Daily Life | Module 4: Superheroes, Clothes & City |
| :--- | :--- | :--- | :--- |
| 1. Greetings & Introductions | 7. Family Members | 13. Food & Drinks Vocabulary | 19. Clothes & Accessories |
| 2. Expressing Emotions | 8. Describing My Family | 14. Expressing Likes & Dislikes | 20. Weather & Seasons |
| 3. Colors & Numbers 1–20 | 9. Pets & Domestic Animals | 15. At the Restaurant – Roleplay | 21. Places in the City |
| 4. Big Numbers 21–100 | 10. Wild Animals & the Zoo | 16. Daily Routine Verbs | 22. Prepositions of Place |
| 5. School Supplies & Objects | 11. Animal Abilities – Can / Can't | 17. Days of the Week & Time | 23. Superhero Workshop |
| 6. Project 1 – Show & Tell | 12. Project 2 – Family & Pets Poster | 18. Project 3 – My Daily Schedule | 24. Grand Final – Graduation Showcase |

## Base Themes Preview

| Dark Theme                                       | Light Theme                                         | Forta Theme                                         |
| :----------------------------------------------: | :-------------------------------------------------: | :-------------------------------------------------: |
| [![Dark title page][demo-dark-title]][demo-dark] | [![Light title page][demo-light-title]][demo-light] | [![Forta title page][demo-forta-title]][demo-forta] |
| [![Dark page][demo-dark-page]][demo-dark]        | [![Light page][demo-light-page]][demo-light]        | [![Forta page][demo-forta-page]][demo-forta]        |

## Usage

To clone and compile the workbook from the repository:

```bash
# Get the code
git clone https://github.com/dial999/eng-workbook.git && cd eng-workbook/

# Build the Kids Workbook
lualatex --output-directory=build kids.tex
lualatex --output-directory=build kids.tex
```

The recommended compiler is `lualatex` (required for `fontspec`, custom `ttf`/`otf` fonts like Nunito, and emoji support via `Segoe UI Emoji` with the HarfBuzz renderer).

## Project structure

The project has the following tree:

```bash
< PROJECT ROOT >
   |
   |-- build/                 # Where the compiled pdf (kids.pdf) will pop, as well as temp files
   |
   |-- images/                # Assets and illustrations used in the workbook
   |
   |-- sections/              # All the individual sessions and modules
      |
      |-- module1/            # Sessions 01-06: All About Me
      |
      |-- module2/            # Sessions 07-12: Family & Animals
      |
      |-- module3/            # Sessions 13-18: Food, Routines & Daily Life
      |
      |-- module4/            # Sessions 19-24: Superheroes, Clothes & City
      |
      |-- appendices/         # Word list and extra reference materials
   |
   |-- template/              # The actual template definition, independent from the document
      |
      |-- book/               # Base book layout, cover, TOC, and titles
      |
      |-- generic/            # Core styling (boxes, fonts, geometry, tables, themes)
      |
      |-- kids/               # Kids workbook theme (custom colors, Bauhaus cover, activity boxes)
   |
   |-- context.tex            # Workbook metadata (author, title, subtitle, level, year)
   |
   |-- kids.tex               # Main entry point that loads the Kids theme and compiles the workbook
   |
   |-- main_kids.tex          # Script that assembles all 4 modules, 24 sessions, and appendices
```

## Credits

The workbook content and Kids Edition theme were created by **Diana Lorena Muñoz Ramos**.

This project is built upon the [LatHeX Template][lathex-template] by [apehex][github-apehex], which has roots in the popular LaTeX scripts mentioned below.

### LatHeX & Solidity Highlighting

Base template architecture by [apehex][github-apehex]. The syntax highlighting for Solidity was made by [Sergei Tikhomirov][solidity-syntax-highlighting].

### Legrand Orange Book

The underlying template started from the [Legrand Orange template][legrand-orange-book].

### Latexdraw.com

The base cover page started from the templates in [Latexdraw][latexdraw-cover-pages].

## License

This work is licensed under the GNU [aGPL v3](LICENSE.txt).

---

[kids-workbook-pdf]: build/kids.pdf
[demo-dark]: dark.tex
[demo-forta]: forta.tex
[demo-light]: light.tex
[demo-dark-page]: images/dark-page.png
[demo-forta-page]: images/forta-page.png
[demo-light-page]: images/light-page.png
[demo-dark-title]: images/dark-title.png
[demo-forta-title]: images/forta-title.png
[demo-light-title]: images/light-title.png
[lathex-template]: https://github.com/apehex/lathex-template
[github-apehex]: https://github.com/apehex/
[latexdraw-cover-pages]: https://latexdraw.com/tikz-cover-pages-gallery/
[legrand-orange-book]: https://www.latextemplates.com/template/legrand-orange-book
[solidity-syntax-highlighting]: https://github.com/s-tikhomirov/solidity-latex-highlighting
