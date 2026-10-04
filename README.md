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
# Étape 2 : Ajouter MinGW aux variables d'environnement (PATH)
Pour pouvoir utiliser la commande gcc depuis n'importe quel terminal Windows (Invite de commandes ou PowerShell), il faut déclarer le chemin du compilateur.
1. Dans la barre de recherche Windows, tapez "Variables d'environnement" et cliquez sur Modifier les variables d'environnement système.
2. Dans la fenêtre qui s'ouvre, cliquez sur le bouton Variables d'environnement... en bas à droite.
3. Dans la section Variables système (en bas), cherchez la ligne nommée Path et double-cliquez dessus.
4. Cliquez sur le bouton Nouveau à droite, puis collez le chemin d'accès exact vers le dossier bin du compilateur installé. Par défaut avec MSYS2, c'est :

   C:\msys64\ucrt64\bin

5. Cliquez sur OK sur toutes les fenêtres ouvertes pour enregistrer les modifications.
# Étape 3 : Vérifier l'installation
1. Ouvrez une nouvelle Invite de commandes (cmd) ou un nouveau PowerShell (indispensable pour charger le nouveau Path).
2. Tapez la commande suivante :

   gcc --version

3. Si tout est correct, le terminal affichera la version de GCC (ex: gcc (Rev...) 13.x.x). Si vous avez un message d'erreur indiquant que la commande n'est pas reconnue, redémarrez votre PC.
# Étape 4 : Écrire le code source
1. Ouvrez un éditeur de texte simple (le Bloc-notes, Notepad++, ou Visual Studio Code).
2. Copiez-collez ce code de test minimal :

----------------------------------------------
#include <stdio.h>

int main() {
    printf("Bravo, MinGW fonctionne parfaitement !\n");
    return 0;
}

----------------------------------------------
3. Enregistrez le fichier sous le nom de main.c dans un dossier facile d'accès (par exemple : C:\Projets). Attention à ce que le fichier ne s'appelle pas main.c.txt.
