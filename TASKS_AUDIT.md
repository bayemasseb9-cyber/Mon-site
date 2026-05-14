# Audit rapide de la base de code — tâches proposées

## 1) Coquille typographique à corriger
**Constat**
- Le lien de démonstration du projet « Beauté & Bien-être » pointe vers `Demo.sallon` (double `l`), ce qui ressemble à une coquille (`salon`).

**Tâche proposée**
- Corriger l’URL `https://bayemasseb9-cyber.github.io/Demo.sallon/` vers la bonne orthographe du slug (probablement `Demo.salon`) et vérifier que le lien répond en HTTP 200.

**Priorité**: Moyenne

## 2) Bug fonctionnel à corriger
**Constat**
- Le commentaire annonce un « chargement des icônes corrigé », mais la balise CSS Font Awesome est incomplète: `https://cdnjs.cloudflare.com` sans chemin vers le fichier CSS.
- Résultat probable: les icônes (`fa-*`) ne s’affichent pas.

**Tâche proposée**
- Remplacer le `href` actuel par une URL Font Awesome complète et versionnée (avec intégrité/SRI si possible), puis valider visuellement l’affichage des icônes dans les sections Services, Portfolio et CTA.

**Priorité**: Haute

## 3) Commentaire / documentation à corriger
**Constat**
- Le commentaire `<!-- Chargement des icônes CORRIGÉ -->` est incohérent avec l’implémentation réelle (lien CSS incomplet).
- La documentation (`README.md`) est trop minimale pour contribuer/tester (pas d’instructions d’exécution ni de vérification).

**Tâche proposée**
- Aligner le commentaire avec la réalité (ou le supprimer), puis enrichir le README avec:
  - objectif du site,
  - structure des fichiers (`index.html`, `index#.html`),
  - procédure de lancement local,
  - checklist de vérification (liens, icônes, responsive).

**Priorité**: Moyenne

## 4) Amélioration de test
**Constat**
- Le projet ne contient pas de tests automatisés pour valider les régressions UI de base.

**Tâche proposée**
- Ajouter un test E2E léger (Playwright) qui vérifie:
  1. que la page d’accueil charge (status 200),
  2. que les icônes majeures sont présentes dans le DOM,
  3. que les liens externes critiques (démos, WhatsApp, téléphone) ont des `href` valides,
  4. qu’un screenshot de non-régression est généré.

**Priorité**: Haute
