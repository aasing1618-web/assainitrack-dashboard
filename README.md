# AssainiTrack — Dashboard institutionnel

**En ligne : https://assainitrack-dashboard.vercel.app**

Maquette statique (non fonctionnelle) du tableau de bord institutionnel d'AssainiTrack,
plateforme sénégalaise de traçabilité de la vidange de fosses septiques à Dakar.
Destinataires : ONAS et communes de la région de Dakar.

## Contenu

Un seul fichier : `index.html` — HTML, CSS et JS inclus, police Poppins embarquée en base64.
Seule dépendance externe : Chart.js 4.4.1 chargé depuis cdnjs.

Écrans présentés : navigation latérale, 6 cartes KPI, carte de suivi des camions avec
popup de détail, capacité résiduelle des 5 stations de dépotage, activité récente,
graphique d'évolution sur 7 jours, répartition par zone, table des preuves de dépotage.

## Charte graphique

| Rôle | Couleur |
|---|---|
| Navy (sidebar, titres) | `#16324A` |
| Teal (accent) | `#0E7C7B` |
| Amber (alerte, CTA) | `#E1863B` |
| Fond clair | `#FAF8F4` |
| Succès | `#1E9E63` |
| Alerte | `#E0A200` |
| Danger | `#D64545` |

## Lancer en local

Ouvrir `index.html` dans un navigateur, ou servir le dossier :

```bash
npx serve .
```

## Déploiement

Site statique sans build. Sur Vercel : importer le dépôt, aucune configuration
(framework « Other », pas de build command, output = racine du dépôt).
