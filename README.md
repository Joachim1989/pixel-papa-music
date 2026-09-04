# Pixel Papa — Musique

Outils pour accélérer la production musicale Pixel Papa : écriture (Suno),
sous-titrage, et à terme karaoké/animation/SEO. Dépôt indépendant — aucun
rapport avec `insert-coin` (l'appli de cotation brocante Pixel Papa).

## Outils

- **[sous-titres/](sous-titres/index.html)** — cale les paroles d'une
  chanson sur son audio et exporte des sous-titres `.srt`/`.vtt` prêts pour
  le montage. Page HTML autonome, aucune installation : ouvre le fichier
  directement dans un navigateur.

  Le point de départ : les paroles sont déjà connues (écrites pour le
  prompt Suno), donc le vrai problème n'est pas la transcription mais le
  *calage temporel*. Deux méthodes combinables :
  - **tap to sync** — lecture de l'audio + touche Entrée à chaque ligne,
    fiable à 100 %, aucune IA requise ;
  - **pré-remplissage IA (Gemini, clé perso)** — dégrossit le calage à
    partir de l'audio + des paroles numérotées, à corriger ensuite à
    l'oreille.

## Roadmap (pas encore construit)

- Export karaoké `.ass` (surlignage mot par mot, branding Pixel Papa)
- Repères de timing exportés en JSON pour caler l'animation (After Effects/Blender)
- Pack SEO auto (titre, description avec chapitres, tags, hashtags)
- Extraction automatique du refrain pour les teasers courts (Shorts/Reels)
