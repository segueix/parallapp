# Parallax 360 · galeria automàtica i RV

Aplicació web estàtica per veure fotos equirectangulars 360° amb profunditat calculada al navegador, parallax avançat, galeria integrada i mode RV/WebXR quan el dispositiu ho suporta.

## Estructura recomanada del repositori

```text
el-teu-repositori/
  index.html
  README.md
  fotos/
    001.jpg
    002.jpg
    003.jpg
```

La carpeta s'ha de dir exactament `fotos` i ha d'estar a l'arrel del repositori, al mateix nivell que `index.html`.

## Noms de les imatges

Format recomanat:

```text
fotos/001.jpg
fotos/002.jpg
fotos/003.jpg
fotos/004.jpg
```

També s'admet aquest altre format:

```text
fotos/foto-001.jpg
fotos/foto-002.jpg
fotos/foto-003.jpg
```

Regles importants:

- Comença per `001`.
- Fes servir tres xifres: `001`, `002`, `003`, etc.
- Mantén la numeració consecutiva. Evita salts grans, perquè l'app s'atura quan troba massa números buits seguits.
- Escriu les extensions en minúscules.
- Extensions admeses: `.jpg`, `.jpeg`, `.png`, `.webp` i `.avif`.
- Evita espais i accents en els noms dels fitxers.

La cerca automàtica comprova fins a `200` imatges.

## Opció amb noms lliures

Si vols usar noms com `claustre.jpg`, `sala-antiga.jpg` o `joc-tauler-medieval.jpg`, crea un fitxer `galeria.json` o `gallery.json` a l'arrel del repositori:

```json
[
  { "title": "Claustre", "src": "fotos/claustre.jpg" },
  { "title": "Sala antiga", "src": "fotos/sala-antiga.jpg" },
  { "title": "Joc de tauler medieval", "src": "fotos/joc-tauler-medieval.jpg" }
]
```

L'app també comprova `fotos/galeria.json` i `fotos/gallery.json`.

## Funcions

- Galeria integrada amb miniatures, sense numeració visible sobre la imatge.
- Càrrega automàtica d'imatges guardades al repositori de GitHub.
- Càrrega múltiple d'imatges locals i arrossegar/deixar anar.
- Profunditat automàtica amb `depth-anything-v2-small` via Transformers.js.
- Parallax geomètric dins d'una esfera 360° amb suavitzat de vores.
- Mode WebXR immersive-vr: Three.js renderitza una vista per a cada ull quan el navegador i el visor ho suporten.
- Botó de rotació automàtica: primer clic cap a la dreta, segon clic cap a l'esquerra, tercer clic l'atura.
- Menú i galeria amagables quan el cursor no és a sobre.
- Pantalla completa i recàlcul de profunditat.

## Publicació a GitHub Pages

1. Puja `index.html` a l'arrel del repositori.
2. Crea la carpeta `fotos/` i puja-hi les imatges.
3. Activa GitHub Pages des de `Settings` → `Pages`.
4. Obre la URL publicada. L'app buscarà la galeria automàticament.

El primer ús necessita connexió per baixar el model de profunditat. WebXR i WebGPU depenen del navegador, del dispositiu i del context segur HTTPS.
