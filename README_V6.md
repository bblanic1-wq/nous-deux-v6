# Nous Deux V6 — PWA gratuite

V6 destinée à deux appareils (Android + iPhone), sans App Store ni Play Store.

## Nouveautés
- 300 questions thématiques + 300 défis thématiques
- catégorie de défis « Coquin » suggestive et optionnelle
- deux identités distinctes : les réponses ne s'écrasent plus
- compte à rebours jour + heure + minute
- calendrier mensuel + événements du/au pour les week-ends
- espaces à deux avec états Secret / À envoyer / Commun
- ND6 : AES-256-GCM + Base64URL, plus robuste au transport par messagerie
- diagnostic de synchronisation amélioré

## Mise à jour depuis V5
Remplacer les fichiers du dépôt GitHub Pages par ceux de V6, en conservant le dossier icons. Le service worker V6 change de cache.

## Confidentialité
Les données applicatives sont conservées dans le stockage local du navigateur/PWA. La clé du couple est également stockée localement : une PWA ne fournit pas le même niveau de protection qu'un Keychain/Keystore natif. Les paquets ND6 sont chiffrés et authentifiés avant partage. Les éléments marqués Secret ne sont pas exportés.

## Appairage
Chaque téléphone choisit son propre prénom/pseudo. Un téléphone crée la clé, l'autre l'importe. Comparez l'empreinte affichée. Ne publiez jamais la clé dans le dépôt GitHub.


## Correctif V6.1
- Remplace les champs date natifs par des sélecteurs jour/mois/année/heure/minute.
- Calendrier : toucher un jour préremplit les dates Du/Au.
- Conserve les clés localStorage `nd6.*` et donc les données V6 existantes.
- Cache PWA incrémenté vers `nous-deux-v6-2`.


## V6.2 correctif iPhone
- Safe areas iOS/Dynamic Island pour l'en-tête et le cadenas.
- Zone tactile du cadenas agrandie à 48 px.
- Import ND6 tolérant aux espaces et caractères invisibles du presse-papiers.
- Diagnostic ND6 détaillé sans modifier les clés nd6.* ni les données existantes.
