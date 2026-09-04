# Pixel Papa — Musique

Outils pour accélérer la production musicale Pixel Papa : écriture (Suno),
calage, sous-titrage, karaoké, animation, SEO/pub. Dépôt indépendant —
aucun rapport avec `insert-coin` (l'appli de cotation brocante Pixel Papa).

## L'outil : boîte à outils chanson

**[sous-titres/](sous-titres/index.html)** — page HTML autonome (aucune
installation, ouvre le fichier directement dans un navigateur). Un seul
calage (paroles + audio), six onglets qui en découlent sans reprendre le
travail :

1. **Calage** — colle les paroles (format Suno, balises `[Refrain]` etc.
   reconnues), charge l'audio, cale au clavier ("tap to sync" — Entrée à
   chaque ligne, fiable à 100 %) avec pré-remplissage optionnel par IA
   (Gemini, clé perso, à corriger ensuite à l'oreille).
2. **Sous-titres** — export `.srt` / `.vtt` pour Premiere/Resolve/CapCut
   ou incrustation ffmpeg.
3. **Karaoké** — export `.ass` avec surlignage doré, ligne entière (exact)
   ou mot par mot (estimation par longueur de mot, à vérifier).
4. **Repères animation** — le même minutage en `.json` (lignes + sections),
   pour caler des keyframes sans réécouter au casque.
5. **Pack SEO / pub** — titres, description YouTube avec chapitres, tags,
   hashtags. Les horodatages des chapitres viennent du calage réel (jamais
   inventés par l'IA) ; seule la partie texte est générée.
6. **Hook / teaser** — repère le refrain (balise ou répétition de lignes)
   et propose une fenêtre de clip courte pour Shorts/Reels.

## Roadmap (pas encore construit)

- Vraie estimation mot-par-mot par IA (au lieu de la répartition par
  longueur de mot actuelle)
- Extraction automatique de plusieurs teasers candidats, pas juste le
  premier refrain trouvé
- Génération de vignettes (prompt image) à partir du pack SEO
