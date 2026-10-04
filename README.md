# Compile C with MINGW
FFF
# Étape 1 : Installer MinGW-w64 via MSYS2
La méthode moderne et la plus stable pour installer MinGW sous Windows consiste à utiliser le gestionnaire de paquets MSYS2.
1. Rendez-vous sur le site officiel de MSYS2 et téléchargez l'installateur (fichier .exe).
2. Lancez l'installateur et suivez les instructions en laissant le dossier d'installation par défaut (C:\msys64).
3. À la fin de l'installation, cochez la case pour ouvrir le terminal MSYS2 UCRT64 (ou cherchez "MSYS2 UCRT64" dans votre menu Démarrer).
4. Dans le terminal qui s'ouvre, tapez la commande suivante pour installer le compilateur GCC et les outils de développement indispensables :

   pacman -S --needed base-devel mingw-w64-ucrt-x86_64-toolchain

5. Appuyez sur Entrée pour confirmer les choix par défaut, puis tapez Y (Yes) pour lancer le téléchargement et l'installation.
