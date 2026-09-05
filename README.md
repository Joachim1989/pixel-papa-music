# Pixel Papa — Musique

Outils pour accélérer la production musicale Pixel Papa : de l'écriture
(Suno) jusqu'au pack de publication. Dépôt indépendant — aucun rapport
avec `insert-coin` (l'appli de cotation brocante Pixel Papa).

## L'outil : boîte à outils chanson

**[sous-titres/](sous-titres/index.html)** — page HTML autonome (aucune
installation, ouvre le fichier directement dans un navigateur). Un seul
calage (paroles + audio), neuf onglets qui en découlent sans reprendre le
travail :

0. **Écriture** — pas un générateur : récupère le titre/les paroles déjà
   écrits en conversation avec Claude (skill `pixel-papa-suno`, qui
   propose des angles puis vérifie rimes/minutage/prononciation avant de
   livrer) et les envoie vers le Calage. Inclut un pense-bête (checklist
   qualité + rappel que Suno limite les téléchargements, pas les crédits).
1. **Calage** — colle les paroles (balises `[Refrain]` etc. reconnues),
   charge l'audio, cale au clavier ("tap to sync" — Entrée à chaque
   ligne, fiable à 100 %) avec pré-remplissage optionnel par IA (Gemini,
   clé perso). Une fois calées, les lignes défilent toutes seules à
   l'écoute (suivi de lecture) pour vérifier sans rien taper.
2. **Sous-titres** — export `.srt` / `.vtt`.
3. **Karaoké** — export `.ass`, surlignage doré, ligne entière (exact) ou
   mot par mot (estimation, à vérifier).
4. **Repères animation** — le même minutage en `.json` (lignes + sections).
5. **Pack SEO / pub** — titres, description YouTube avec chapitres réels,
   tags, hashtags.
6. **Hook / teaser** — repère le refrain (balise ou répétition) et
   propose une fenêtre de clip courte pour Shorts/Reels.
7. **Visuels** — vignette YouTube + storyboard (une image par section),
   générés directement (Gemini). Style calé sur une fiche éditable ou
   extrait d'une image de référence (transfert de style/personnage,
   comme le skill `style-transfer-portrait`) ; chaque scène est
   régénérable (prompt éditable) ; cohérence de personnage d'une scène à
   l'autre via chaînage ; format 16:9/9:16/1:1 au choix.
8. **Aperçu** — previz dans le navigateur (pas un export vidéo) :
   enchaîne les images du storyboard au bon timing avec les sous-titres
   par-dessus, pour valider le rythme avant de monter dans
   CapCut/VN/Canva.

## Choix d'architecture qui comptent

- **L'écriture reste conversationnelle.** Le skill `pixel-papa-suno`
  propose des angles et fait un vrai contrôle qualité (rimes, bars,
  prononciation) avant de livrer — un bouton "générer" dans l'outil
  produirait un texte moins abouti en sautant ces vérifications.
  L'onglet 0 ne fait que relayer, pas écrire.
- **Le montage reste externe** (CapCut/VN/Canva confirmés à l'usage) :
  l'outil fournit les matériaux (sous-titres, karaoké, images, repères),
  jamais un export vidéo — hors de portée d'une page statique.
- **Aucune image générée n'est sauvegardée** (trop lourd pour
  localStorage) : un avertissement bloque la fermeture/rafraîchissement
  tant qu'il y a des visuels non téléchargés dans la session.
- **Le dernier modèle image qui a fonctionné est mémorisé** (comme le
  modèle texte) pour éviter de retenter des modèles en échec à chaque
  scène du storyboard.

## Roadmap (pas encore construit)

- Variantes multiples par scène (choisir parmi 2-3 plutôt qu'une seule)
- "Réessayer seulement les échecs" plutôt que relancer tout le storyboard
- Extraction automatique de plusieurs teasers candidats
- Suite de tests committée (aujourd'hui vérifié ad hoc avec Playwright à
  chaque changement, rien n'est gardé dans le dépôt)
