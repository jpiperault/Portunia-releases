# Feuille de route

[English](ROADMAP.md) · **Français**

Ce qui est prévu pour **Portunia**, **Portunia Gate** et **Portunia Assist**. Pas de dates : l'ordre peut changer selon vos retours.

*Mise à jour : 5 novembre 2026 · Portunia 0.70 · Portunia Gate 0.30*

## Maintenant

Ce sur quoi nous travaillons.

- **Essais en conditions réelles** des dernières nouveautés : copie de fichiers en Bureau à distance, Proxmox VE (création de machines, gestion des nœuds), interfaces web par la Gate, Bureau à distance au coffre.
- **Installateur signé** : plus d'avertissement Windows SmartScreen au téléchargement de Portunia et de Portunia Assist.
- **Suivre une session en direct** depuis le lecteur de l'Audit, avec un bouton « Couper la session » (et, au choix, désactiver le compte).
- **Exporter une session en vidéo** (MP4) à la demande, avec sous-titres et filigrane ; chaque export est inscrit au journal.

## Ensuite

Prévu après, dans cet ordre approximatif.

**Portunia Gate**

- **Approbation des accès** : une règle peut exiger l'accord d'un approbateur, avec motif, durée et numéro de ticket. Demande possible depuis Portunia ou le portail web.
- **Alertes** : commande sensible, échecs de connexion répétés, saisie révélée, journal altéré ; par e-mail, Microsoft Teams ou webhook signé.
- **Authentification unique** (OIDC, SAML) pour la Gate et le portail web.
- **Portail web** : clés d'accès (passkeys), logo de l'entreprise, copier-coller réglable par règle.
- **Bureau à distance** : connexion par la Gate depuis le client Windows (mstsc) et Remmina, en plus de Portunia.

**Portunia**

- **Nouveaux stockages** dans les sessions de fichiers à deux volets : WebDAV, partages Windows (SMB), Azure Blob, Google Cloud Storage.
- **Reprise des transferts interrompus** et comparaison de dossiers par contenu.
- **Lecteur détachable** : revoir une session dans une fenêtre à part.
- **Bureau à distance** : certificat du serveur mémorisé à la première connexion, comme les clés SSH.

**Portunia Assist**

- **Inviter par un lien**, en plus du code lu au téléphone.
- **Discussion, fichiers et presse-papiers** pendant l'assistance.
- **Plusieurs écrans** et bouton **« Demander l'administration »** (élévation Windows).
- **Historique** des assistances, des deux côtés.
- **Android** : prise en main de l'appareil (aujourd'hui, vue seule).

## Plus tard

Envisagé, à préciser.

- **Portunia sur macOS et Linux** : la même application, avec les mêmes protocoles, la connexion par une Gate et l'administration.
- **Synchronisation chiffrée de bout en bout** des sessions entre vos ordinateurs, Windows, macOS ou Linux.
- **Partage de sessions et d'identifiants** dans une équipe, avec droits et déploiement centralisé.
- **Rotation automatique** des mots de passe gardés au coffre de la Gate.
- **Accès sans surveillance** à vos propres PC (« Mes PC ») avec Portunia Assist, et logo de votre société pour vos clients.
- **Portunia Assist sur macOS et Linux.**
- **Extensions tierces** dans le catalogue : téléchargées, signées et isolées.

## Déjà livré récemment

- **0.70** : Proxmox VE, création de machines virtuelles et de conteneurs, gestion des nœuds (mises à jour, services, journal, réseau, disques).
- **0.69** : copie de fichiers en Bureau à distance, contrôlée et tracée par la Gate.
- **0.66 à 0.68** : Proxmox VE dans la barre latérale, avec supervision.
- **0.67** : interfaces web (vCenter, iDRAC, pare-feu…) ouvertes par la Gate.
- **0.65** : Bureau à distance au coffre (la Gate fournit le compte Windows), options du Bureau à distance (résolution, passerelle RD, RemoteApp…).

Le détail de chaque version est sur la [page des versions](https://github.com/jpiperault/Portunia-releases/releases).

## Donner votre avis

Une fonction vous manque, ou l'ordre ne vous convient pas ? Ouvrez une [issue](https://github.com/jpiperault/Portunia-releases/issues) : les demandes les plus partagées passent en premier.
