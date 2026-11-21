# Petit Slime

Petit jeu de survie en 3D dans le navigateur, construit avec Three.js. Le serveur local est écrit avec Node.js ; aucune compilation n’est nécessaire.

## Prérequis

Il faut installer :

- **Git**, pour télécharger le projet.
- **Node.js LTS** et npm, installés avec Node.js. Node.js 20 ou plus récent est recommandé.
- Un navigateur récent compatible avec WebGL, par exemple Firefox, Chrome ou Edge.

Téléchargements officiels : [Git](https://git-scm.com/downloads) et [Node.js](https://nodejs.org/).

Vérifier l’installation dans un terminal :

```sh
git --version
node --version
npm --version
```

## Installation et lancement

Dans un terminal, télécharge le dépôt et installe ses dépendances :

```sh
git clone https://github.com/Binixe/Jeu.git
cd Jeu
npm install
```

Démarre ensuite le serveur :

```sh
npm start
```

Le terminal indique l’adresse du serveur. Par défaut, ouvre **http://localhost:3000/** dans ton navigateur. Laisse le terminal ouvert pendant que tu joues. Pour arrêter le serveur, reviens au terminal et appuie sur `Ctrl+C`.

Si le port 3000 est déjà utilisé, lance le serveur sur le port 3001 :

```sh
PORT=3001 npm start
```

Sous PowerShell, utilise plutôt :

```powershell
$env:PORT=3001
npm start
```

Puis ouvre http://localhost:3001/.

## Windows avec WSL et Debian

Cette procédure installe Debian dans WSL sur Windows. Ouvre **PowerShell en tant qu’administrateur**, puis installe WSL et Debian :

```powershell
wsl --install -d Debian
```

Redémarre Windows si demandé, puis lance **Debian** depuis le menu Démarrer. Au premier lancement, crée le nom d’utilisateur et le mot de passe Linux demandés.

Dans le terminal Debian, installe Git et les outils nécessaires à Node.js :

```sh
sudo apt update
sudo apt install -y git curl ca-certificates
```

Installe Node.js LTS avec nvm :

```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash
source ~/.bashrc
nvm install --lts
nvm use --lts
```

Vérifie que `node` et `npm` répondent, puis télécharge et lance le jeu depuis le système de fichiers Linux :

```sh
node --version
npm --version
mkdir -p ~/projets
cd ~/projets
git clone https://github.com/Binixe/Jeu.git
cd Jeu
npm install
npm start
```

Pendant que le serveur tourne dans Debian, ouvre **http://localhost:3000/** dans le navigateur Windows. WSL 2 transmet normalement ce port automatiquement. Garde le projet dans `~/projets` plutôt que dans `/mnt/c` pour de meilleures performances. Pour arrêter le serveur, utilise `Ctrl+C` dans Debian.

## Contrôles

- `W`, `A`, `S`, `D` ou les flèches : déplacer le slime.
- Glisser la souris : orienter la caméra en vue FPS ou TPS.
- `1`, `2`, `3`, `4` : choisir FPS, TPS, isométrique ou défilement latéral.
- `E` près d’une porte : entrer dans une maison ; près d’un meuble : le fouiller.
- `Q` : sortir d’une maison.
- `Espace` : attaquer un slime zombie à portée.
- Le bouton **Inventaire** ouvre le sac. Les soins s’utilisent depuis ce panneau ; un couteau peut y être équipé.
- `R` : recommencer après une défaite.