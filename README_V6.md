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


## V6.4 correctif iPhone
- Safe areas iOS/Dynamic Island pour l'en-tête et le cadenas.
- Zone tactile du cadenas agrandie à 48 px.
- Import ND6 tolérant aux espaces et caractères invisibles du presse-papiers.
- Diagnostic ND6 détaillé sans modifier les clés nd6.* ni les données existantes.


## V6.4
- Banque entièrement revue : 300 questions uniques et 300 défis uniques.
- Suppression des déclinaisons artificielles des 100 premiers contenus.
- Conservation des correctifs V6.3 (iPhone/ND6/suppression messages).


## V6.5
- Décodage Base64URL 100 % JavaScript, sans `atob()` : correctif Safari/iPhone.
- Questions et défis : les réponses enregistrées restent visibles (`mine.text`) avec compatibilité anciennes réponses texte.
- Nouveau paquet `NOUS-DEUX-ND65` compressé (gzip si disponible).
- Synchronisation courte différentielle avec accusé logique : les changements non accusés sont renvoyés, pour éviter de perdre une modification si un paquet WhatsApp n'arrive pas.
- Bouton « Sync complète » disponible en secours.
- 300 questions et 300 défis originaux de V6.4 conservés.


## V6.5.2
- ND652 AES-GCM sans compression navigateur.
- IV inclus dans la charge utile : `ND652.<iv+ciphertext>`.
- Import du paquet complet ou de la charge utile seule.
- Diagnostic de création permanent.

## V6.5.4
- Paquet ND654 auto-diagnostique.
- Empreinte courte de clé avant AES-GCM, sans exposer la clé.
- Contrôle de longueur exacte du paquet.
- Contrôle SHA-256 tronqué de la charge chiffrée.
- Erreurs distinctes : clé différente / paquet tronqué / paquet modifié / échec AES.
- Stockage `nd6.*` inchangé : données et appairage conservés.

## V6.5.5 — fragments WhatsApp
- ND654 reste le paquet chiffré et contrôlé.
- Transport ND655F : découpage automatique en fragments d'environ 1800 caractères.
- Chaque fragment possède un identifiant de paquet et une numérotation `n/total`.
- Le récepteur mémorise localement les fragments reçus et indique la progression.
- Fusion uniquement après réception de tous les fragments puis validation ND654 complète.
- Un paquet ND654 complet peut toujours être importé directement.
- Aucune modification de la clé ou des données `nd6.*`.
