# Les Commandes Linux de Base
### **Cours complet sur les commandes de base Linux**

Ce cours vise à vous initier aux commandes de base utilisées dans un système d'exploitation Linux. Ces commandes permettent de naviguer dans le système de fichiers, de manipuler des fichiers et dossiers, de gérer des processus et d'effectuer des tâches d'administration simples.

---

## **1. Introduction à Linux**
Linux est un système d'exploitation libre basé sur Unix. Il est utilisé dans les serveurs, les postes de travail et les systèmes embarqués. Les commandes Linux permettent une interaction puissante avec le système à partir du **terminal**.

---

## **2. Navigation dans le système de fichiers**

### **2.1 Commandes de navigation**
- **`pwd`** : Affiche le chemin du répertoire courant.
  ```bash
  pwd
  ```
  *Exemple de sortie :* `/home/utilisateur`

- **`ls`** : Liste les fichiers et répertoires.
  ```bash
  ls
  ```
  Options utiles :
  - `-l` : Affiche en format détaillé.
  - `-a` : Inclut les fichiers cachés.
  - `-h` : Affiche les tailles dans un format lisible (avec `-l`).

- **`cd`** : Change de répertoire.
  ```bash
  cd /chemin/vers/repertoire
  cd ..  # Revenir au répertoire parent
  cd ~   # Aller dans le répertoire personnel (home)
  ```

---

### **2.2 Commandes de gestion des fichiers et répertoires**
- **`touch`** : Crée un fichier vide.
  ```bash
  touch fichier.txt
  ```

- **`mkdir`** : Crée un répertoire.
  ```bash
  mkdir mon_dossier
  ```

- **`cp`** : Copie des fichiers ou répertoires.
  ```bash
  cp fichier.txt copie_fichier.txt  # Copier un fichier
  cp -r dossier/ copie_dossier/    # Copier un répertoire
  ```

- **`mv`** : Déplace ou renomme des fichiers.
  ```bash
  mv fichier.txt nouveau_nom.txt   # Renommer
  mv fichier.txt /chemin/dossier   # Déplacer
  ```

- **`rm`** : Supprime des fichiers ou répertoires.
  ```bash
  rm fichier.txt           # Supprimer un fichier
  rm -r dossier/           # Supprimer un répertoire
  rm -rf dossier/          # Supprimer de manière forcée (attention)
  ```

---

## **3. Gestion des fichiers**
### **3.1 Afficher le contenu d’un fichier**
- **`cat`** : Affiche le contenu d’un fichier.
  ```bash
  cat fichier.txt
  ```

- **`less`** : Affiche le contenu en permettant de défiler.
  ```bash
  less fichier.txt
  ```

- **`head`** et **`tail`** : Affiche les premières ou dernières lignes.
  ```bash
  head -n 10 fichier.txt  # Premières 10 lignes
  tail -n 10 fichier.txt  # Dernières 10 lignes
  tail -f fichier.log     # Suivre un fichier en temps réel
  ```

---

## **4. Gestion des permissions**
### **4.1 Visualiser les permissions**
- **`ls -l`** : Affiche les permissions des fichiers et répertoires.
  ```bash
  ls -l
  ```
  *Exemple de sortie :*
  ```
  -rw-r--r-- 1 utilisateur groupe 1024 Oct 4 fichier.txt
  ```

### **4.2 Modifier les permissions**
- **`chmod`** : Change les permissions d’un fichier.
  ```bash
  chmod 755 script.sh  # Lecture, écriture, exécution pour l'utilisateur, lecture/exécution pour les autres
  chmod +x fichier     # Ajouter l'exécution
  chmod -r fichier     # Enlever la lecture
  ```

---

## **5. Recherche de fichiers**
- **`find`** : Rechercher des fichiers.
  ```bash
  find /chemin -name "fichier.txt"   # Rechercher par nom
  find /chemin -type d -name "dossier"  # Rechercher un répertoire
  ```

- **`grep`** : Rechercher une chaîne dans un fichier.
  ```bash
  grep "mot" fichier.txt
  grep -r "mot" /dossier           # Rechercher récursivement
  ```

---

## **6. Gestion des processus**
### **6.1 Commandes de base**
- **`ps`** : Liste les processus en cours.
  ```bash
  ps
  ps aux  # Liste complète
  ```

- **`top`** : Affiche les processus actifs en temps réel.
  ```bash
  top
  ```

- **`kill`** : Terminer un processus.
  ```bash
  kill PID  # Remplacer PID par l'identifiant du processus
  kill -9 PID  # Forcer l'arrêt
  ```

### **6.2 Historique des commandes**
- **`history`** : Affiche les commandes précédentes.
  ```bash
  history
  ```

---

## **7. Compression et archivage**
- **`tar`** : Crée ou extrait des archives.
  ```bash
  tar -cvf archive.tar dossier/  # Créer une archive
  tar -xvf archive.tar           # Extraire une archive
  tar -czvf archive.tar.gz dossier/  # Créer une archive compressée
  tar -xzvf archive.tar.gz           # Extraire une archive compressée
  ```

- **`zip` et `unzip`** : Compresser et décompresser.
  ```bash
  zip -r archive.zip dossier/  # Compresser
  unzip archive.zip            # Décompresser
  ```

---

## **8. Réseau**
### **8.1 Vérification de la connectivité**
- **`ping`** : Vérifie la connectivité avec un hôte.
  ```bash
  ping google.com
  ```

- **`curl`** : Effectue des requêtes HTTP.
  ```bash
  curl http://example.com
  ```

- **`wget`** : Télécharge des fichiers depuis une URL.
  ```bash
  wget http://example.com/fichier.zip
  ```

---

## **9. Redirections et pipes**
### **9.1 Redirection de sortie**
- **Rediriger la sortie standard vers un fichier :**
  ```bash
  echo "Bonjour" > fichier.txt  # Écrase le contenu
  echo "Comment ça va ?" >> fichier.txt  # Ajoute au contenu
  ```

- **Rediriger les erreurs :**
  ```bash
  commande 2> erreur.log
  ```

### **9.2 Utilisation des pipes**
- **`|`** : Enchaîne plusieurs commandes.
  ```bash
  ls | grep "txt"  # Cherche les fichiers contenant 'txt'
  ```

---

## **10. Commandes système**
- **`df`** : Affiche l’espace disque disponible.
  ```bash
  df -h
  ```

- **`du`** : Affiche l’utilisation de l’espace disque.
  ```bash
  du -sh dossier/
  ```

- **`free`** : Affiche la mémoire disponible.
  ```bash
  free -h
  ```

- **`uptime`** : Affiche depuis combien de temps le système est actif.
  ```bash
  uptime
  ```

---

## **11. Exercices pratiques**
1. **Création et manipulation de fichiers :**
   - Créez un fichier, ajoutez-y du texte, puis copiez-le dans un autre dossier.

2. **Recherche et gestion des processus :**
   - Listez les processus actifs, trouvez un processus spécifique et terminez-le.

3. **Compression et archivage :**
   - Compressez un dossier, puis extrayez-le.

4. **Analyse système :**
   - Vérifiez l’espace disque utilisé sur votre machine.

---

En maîtrisant ces commandes de base, vous serez capable de travailler efficacement dans un environnement Linux. Ce cours constitue une base solide pour explorer des concepts plus avancés comme le scripting shell et l’administration système.
