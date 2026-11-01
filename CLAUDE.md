# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Werkwijze met Cindy

- Praat Nederlands en leg dingen simpel uit, stap voor stap.
- Dit is een leerproject voor GitHub (en Claude Code): leg uit wat je doet en waarom.
- Werk altijd op een aparte branch en laat Cindy zelf de pull request maken en mergen.
- Maak kleine commits, één aanpassing per keer. Kleine aanpassingen zijn later makkelijker terug te draaien (revert).
- Verander alleen de regels die nodig zijn. Herformatteer geen code die je niet hoeft aan te passen.

## Het project

Portfolio-homepagina voor cindyhoomans.nl. Het is een statische website met alleen HTML en CSS: geen build-stap, geen package manager, geen tests en geen JavaScript.

Bekijken: open `index.html` in een browser.

- `index.html`: één pagina met de secties hero, `#werk`, `#over` en `#contact`. Het menu bovenaan linkt naar die ankers.
- `style.css`: alle opmaak. Lettertypes (Fraunces voor koppen, Inter voor tekst) komen van Google Fonts via `index.html`.
- `GITHUB-SPIEKBRIEFJE.md`: Cindy's naslag over de GitHub-werkwijze. Houd die in lijn met hoe we werken.

## Kleuren en opmaak

- Alle kleuren staan als CSS-variabelen in `:root` bovenaan `style.css`. Gebruik die variabelen in plaats van losse kleurcodes.
- `--accent` (nu blauw) wordt gedeeld door de knoppen, het "Portfolio"-label, de hover-kleur van het menu en de `h2`-koppen. Verander je `--accent`, dan veranderen al die dingen mee. Benoem dat als je de kleur aanpast.

## Tijdelijke inhoud

De teksten op de pagina (intro, projecten, over mij) zijn nog tijdelijk. Het e-mailadres `hallo@cindyhoomans.nl` is verzonnen en moet nog vervangen worden.
