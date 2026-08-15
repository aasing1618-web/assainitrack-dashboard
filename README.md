# AssainiTrack — Dashboard institutionnel

**En ligne : https://assainitrack-dashboard.vercel.app**

Maquette du tableau de bord institutionnel d'AssainiTrack, plateforme sénégalaise de
traçabilité de la vidange de fosses septiques à Dakar. Destinataires : ONAS et communes
de la région de Dakar.

## Contenu

Un seul fichier : `index.html` — HTML, CSS et JS inclus, police Poppins embarquée en base64.
Seule dépendance externe : Chart.js 4.4.1 chargé depuis cdnjs.

Dix pages navigables, routées par hash (`#/vidanges`, `#/suivi-gps`…) et rendues côté
client. Aucun serveur ni build : le rafraîchissement d'une page profonde fonctionne, et
l'hébergement statique n'a besoin d'aucune règle de réécriture.

| Page | Contenu |
|---|---|
| Dashboard | 6 KPI, carte de suivi + popup camion, stations, activité récente, 2 graphiques, preuves |
| Vidanges | Table filtrable par statut (filtres réellement actifs), 4 KPI |
| Suivi GPS | Carte des positions, popup AT-024, liste de la flotte suivie |
| Opérateurs | Vidangeurs agréés, camion rattaché, zone, charge du jour |
| Ménages | Parc des foyers, échéances de vidange (numéros masqués) |
| Paiements | Répartition Wave / Orange Money / Espèces, encaissements par zone, transactions |
| Preuves de dépotage | Taux de conformité, capacité des stations, registre des scans QR |
| Carte | Cartographie plein écran, densité par zone, état des stations |
| Rapports | Courbe 7 jours, répartition, charge des stations, synthèse chiffrée |
| Paramètres | Profil, seuils d'alerte, notifications (interrupteurs actifs) |

### Données

Les chiffres du cahier des charges sont figés une seule fois dans l'objet `DATA` et tout
le reste en est dérivé par calcul, jamais saisi à la main : 128 vidanges = 17 en cours +
104 terminées + 7 à vérifier, les 1 850 000 FCFA se répartissent exactement entre les trois
moyens de paiement et entre les quatre zones (32 / 26 / 21 / 21 %), le taux de conformité
93,7 % vient de 104 / 111. Les enregistrements nominatifs (ménages, opérateurs) sont des
exemples de présentation ; les numéros de téléphone sont volontairement masqués.

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
