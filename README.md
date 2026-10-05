================================================================
  LE REPAIRE V5 — Scanner Stalker Portal + Rotation 5G
  Version PC Windows standalone (aucune dépendance requise)
================================================================

CONTENU DU DOSSIER
------------------
  LE_REPAIRE_V5.exe   → l'application (standalone, ~15 Mo)
  INSTALLER.bat       → crée un raccourci sur le bureau
  README.txt          → ce fichier

INSTALLATION
------------
  Option 1 (recommandée) :
    Double-clic sur INSTALLER.bat
    → Crée l'icône "LE REPAIRE V5" sur ton bureau

  Option 2 (lancement direct) :
    Double-clic sur LE_REPAIRE_V5.exe

LANCEMENT
---------
  1. Double-clic sur l'icône (bureau ou .exe)
  2. Une fenêtre console noire s'ouvre (le serveur)
  3. Ton navigateur par défaut s'ouvre AUTOMATIQUEMENT
     sur http://127.0.0.1:5556
  4. Sinon : va manuellement sur http://127.0.0.1:5556

ARRÊT
-----
  Ferme la fenêtre console noire → le serveur s'arrête.

ONGLETS DISPONIBLES
-------------------
  MAC Scan      → Scan de portails Stalker (handshake, profiles, flux)
  MACs Gen      → Générateur de MACs (range + random)
  M3U Check     → Vérification de liens M3U (player_api, enigma2, etc.)
  Rotation 5G   → Rotation d'IP mobile via ADB (téléphone USB)
  Debug         → État runtime, routes, logs serveur, scanners actifs

TEST HOST
---------
  Bouton >_ TEST HOST sous le champ HOST (dans MAC Scan).
  Teste à quels endpoints répond un serveur Stalker:
    /, /c/, /stalker_portal/c/, /portal.php, /c/portal.php,
    /stalker_portal/server/load.php, /portalott.php,
    /player_api.php, /panel_api.php, /enigma2.php
  Affiche IP, pays, ville, ASN, version middleware +
  le code HTTP de chaque endpoint, avec indicateur <PORTAL>
  si Stalker détecté.

KEYCHECK STATUS
---------------
  Dropdown dans la section Modes :
    1 - OFF (défaut) : Laisse passer toutes les MACs
    2 - Strict       : Invalide la MAC si aucun get_profile
                       n'a retourné un stb_type MAG réel
                       (MAG200/250/254/256/270/322/349/424)

ROTATION 5G (NOUVEL ONGLET)
---------------------------
  Change l'IP mobile d'un téléphone Android branché en USB (ADB).

  Prérequis :
    - Android avec débogage USB activé
    - Autoriser cet ordinateur à utiliser ADB (popup à l'écran)
    - Si "ADB non trouvé" : installer Android SDK platform-tools
      ou le tool "Rotation 5G" (déjà détecté automatiquement)

  Comment ça marche :
    - "Mode avion" : cmd connectivity airplane-mode enable/disable
    - "Données mobiles" : svc data disable/enable
    - WiFi coupé en option (force tout le trafic en 5G)

  Config :
    - Appareil ADB : détection auto (bouton ↻ Scanner)
    - Mode de rotation : avion (fiable) ou data mobile
    - Intervalle : secondes entre deux rotations
    - Rotations : 0 = infini, N = s'arrête après N rotations

  Affiche IP mobile avant/après chaque rotation.

DEBUG (ONGLET REFAIT)
---------------------
  État temps réel du serveur :
    - Uptime, PID, Python, OS, hostname, IP locale
    - Compteurs : requêtes totales, API, pages
    - État : MAC Scanner, M3U Checker, Rotation 5G
    - Table complète des routes Flask actives
    - Logs runtime

HITS SAUVÉS
-----------
  Dans un sous-dossier "hits/" à côté de l'exe
  (ou dans %USERPROFILE% suivant la plateforme).

PORT
----
  Le serveur écoute sur le port 5556.
  Pour changer : édite le code source (le .py), pas le .exe.

ANTIVIRUS / SMARTSCREEN
-----------------------
  Windows peut afficher "SmartScreen a empêché le démarrage" :
    → "Informations complémentaires" puis "Exécuter quand même"
  C'est normal pour un .exe non signé.

================================================================
