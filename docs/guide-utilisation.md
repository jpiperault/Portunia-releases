# Guide d'utilisation

*Portunia 0.69.0 · Portunia Gate 0.30.0 · Mise à jour : 5 novembre 2026*

> Le guide d'administration de la Gate est dans [Portunia-Gate-releases](https://github.com/jpiperault/Portunia-Gate-releases/blob/main/docs/guide-administration.md).

Se connecter à ses serveurs avec Portunia, transférer des fichiers, travailler par une Gate, utiliser le portail web et donner ou recevoir de l'aide à distance. Aucune connaissance de l'administration n'est nécessaire.

<a id="bienvenue"></a>

## 1\. Quel chapitre pour vous ?

Portunia réunit vos connexions dans une seule fenêtre Windows. Ce guide s'adresse à plusieurs profils ; allez directement à ce qui vous concerne.

| Vous êtes | Commencez par |
| --- | --- |
| Utilisateur seul, avec vos propres serveurs | [Installer](#installer), [Première connexion](#premiere), puis [Sessions](#sessions). |
| Salarié dont l'entreprise a une Gate | [Installer](#installer), puis [Se connecter par une Gate](#Gate). |
| Utilisateur sans Portunia, sur un autre poste | [Le portail web](#portail). |
| Dépanneur | [Dépanner quelqu'un](#depanner). |
| Personne qui se fait aider | [Être dépanné](#aide). Vous n'avez besoin de rien d'autre. |

> [!NOTE]
> **Administrateurs** — Créer des comptes, ajouter des serveurs ou régler les droits est décrit dans le guide d'administration.

### Les mots utiles

| Mot | Sens |
| --- | --- |
| Session | Une connexion enregistrée : adresse, identifiant, réglages. Elle s'ouvre dans un onglet. |
| Hôte | L'adresse de la machine : un nom (`srv-01.exemple.fr`) ou une IP (`10.0.0.12`). |
| Gate | Serveur de l'entreprise par lequel passent toutes les connexions. Il vérifie qui vous êtes et ce que vous avez le droit d'ouvrir. |
| Code | Les 6 chiffres qui changent toutes les 30 secondes dans l'application d'authentification de votre téléphone. |
| Empreinte | Identité numérique d'une machine. Elle permet de vérifier qu'on parle bien au bon serveur. |
| Extension | Dans Portunia, chaque protocole est une extension que l'on peut activer ou désactiver. |

<a id="installer"></a>

## 2\. Installer Portunia

1.  Téléchargez `Portunia_x.y.z_x64-setup.exe` depuis [la page des versions](https://github.com/jpiperault/Portunia-releases/releases), ou le lien donné par votre entreprise.
2.  Ouvrez le fichier et choisissez : **pour moi seulement** (sans droits d'administrateur, dans votre profil Windows) ou **pour tous les utilisateurs de ce PC** (dans Program Files, droits d'administrateur demandés). Les mises à jour gardent ce choix ; une installation pour tous demande l'autorisation de Windows à chaque mise à jour.
3.  Si Windows SmartScreen avertit, cliquez sur « Informations complémentaires » puis « Exécuter quand même ». L'installateur n'a pas encore de certificat de signature de code.
4.  Lancez Portunia. Il s'affiche dans la langue de Windows, en anglais ou en français.

Portunia cherche ses mises à jour au démarrage. Une bannière propose la nouvelle version ; rien ne s'installe sans votre accord. Vos sessions et réglages sont conservés.

### Éditions

| Édition | Contient |
| --- | --- |
| **Gratuit** | Les connexions, le terminal, les fichiers, les tunnels, les outils réseau, le verrouillage. |
| **Pro** | En plus : alertes de supervision, tableau de bord serveur, commande sur plusieurs serveurs, conteneurs, enregistrement des sessions, stockage S3. |
| **Équipes** | En plus : administration et audit d'une Gate. |

> [!NOTE]
> **Avant-première** — Pendant cette période, toutes les fonctions sont débloquées dans chaque édition.

<a id="premiere"></a>

## 3\. Première connexion

### Le plus rapide : connexion rapide

1.  Appuyez sur Ctrl+Maj+Q.
2.  Tapez l'adresse, par exemple `deploy@10.0.1.12` ou `rdp srv-01`.
3.  À la première connexion SSH, Portunia affiche l'empreinte du serveur. Acceptez si vous l'avez vérifiée ou si vous êtes sur votre réseau.
4.  Saisissez le mot de passe si le serveur le demande.

Rien n'est enregistré. La connexion reste dans l'historique récent et « Enregistrer comme session » la garde pour la prochaine fois.

### Pour une machine que vous utilisez souvent : une session

1.  Ctrl+Maj+N ouvre « Nouvelle session ».
2.  Choisissez le protocole, donnez un nom, indiquez l'hôte et l'utilisateur.
3.  Enregistrez, puis double-cliquez sur la session dans la barre latérale.

> [!NOTE]
> **Mot de passe** — Laissez le champ vide pour qu'il soit demandé à chaque connexion. S'il est rempli, il va au Gestionnaire d'identifiants de Windows, jamais dans un fichier en clair.

<a id="fenetre"></a>

## 4\. La fenêtre en bref

| Zone | Rôle |
| --- | --- |
| Rail (colonne d'icônes à gauche) | Choisit le panneau affiché : **Sessions**, **Gates**, **Ce PC** (shells locaux). Dessous : commandes enregistrées, identifiants partagés, enregistrements, assistance, outils réseau, import ; en bas, extensions et paramètres. Un clic sur l'icône du panneau ouvert replie la barre. |
| Panneau Sessions | Le filtre, les puces, les sessions **épinglées** et **récentes**, puis vos dossiers ; en bas, « Toutes les sessions en tableau ». |
| Onglets | Une connexion par onglet. Ctrl+Maj+W ferme l'onglet actif. |
| Barre d'outils de l'onglet | Toujours sur une ligne : l'adresse de la connexion, puis les actions (commandes, recherche, enregistrement, écran partagé, tunnels, clé SSH, modifier), le groupe des **panneaux** (Fichiers, Notes, Serveur, Conteneurs) et Déconnecter. Quand la fenêtre rétrécit, les libellés disparaissent (le nom reste en infobulle), puis les actions rares passent dans le menu **⋯**. |
| Panneau de droite | Ouvert depuis le groupe des panneaux ; ses onglets passent de Fichiers à Notes, Serveur ou Conteneurs, la croix le ferme. Dans une fenêtre étroite, il s'ouvre par-dessus le terminal. |
| Barre d'état | L'édition et la version. Cliquez pour accéder à la licence dans Paramètres. |

### La palette : tout retrouver au clavier

Ctrl+Maj+O ouvre une liste qui contient vos sessions, vos shells locaux et les actions de Portunia. Tapez quelques lettres puis Entrée. Si vous tapez une adresse, Portunia propose de s'y connecter. C'est aussi le chemin le plus court vers Paramètres, Clés SSH ou Outils réseau.

<a id="sessions"></a>

## 5\. Sessions et dossiers

Rangez vos sessions dans des dossiers imbriqués et glissez-les de l'un à l'autre. Le clic droit donne les actions disponibles.

| Sur | Clic droit |
| --- | --- |
| Une session | Ouvrir, Épingler en haut, Modifier, Dupliquer, Sortir du dossier, Supprimer, Ping, traceroute, ports…, Réveiller (Wake-on-LAN, si une adresse MAC est renseignée). |
| Un dossier | Nouvelle session ici, Nouveau sous-dossier, Renommer, Couleur…, Lancer une commande sur ce dossier… (Pro), Supprimer le dossier. |

> [!WARNING]
> **Conseil** — Donnez une couleur rouge à votre dossier de production. Les sessions héritent d'un bandeau bien visible, et la commande sur plusieurs serveurs demande une confirmation renforcée.

### Plusieurs sessions à la fois

-   **Écran partagé** : jusqu'à 4 sessions côte à côte (bouton de la barre d'outils, ou « Afficher à côté » sur un onglet).
-   **Saisie multiple** (Ctrl+Maj+B) : ce que vous tapez part dans toutes les sessions affichées. Le bouton passe à « Saisie multiple : ACTIVE » ; vérifiez-le avant de taper une commande.

### Retrouver une session parmi beaucoup

-   Ctrl+Maj+K place le curseur dans le filtre. Tapez quelques lettres du nom, de l'adresse, du dossier ou d'une étiquette : la liste devient à plat, avec l'adresse et le dossier sous chaque nom. Entrée ouvre la première, ↓ parcourt la liste, Échap efface le filtre.
-   **Puces** sous le filtre : Connectées, Épinglées, un protocole (SSH, RDP…) ou une étiquette parmi les plus utilisées. Un second clic sur la puce l'enlève.
-   **Épingler** (étoile au survol, ou clic droit) : la session reste en tête du panneau. Les 5 dernières sessions ouvertes apparaissent sous **Récentes**.
-   Le filtre s'applique aussi aux serveurs des Gates : une ligne « N serveur(s) dans les Gates » mène au panneau Gates.
-   **Toutes les sessions en tableau** (en bas du panneau, ou la palette) : un onglet triable par nom, adresse, protocole, dossier, étiquettes ou dernière ouverture, avec des filtres par dossier, protocole et étiquette. Cochez plusieurs sessions pour les ouvrir ensemble ou y lancer une commande (Pro). Double-clic ou Entrée ouvre une session, F2 la modifie.

<a id="protocoles"></a>

## 6\. Se connecter à chaque type de machine

Une extension désactivée disparaît des menus, mais ses sessions sont conservées. Pour en réactiver une : palette, puis « Extensions ».

SFTP et FTP / FTPS sont dans le **catalogue**, en bas de la page Extensions : cliquez sur « Installer » pour les ajouter à la fenêtre « Nouvelle session ». Si vous aviez déjà des sessions FTP, l'extension est installée d'office.

| Protocole | Pour | À renseigner |
| --- | --- | --- |
| **SSH** | Serveurs Linux, équipements réseau. | Hôte, utilisateur, authentification : clé privée, mot de passe ou agent (Pageant, OpenSSH). |
| **Bureau à distance** | Windows. | Hôte, `DOMAINE\utilisateur`, affichage dans un onglet ou dans le client Windows. Dans un onglet, Portunia exige NLA, comme Windows par défaut : un faux serveur ne peut pas obtenir votre mot de passe. Pour un serveur de confiance qui ne le propose pas (xrdp sous Linux, ancien Windows), cochez « Accepter les serveurs sans NLA ». |
| **VNC** | Linux, macOS, Raspberry Pi. | Hôte et port. |
| **Shell local** | PowerShell, Invite de commandes, WSL, Git Bash de ce PC. | Rien : panneau **Ce PC** du rail, ou Ctrl+Maj+T pour le shell par défaut. « Ouvrir en administrateur » utilise une fenêtre séparée. |
| **Telnet** | Anciens équipements. | Hôte. Telnet n'est pas chiffré : réservez-le au réseau local. |
| **Port série** | Microcontrôleurs, consoles de commutateurs et routeurs. | Port COM, vitesse. Portunia propose les ports présents. |
| **SFTP** | Fichiers d'un serveur Linux, sans terminal. | Comme SSH : hôte, utilisateur, clé, agent ou mot de passe, rebond. Dossiers de départ du serveur et de ce PC, facultatifs. |
| **FTP / FTPS** | Serveurs de fichiers. | Hôte, identifiants. FTPS explicite est le choix par défaut ; FTPS implicite utilise le port 990. Mode actif et encodage Windows-1252 pour les anciens serveurs. |
| **Stockage S3** Pro | AWS, MinIO, Scaleway, OVH, Wasabi, R2. | Point d'accès, clés d'accès. Envoi jusqu'à 5 Go par fichier. |
| **Interface web** | Consoles de NAS, routeur, hyperviseur. | L'adresse. La page s'ouvre dans une fenêtre isolée de Portunia. |

### Options SSH utiles

| Option | Quand l'utiliser |
| --- | --- |
| Serveur de rebond | La machine n'est joignable qu'à travers une autre. Indiquez une session SSH ou `utilisateur@hôte:port`, jusqu'à 3 niveaux. |
| Compatibilité anciens équipements | Un vieil équipement refuse la connexion. L'option autorise des algorithmes faibles ; ne l'activez que pour lui. |
| Afficher les applications graphiques (X11) | Vous lancez une application graphique du serveur. Il faut un serveur X sur ce PC, comme VcXsrv ou X410. |
| Adresse MAC | Pour réveiller la machine avec Wake-on-LAN. |

<a id="terminal"></a>

## 7\. Le terminal

| Pour | Faites |
| --- | --- |
| Copier, coller | Clic droit : avec une sélection il copie, sans sélection il colle, comme PuTTY. Réglable dans Paramètres. |
| Rechercher dans le texte | Ctrl+Maj+F. |
| Changer la taille du texte | Ctrl + molette. |
| Ouvrir un lien | Ctrl + clic. Un simple clic sélectionne. |
| Se reconnecter | Bouton « Reconnecter » ou Entrée. Après une coupure réseau ou une mise en veille, Portunia se reconnecte tout seul. |

Les raccourcis de Portunia commencent tous par Ctrl+Maj. Ctrl+W, Ctrl+K et les autres restent aux programmes du terminal, comme vim ou nano.

Avant de coller plusieurs lignes, Portunia demande confirmation : un collage peut lancer des commandes sans que vous ayez appuyé sur Entrée. Les erreurs ressortent en rouge, les avertissements en orange, les succès en vert et les adresses IP en cyan. Ces règles sont modifiables dans Paramètres.

<a id="fichiers"></a>

## 8\. Fichiers et transferts

Dans une session SSH, ouvrez le panneau **Fichiers** à droite du terminal. Pour n'avoir que les fichiers, clic droit sur la session SSH, puis « Ouvrir en fichiers seulement (SFTP) » : ses réglages (clé, rebond) servent tels quels.

Les sessions SFTP, FTP et S3 s'ouvrent en **deux volets** : **Ce PC** à gauche, le serveur à droite, la file de transferts en bas.

### Deux volets

| Action | Comment |
| --- | --- |
| Choisir plusieurs fichiers | Ctrl+clic, Maj+clic, ou Ctrl+A dans un volet. |
| Envoyer vers le serveur | Flèche → ou F5. Double-clic sur un fichier de ce PC fait de même. |
| Récupérer sur ce PC | Flèche ← ou F6, dans le dossier ouvert à gauche. Double-clic sur un fichier du serveur fait de même. |
| Fichier déjà présent | Règle « Si le fichier existe » de la file : demander, remplacer si plus récent, remplacer, ignorer. « Demander » pose une seule question pour toute la sélection. |
| Suivre les transferts | Avancement et débit dans la file. « Pause » arrête de lancer les suivants ; la croix retire un transfert en attente. |
| Fichiers cachés | Bouton « Fichiers masqués » : fichiers commençant par un point, et fichiers cachés de Windows. |

### Comparer et synchroniser Pro

Le bouton **Comparer et synchroniser** des deux volets compare le dossier ouvert sur ce PC et celui du serveur, sous-dossiers compris. La comparaison ne copie rien : elle liste les écarts et la raison de chacun.

| Réglage | Effet |
| --- | --- |
| Sens | **Envoyer** met le serveur à jour, **Récupérer** met ce PC à jour, **Les deux** copie chaque fichier vers le côté où il est plus ancien ou absent. |
| Comparer par | Date et taille (conseillé), ou taille seulement quand les horloges ne sont pas fiables. |
| Exclure | Motifs séparés par des espaces : `.git/` pour un dossier, `*.log` pour des noms, `dist/*.map` pour un chemin. |
| Supprimer sur le serveur | En envoi seulement, décoché par défaut : retire du serveur ce qui n'existe plus sur ce PC, après confirmation. Rien n'est jamais supprimé sur ce PC. |

Les lignes en orange sont à trancher : même date mais contenu différent, ou fichier d'un côté et dossier de l'autre. Choisissez « Envoyer », « Récupérer » ou « Ignorer ». Un fichier plus récent du côté d'arrivée n'est pas coché d'office. « Synchroniser » place les copies dans la file de transferts ; les deux volets se rechargent à la fin. Les copies gardent la date de l'original (en FTP, si le serveur accepte MFMT ; pas en S3), si bien qu'une nouvelle comparaison les voit identiques.

### Panneau Fichiers d'une session SSH

| Action | Comment |
| --- | --- |
| Envoyer | Glissez des fichiers ou dossiers sur le panneau, ou utilisez « Envoyer des fichiers » et « Envoyer un dossier ». |
| Télécharger | Double-clic sur un fichier, ou « Télécharger le dossier entier ». |
| Renommer, supprimer | F2, Suppr. |
| Créer un dossier | « Nouveau dossier ». |
| Modifier sur place | « Ouvrir dans mon éditeur ». Le fichier s'ouvre sur votre PC et repart sur le serveur à chaque enregistrement, jusqu'à « Arrêter la synchronisation » ou la fermeture de la session. |

> [!NOTE]
> **Fichiers exécutables** — Pour votre sécurité, Portunia refuse d'ouvrir en édition les types que Windows lancerait, comme `.exe`, `.bat`, `.js` ou `.lnk`.

<a id="tunnels"></a>

## 9\. Tunnels

Un tunnel fait passer une autre connexion à travers une session SSH. Il se règle depuis le bouton **Tunnels** de l'onglet, ou dans la session pour s'ouvrir à chaque connexion.

| Type | Équivalent | Exemple |
| --- | --- | --- |
| Port local | `ssh -L` | Le port 5432 de ce PC mène à une base de données derrière le serveur. |
| Proxy SOCKS | `ssh -D` | Votre navigateur passe par le serveur pour atteindre des sites internes. |
| Port distant | `ssh -R` | Le serveur atteint une application qui tourne sur votre PC. |

Les ports de votre PC n'écoutent que sur `127.0.0.1` : les autres machines du réseau ne peuvent pas les utiliser.

<a id="ecran"></a>

## 10\. Bureau à distance et VNC

| Bouton | Effet |
| --- | --- |
| Ctrl+Alt+Suppr | Envoie la combinaison à la machine distante. Tapée au clavier, elle resterait à votre propre Windows. |
| Presse-papiers | VNC : copie le presse-papiers de Windows vers l'écran distant. En Bureau à distance, le texte copié passe tout seul dans les deux sens. |
| Envoyer des fichiers 0.69 | Bureau à distance : choisissez des fichiers de ce PC (ou déposez-les sur l'écran), puis collez-les dans l'Explorateur du serveur avec Ctrl+V. Un message indique quand chaque fichier a été lu. |
| Récupérer les fichiers 0.69 | Apparaît quand des fichiers sont copiés (Ctrl+C) dans l'Explorateur du serveur : choisissez un dossier de ce PC, ils y sont enregistrés (un nom déjà pris devient « nom (2) »). |
| Ajuster à la fenêtre / Taille réelle | Adapte l'image à l'onglet, ou l'affiche à sa taille avec défilement. |

En Bureau à distance dans un onglet, le bureau distant s'adapte à la taille de l'onglet. Choisissez « Client Windows (mstsc) » pour le plein écran, tous vos écrans, ou si une fonction manque dans l'onglet.

Par une Gate, les boutons de fichiers n'apparaissent que si votre administrateur permet la copie de fichiers sur ce serveur (Gate 0.28 et suivantes) ; chaque fichier copié y est noté avec son nom, sa taille et son empreinte SHA-256. Le texte copié-collé reste possible dans tous les cas.

### Options du Bureau à distance (Portunia 0.65)

| Option | Onglet | Client Windows | Détail |
| --- | --- | --- | --- |
| Résolution | Oui | Oui | « Celle de l'onglet ou de la fenêtre » (par défaut) ou une taille fixe (1280 × 720 à 2560 × 1440) : l'image est alors mise à l'échelle. |
| Couleurs | Oui | Oui | 32, 24 ou 16 bits ; 16 bits allège une liaison lente. |
| Jouer le son du serveur ici | Oui | Oui | Activé par défaut. |
| Passerelle Bureau à distance | Oui | Oui | Serveurs joints par une passerelle RD (HTTPS, port 443 par défaut). Sans compte de passerelle, les identifiants du serveur servent aussi pour elle. Le client Windows demande lui-même le mot de passe de la passerelle. |
| Partager les lecteurs, les imprimantes | — | Oui | Les disques et imprimantes de ce poste apparaissent dans la session. |
| Session d'administration (console) | — | Oui | Comme `mstsc /admin`. |
| RemoteApp | — | Oui | La fenêtre d'un seul programme (chemin sur le serveur, ou `\|\|alias` publié) au lieu du bureau entier. Le serveur doit autoriser ce programme. |

En VNC, la résolution reste celle du serveur.

<a id="commandes"></a>

## 11\. Commandes, notes, identifiants

### Commandes enregistrées

Ctrl+Maj+P ouvre vos commandes. Une commande vaut pour une session, un dossier ou partout, et accepte des variables comme `{{host}}` et `{{username}}`.

### Notes

Chaque session a ses notes en Markdown : procédures, contacts, mots-clés. Les cases à cocher se cliquent et les blocs de code s'envoient au terminal.

### Identifiants partagés

Quand plusieurs sessions SSH, Bureau à distance ou VNC utilisent le même compte, créez un identifiant partagé et choisissez-le dans chacune. Le jour où le mot de passe change, vous ne le modifiez qu'une fois.

<a id="cles"></a>

## 12\. Clés SSH

Une clé remplace le mot de passe et résiste bien mieux aux attaques. Palette, puis « Clés SSH ».

1.  Ouvrez une session sur le serveur avec votre mot de passe.
2.  Cliquez sur le bouton **Clé SSH** de l'onglet : « Créer une clé SSH et l'installer sur ce serveur ».
3.  Gardez Ed25519 (recommandé) et choisissez une phrase secrète.
4.  Portunia installe la clé, corrige les droits et fait passer la session sur la clé.

> [!WARNING]
> **Partie publique seulement** — « Copier la clé publique » donne le texte à transmettre. Le fichier de clé privée, sans extension `.pub`, ne se partage jamais.

<a id="outils"></a>

## 13\. Outils réseau et supervision

| Outil | Usage |
| --- | --- |
| Ping, traceroute | La machine répond-elle, et par où passe la route ? Aucun droit d'administrateur n'est nécessaire. |
| Test de ports | Quels ports TCP sont ouverts : listes et plages acceptées, services reconnus. |
| DNS | Résoudre un nom. |
| Wake-on-LAN | Réveiller une machine. |

La **supervision** teste si vos serveurs répondent (toutes les 30 secondes, minutes ou 5 minutes). Une pastille verte ou rouge et la latence s'affichent dans l'arbre, avec une vue d'ensemble dans « Supervision des serveurs ». L'option « Me prévenir quand un serveur tombe ou revient » est réservée à Pro.

<a id="pro"></a>

## 14\. Fonctions Pro

| Fonction | Ce qu'elle apporte |
| --- | --- |
| Tableau de bord | Processeur, mémoire, disques, charge, processus actifs et services en échec d'un serveur Linux, relevés toutes les 5 secondes. « Voir » ouvre le journal d'un service. |
| Commande sur plusieurs serveurs | La même commande sur des sessions choisies ou un dossier, 8 serveurs à la fois. Résultats côte à côte, avec filtre des échecs. |
| Conteneurs | Docker, Podman et pods Kubernetes du serveur : shell, journaux, démarrer, arrêter, redémarrer. |
| Enregistrement | Le bouton **Enregistrer** de l'onglet garde la session terminal. Palette, puis « Enregistrements » pour la revoir, avec vitesse et navigation. |
| Proxmox VE | Les serveurs Proxmox dans leur propre section (voir ci-dessous). |

<a id="proxmox"></a>

### Proxmox VE (Portunia 0.66)

Installez l'extension **Proxmox VE** depuis le catalogue (Extensions › Catalogue, offre Pro ; Portunia 0.67.1) : une icône **Proxmox** apparaît dans la barre de gauche. **+** ajoute un serveur : son adresse (port 8006 par défaut), puis l'**empreinte du certificat** à comparer avec celle de Proxmox (nœud › Système › Certificats), l'utilisateur (`root@pam`, `admin@pve`…) et un **jeton d'API** (conseillé : Datacenter › Permissions › API Tokens, sans « Privilege Separation » pour garder les droits de l'utilisateur) ou un mot de passe. Le secret reste dans le Gestionnaire d'identifiants de Windows. Un compte à double authentification demande un jeton. Plusieurs serveurs ou clusters peuvent être ajoutés.

Un jeton créé avec « Privilege Separation » n'a **aucun droit** tant qu'on ne lui en donne pas, même pour `root@pam` : Proxmox montre alors le nœud mais aucune machine, et Portunia affiche « Aucun droit de voir les machines ». Donnez-lui une permission : Datacenter › Permissions › Ajouter › Permission de jeton d'API, chemin `/`, rôle `PVEVMAdmin` (ou `PVEAuditor` pour seulement regarder), puis **Actualiser**.

Sous chaque serveur, ses nœuds (charge du processeur) puis leurs machines virtuelles et conteneurs (point vert : en marche). L'état se met à jour toutes les 30 secondes ; le filtre des sessions s'applique aussi (numéro, nom, nœud, étiquette). Un clic ouvre la **console** d'une machine en marche dans un onglet ; le clic droit donne le reste.

| Où | Actions |
| --- | --- |
| Machine ou conteneur (clic droit) | Console ; démarrer, éteindre, redémarrer, mettre en pause et reprendre (machines virtuelles), arrêter (coupure, avec confirmation) ; **Instantanés** (prendre, avec la mémoire si la machine tourne, revenir, supprimer) ; **Sauvegardes** (sauvegarder maintenant sur un stockage, mode et compression ; lister, restaurer par-dessus, supprimer) ; **Cloner** (nouveau numéro proposé, nœud cible, copie complète ou liée depuis un modèle) ; **Migrer** vers un autre nœud, à chaud si elle tourne ; **Ressources et réglages** (cœurs, processeurs, mémoire, démarrage avec le nœud, notes, tous les réglages en lecture) ; Tâches ; convertir en modèle ; supprimer (en tapant son numéro). |
| Nœud (clic droit) | **Supervision** de ce nœud ; shell du nœud dans un onglet ; stockages ; tâches. |
| Serveur (menu « … ») | **Supervision** ; actualiser ; tâches du cluster ; stockages (place occupée, contenu : images ISO, modèles, disques, sauvegardes) ; modifier ; copier l'empreinte ; retirer de Portunia. |

<a id="proxmox-supervision"></a>

#### Supervision (Portunia 0.68)

Menu « … » du serveur (ou clic droit sur un nœud) › **Supervision** : un onglet relu toutes les 10 secondes tant qu'il est ouvert.

-   **Ensemble** : processeur et mémoire de tous les nœuds, stockage occupé (un stockage partagé compté une fois), machines en marche.
-   **Chaque nœud** : jauges (processeur, mémoire, disque système) et courbes sur l'heure, le jour, la semaine ou le mois (processeur et attente disque, mémoire et swap, réseau, charge moyenne). Survolez une courbe pour lire ses valeurs à un instant.
-   **Stockages** : type, contenus, place occupée (orange à 75 %, rouge à 90 %).
-   **Machines et conteneurs** : processeur, mémoire, disque, débits réseau et disque (mesurés entre deux relevés), durée de marche ; cliquez sur un titre de colonne pour trier, sur une ligne pour ses courbes.

Les courbes des nœuds demandent le droit `Sys.Audit` (rôle `PVEAuditor`, par exemple), celles des machines `VM.Audit`.

Chaque action lance une tâche Proxmox : Portunia la suit et annonce son résultat. Les consoles utilisent la console VNC de Proxmox, relayée par Portunia : l'extension **VNC** doit être activée. Les droits sont ceux de l'utilisateur ou du jeton dans Proxmox. Pour créer une machine, clonez un modèle.

<a id="verrou"></a>

## 15\. Verrouillage et données

Dans Paramètres › Sécurité, « Activer le verrouillage » crée un mot de passe maître d'au moins 8 caractères. Vos sessions, notes et empreintes sont alors chiffrées sur le disque. Portunia demande ce mot de passe au démarrage et après la durée d'inactivité choisie. Windows Hello (visage, empreinte, code PIN) peut le remplacer au quotidien.

Ctrl+Maj+L verrouille immédiatement. Les sessions ouvertes continuent de tourner en arrière-plan.

> [!CAUTION]
> **Mot de passe maître oublié** — Personne ne peut le récupérer. Sans Windows Hello, les données chiffrées sont perdues. Conservez une sauvegarde ([chapitre suivant](#sauvegarde)).

Après 5 essais manqués, Portunia impose une attente croissante, de 5 secondes à 5 minutes. Pendant l'attente, même le bon mot de passe est refusé.

<a id="sauvegarde"></a>

## 16\. Importer et sauvegarder

Palette, puis « Importer / exporter ».

| Source | Ce qui est repris |
| --- | --- |
| `~/.ssh/config` | Hôtes, utilisateurs, ports, clés, rebonds et tunnels. |
| PuTTY | Sessions du registre Windows. |
| mRemoteNG | Fichier XML exporté. |
| Sauvegarde Portunia | Une sauvegarde créée avec « Exporter… ». |

Un aperçu liste ce qui sera importé et signale les sessions déjà présentes. Pour une sauvegarde, choisissez une phrase de passe d'au moins 8 caractères : sans elle, le fichier reste en clair.

> [!NOTE]
> **Mots de passe** — Un import ou une sauvegarde ne contient jamais de mot de passe. Après une restauration sur un autre PC, il faudra les saisir à nouveau.

<a id="reglages"></a>

## 17\. Paramètres et licence

| Rubrique | Ce qu'on y règle |
| --- | --- |
| Apparence | Langue (appliquée au prochain démarrage), thème clair, sombre ou comme Windows, couleurs du terminal, police, taille, curseur (barre, bloc, souligné). |
| Terminal | Clic droit, copie automatique de la sélection, confirmation du collage, mise en évidence, rendu. |
| Connexion | Reconnexion automatique après une coupure réseau ou une mise en veille. |
| Shells locaux | Shell par défaut, shells personnalisés, ouverture au démarrage. |
| Sécurité | Mot de passe maître, Windows Hello, verrouillage après inactivité. |
| Supervision | Activation, fréquence, alertes. |
| Mises à jour | Vérification au démarrage, « Rechercher maintenant ». |
| Licence | Collez ici le texte reçu par e-mail. La vérification se fait sans connexion à Internet. |

Une licence expirée garde ses fonctions : seules les versions publiées après l'expiration ne sont plus incluses.

<a id="Gate"></a>

## 18\. Se connecter par une Gate

Votre administrateur vous donne l'**adresse de la Gate**, votre **identifiant**, un **mot de passe provisoire** et l'**empreinte du certificat**. Installez sur votre téléphone une application d'authentification, comme Microsoft Authenticator ou Google Authenticator.

### Premier accès

1.  Dans le panneau **Gates** (icône du bouclier dans le rail), cliquez sur « Ajouter une Gate ». Si elle n'apparaît pas, activez l'extension Portunia Gate dans Extensions.
2.  Saisissez l'adresse, par exemple `gate.exemple.fr`.
3.  **Comparez l'empreinte affichée à celle reçue de votre administrateur.** Si elles diffèrent, arrêtez et prévenez-le.
4.  Saisissez votre identifiant et votre mot de passe provisoire.
5.  Choisissez votre nouveau mot de passe.
6.  Scannez le QR code avec votre application, puis tapez les 6 chiffres affichés.

Vos serveurs apparaissent par dossiers sous le nom de la Gate. Vous ne voyez que ceux qui vous sont autorisés, et seulement aux jours et heures prévus.

### Au quotidien

-   Cliquez sur un serveur : il s'ouvre dans un onglet sans redemander de code. Portunia obtient pour vous une autorisation à usage unique.
-   La ligne de la Gate affiche votre identifiant et le temps restant. Par défaut, une connexion à la Gate dure 8 heures.
-   Une fois la durée écoulée, la Gate indique « session expirée ». Cliquez dessus pour vous reconnecter. Les serveurs restent affichés en gris en attendant.
-   Si l'administrateur l'autorise, cochez « Mémoriser mon mot de passe sur ce PC ». Le code sera toujours demandé.
-   Le bouton « Plus d'actions » de la Gate propose aussi « Mes sessions » (si la Gate permet de relire les vôtres), « Se déconnecter » et « Retirer cette Gate ».

### Sessions qui contournent la Gate

Portunia peut signaler que certaines de vos sessions personnelles visent directement des serveurs protégés par la Gate. Ces connexions échappent aux contrôles et à l'enregistrement. Supprimez-les ou gardez-les selon la politique de votre entreprise, et ouvrez désormais ces serveurs depuis la section Gates.

### Serveurs Windows

Ils portent un badge RDP et demandent l'extension Bureau à distance. Vos identifiants Windows sont demandés à chaque ouverture, sauf pour les serveurs en mode **coffre** (Gate 0.29) : la Gate ouvre alors la session Windows elle-même, sans que vous voyiez le mot de passe. Dans le portail web, les serveurs Windows en mode rebond s'ouvrent aussi : la Gate les relaie, sans les enregistrer.

### Interfaces web

Les consoles d'administration (vCenter, iDRAC, pare-feu…) portent un badge WEB (Gate 0.30, Portunia 0.67, extension Interface web). Un clic ouvre l'application dans une fenêtre dédiée, par la Gate ; vous y tapez vos identifiants comme d'habitude. La Gate note les pages que vous ouvrez. Dans le portail web, elle s'ouvre dans un nouvel onglet ; une seule interface web à la fois par navigateur.

> [!WARNING]
> **Téléphone perdu ou changé** — Sans le téléphone, vous ne pouvez plus générer de code. Demandez à votre administrateur de réinitialiser votre code ; vous referez l'étape du QR code à la prochaine connexion.

<a id="modes"></a>

## 19\. Rebond, enregistré, coffre

Chaque serveur a un mode, choisi par l'administrateur et indiqué dans la liste. Il décide de ce que vous devez taper et de ce qui est conservé.

| Mode | Vous tapez | Enregistré ? |
| --- | --- | --- |
| **Coffre** | Rien : la Gate fournit le compte du serveur, que vous ne voyez jamais. | Oui. |
| **Enregistré** | Vos identifiants du serveur, dans le terminal ou la fenêtre Windows. | Oui. |
| **Rebond** | Vos identifiants du serveur. La Gate relaie de bout en bout. | Non. |

> [!NOTE]
> **Ce qui est conservé** — En modes coffre et enregistré, ce qui s'affiche est enregistré et peut être relu par les auditeurs. La frappe peut l'être aussi selon la règle, avec les saisies masquées protégées. Respectez la charte de votre entreprise, comme sur tout poste professionnel.

<a id="portail"></a>

## 20\. Le portail web

Si votre entreprise l'a activé, le portail ouvre vos serveurs depuis un navigateur, sans Portunia. Il faut être dans le groupe autorisé et avoir fait la première connexion : **première connexion et code perdu ne se traitent pas sur le portail.**

1.  Allez à l'adresse donnée par votre administrateur et patientez pendant la vérification anti-robots.
2.  Remplissez identifiant, mot de passe et code, puis « Se connecter ».
3.  Dans **Mes serveurs**, cherchez un serveur et ouvrez-le dans un onglet.

| Situation | Fonctionnement |
| --- | --- |
| Serveur SSH | Un terminal avec les boutons Copier et Coller. En mode enregistré, vos identifiants sont demandés dans le terminal. |
| Serveur Windows | Identifiants Windows demandés, puis boutons Ctrl+Alt+Suppr et Plein écran. Ils sont envoyés au serveur par une connexion chiffrée : la Gate ne voit pas votre mot de passe. |
| Fichiers avec un serveur Windows | Si votre administrateur l'autorise : **Envoyer des fichiers** (ou déposez-les sur le bureau), puis collez-les dans Windows avec Ctrl+V. Pour en récupérer, copiez-les dans Windows (Ctrl+C) : ils apparaissent dans le panneau Fichiers, avec un bouton Télécharger. Chaque fichier copié est noté par la Gate. Sans autorisation, la copie de fichiers est bloquée, le copier-coller de texte reste possible. |
| Serveur en mode rebond | Pas disponible sur le portail : utilisez Portunia. |
| Inactivité | « Toujours là ? » s'affiche avant la fermeture : cliquez sur Continuer. |

> [!WARNING]
> **Poste partagé** — Cliquez sur « Se déconnecter » en partant et ne laissez aucun onglet ouvert.

<a id="sans-portunia"></a>

## 21\. Sans Portunia

La Gate accepte les clients SSH habituels, comme OpenSSH, PuTTY ou WinSCP. Votre code doit avoir été enrôlé avant. Remplacez `julien`, `web-01`, `Gate` et le port si votre administrateur en indique un autre.

```
ssh -p 2222 julien@gate               # menu des serveurs autorisés
ssh -p 2222 julien%web-01@gate        # directement sur web-01
ssh -J julien@gate:2222 admin@fw-01   # serveur en mode rebond
sftp -P 2222 julien%web-01@gate       # fichiers (coffre, si la règle l'autorise)
```

<a id="depanner"></a>

## 22\. Dépanner quelqu'un

Il vous faut Portunia, les extensions Portunia Gate et Assistance à distance activées, une connexion à une Gate dont le relais est actif, et un compte dans son groupe de dépanneurs.

1.  Appelez la personne au téléphone.
2.  Cliquez sur **Assistance à distance** (icône de la bouée dans le rail). La fenêtre affiche la phrase à dire, avec l'adresse de la page à ouvrir.
3.  Quand la personne vous lit ses 9 chiffres, tapez-les puis « Se connecter ».
4.  La personne voit votre nom et accepte. Son écran s'ouvre dans un onglet.

Elle décide si vous voyez seulement l'écran ou si vous pouvez aussi utiliser la souris et le clavier. Elle peut tout arrêter à tout moment. La liaison est chiffrée de bout en bout à partir du code.

| Message | Que faire |
| --- | --- |
| « Connectez-vous d'abord à une Gate » | Reconnectez-vous dans la section Gates. |
| « Le relais d'assistance est coupé » | Demandez à un administrateur de l'activer dans Administrer › Assistance. |
| « Votre compte n'est pas dans le groupe des dépanneurs » | Demandez à être ajouté au groupe, ou vérifiez que la Gate est en Portunia Gate 0.11 ou suivant. |
| « La Gate n'a pas encore téléchargé Portunia Assistance » | La Gate a besoin d'Internet pour le récupérer : prévenez l'administrateur. |

<a id="aide"></a>

## 23\. Être dépanné

Une personne de confiance va vous aider sur votre ordinateur, sous Windows 10 ou 11. Rien ne s'installe, et personne ne voit votre écran sans votre accord.

1.  Allez sur la page que la personne vous indique et cliquez sur **Télécharger Portunia Assistance**.
2.  Ouvrez le fichier téléchargé. Si Windows affiche un avertissement bleu, cliquez sur « Informations complémentaires » puis « Exécuter quand même ».
3.  Un code à 9 chiffres s'affiche. Lisez-le à la personne qui vous aide.
4.  Son nom apparaît. Vérifiez que c'est bien elle, puis acceptez.
5.  Cochez « Lui laisser utiliser la souris et le clavier » si elle doit agir pour vous. Sinon, elle voit seulement l'écran.

Pendant l'assistance, un cadre entoure votre écran et un bandeau indique qui le voit. **Pour arrêter, cliquez sur « Arrêter » ou appuyez trois fois sur Échap.** Fermé, le programme ne laisse aucun accès.

> [!CAUTION]
> **Méfiez-vous des appels inattendus** — Ne lisez ce code qu'à une personne que vous connaissez ou que vous avez vous-même appelée. Personne de sérieux ne vous appellera à l'improviste pour vous le demander. Si vous avez un doute, raccrochez.

<a id="raccourcis"></a>

## 24\. Raccourcis clavier

| Raccourci | Action |
| --- | --- |
| Ctrl+Maj+O | Palette : sessions, shells, actions |
| Ctrl+Maj+K | Rechercher une session |
| Ctrl+Maj+N | Nouvelle session |
| Ctrl+Maj+Q | Connexion rapide |
| Ctrl+Maj+T | Ouvrir le shell local par défaut |
| Ctrl+Maj+W | Fermer l'onglet actif |
| Ctrl+Maj+F | Rechercher dans le terminal |
| Ctrl+Maj+B | Saisie multiple |
| Ctrl+Maj+P | Commandes enregistrées |
| Ctrl+Maj+L | Verrouiller Portunia |
| Ctrl + molette | Taille du texte du terminal |
| Ctrl + clic | Ouvrir un lien du terminal |
| F2 / Suppr | Renommer ou supprimer dans le panneau Fichiers |

<a id="connexion-rapide"></a>

## 25\. Formes de connexion rapide

Elles fonctionnent dans la recherche, la palette et la fenêtre Connexion rapide.

| Vous tapez | Portunia ouvre |
| --- | --- |
| `10.0.0.12` | Une connexion à cette adresse |
| `ssh deploy@10.0.1.12` | SSH avec cet utilisateur |
| `rdp srv-01` | Bureau à distance |
| `vnc nas:5901` | VNC sur le port 5901 |
| `https://nas:5001` | Interface web |
| `COM3@9600` | Port série à 9600 bauds |
| `ftps://user@hôte` | FTPS |

<a id="problemes"></a>

## 26\. En cas de problème

| Symptôme | Cause probable | Que faire |
| --- | --- | --- |
| « ATTENTION : la clé du serveur a changé » | Le serveur a été réinstallé, ou quelqu'un se fait passer pour lui. | Ne continuez pas. Vérifiez auprès du responsable du serveur. |
| Connexion impossible à un vieil équipement | Algorithmes trop anciens. | Cochez « Compatibilité anciens équipements » dans cette session. |
| « Pas de réponse du serveur RDP » | Machine éteinte, Bureau à distance inactif, pare-feu. | Testez le port 3389 dans Outils réseau. |
| « Moteur RDP introuvable » | Installation incomplète, parfois à cause d'un antivirus. | Réinstallez Portunia ou choisissez l'affichage « Client Windows ». |
| Un serveur est introuvable dans la liste de la Gate | Aucune règle ne vous l'autorise, ou pas à cette heure. | Contactez votre administrateur. |
| Code refusé | Heure du téléphone décalée, ou code déjà utilisé. | Réglez l'heure sur automatique et attendez le code suivant. Après 5 échecs en 10 minutes, il faut patienter. |
| « session expirée » sur la Gate | Durée de connexion écoulée. | Cliquez sur la Gate et reconnectez-vous. |
| Portail : « Autorisation expirée » | L'onglet a attendu trop longtemps. | Rouvrez le serveur depuis la liste. |
| Portail : « Accès refusé par la Gate » | Règle ou serveur non autorisé. | Contactez votre administrateur. |
| Portail : « Portail fermé » | Portail désactivé. | Utilisez Portunia ou contactez votre administrateur. |
| Portail : « Identifiant ou mot de passe Windows refusé » | Identifiants Windows incorrects. | Vérifiez-les et indiquez le domaine si besoin. |
| Portunia Assistance : « ne sait pas quel serveur utiliser » | Le fichier a été renommé. | Téléchargez-le à nouveau depuis la page indiquée. |
| Terminal lent ou affichage cassé | Pilote graphique, session Bureau à distance. | Paramètres › Rendu des terminaux : « Jamais (rendu classique) ». |

<a id="faq"></a>

## 27\. Questions fréquentes

| Question | Réponse |
| --- | --- |
| Où sont mes mots de passe ? | Dans le Gestionnaire d'identifiants de Windows, pas dans les fichiers de Portunia. |
| Portunia envoie-t-il mes données quelque part ? | Vos sessions restent sur votre PC. La vérification des mises à jour interroge le site de publication. |
| Fermer l'onglet coupe-t-il la connexion ? | Oui, et les tunnels de cette session s'arrêtent avec elle. |
| Puis-je changer de PC ? | Oui : exportez une sauvegarde, restaurez-la, puis saisissez à nouveau vos mots de passe. Copiez aussi vos clés SSH de façon sûre. |
| L'administrateur voit-il mes mots de passe de la Gate ? | Non. Il peut vous attribuer un nouveau mot de passe provisoire, mais pas lire le vôtre. |
