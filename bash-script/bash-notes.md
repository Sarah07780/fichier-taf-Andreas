# Notes de cours Bash Scripting

### Introduction au scripting Bash (Shell Scripting)

Le scripting **Bash** (ou scripting shell) désigne la création de scripts pour automatiser des tâches dans un système basé sur Unix/Linux. Un **script shell** est un fichier texte contenant une série de commandes qui sont exécutées séquentiellement par un interpréteur de commande (bash, sh, zsh, etc.).

---

## **1. Présentation du Shell**
### **Qu’est-ce qu’un shell ?**
- Le shell est une interface entre l'utilisateur et le noyau du système d'exploitation.
- Il interprète les commandes tapées par l'utilisateur et les exécute.

### **Types de shells**
- **Bash (Bourne Again Shell)** : le plus courant sur Linux.
- **Zsh**, **Sh**, **Ksh**, **Fish** : autres variantes.

### **Pourquoi apprendre le scripting shell ?**
- Automatisation des tâches répétitives.
- Gestion de fichiers (création, suppression, copie).
- Surveillance et administration de systèmes.
- Création d'outils simples pour interagir avec le système.

---

## **2. Pré-requis**
Avant de commencer, vous devez savoir :
- Naviguer dans le terminal (commandes : `cd`, `ls`, `pwd`, `mkdir`).
- Manipuler des fichiers (commandes : `touch`, `cp`, `mv`, `rm`).
- Comprendre les permissions des fichiers (`chmod`, `chown`).

---

## **3. Structure d’un script shell**
### **Créer un script simple**
1. **Création du fichier :**
   ```bash
   touch script.sh
   ```
2. **Rendre le script exécutable :**
   ```bash
   chmod +x script.sh
   ```
3. **Contenu de base d’un script :**
   ```bash
   #!/bin/bash
   # Ceci est un commentaire
   echo "Bonjour, Monde !" # Affiche un message
   ```
4. **Exécution du script :**
   ```bash
   ./script.sh
   ```

### **Détails :**
- `#!/bin/bash` : spécifie l’interpréteur utilisé pour exécuter le script.
- `echo` : commande pour afficher du texte.

---

## **4. Variables dans le shell**
### **Définir une variable**
```bash
#!/bin/bash
nom="Bertrand"
echo "Bonjour, $nom !"
```

### **Opérations sur les variables**
- **Lire une entrée utilisateur :**
  ```bash
  echo "Quel est votre nom ?"
  read utilisateur
  echo "Bonjour, $utilisateur !"
  ```
- **Manipulation des nombres :**
  ```bash
  a=5
  b=3
  somme=$((a + b))
  echo "La somme de $a et $b est $somme"
  ```

---

## **5. Conditions**
### **Syntaxe de base**
```bash
if [ condition ]; then
    # Code si la condition est vraie
else
    # Code si la condition est fausse
fi
```

### **Exemple :**
```bash
#!/bin/bash
echo "Entrez un nombre :"
read nombre
if [ $nombre -gt 10 ]; then
    echo "Le nombre est supérieur à 10"
else
    echo "Le nombre est inférieur ou égal à 10"
fi
```

### **Opérateurs de comparaison**
- Nombres :
  - `-eq` : égal à.
  - `-ne` : différent de.
  - `-lt` : inférieur à.
  - `-le` : inférieur ou égal à.
  - `-gt` : supérieur à.
  - `-ge` : supérieur ou égal à.
- Fichiers :
  - `-e` : existe.
  - `-f` : est un fichier régulier.
  - `-d` : est un répertoire.

---

## **6. Boucles**
### **Boucle `for`**
```bash
for i in 1 2 3 4 5; do
    echo "Compteur : $i"
done
```

### **Boucle `while`**
```bash
compteur=1
while [ $compteur -le 5 ]; do
    echo "Compteur : $compteur"
    compteur=$((compteur + 1))
done
```

### **Boucle `until`**
```bash
compteur=1
until [ $compteur -gt 5 ]; do
    echo "Compteur : $compteur"
    compteur=$((compteur + 1))
done
```

---

## **7. Fonctions**
### **Définir une fonction**
```bash
ma_fonction() {
    echo "Ceci est une fonction"
}
ma_fonction
```

### **Fonction avec paramètres**
```bash
addition() {
    resultat=$(( $1 + $2 ))
    echo "La somme est $resultat"
}
addition 5 10
```

---

## **8. Gestion des fichiers et répertoires**
### **Lister les fichiers d’un répertoire**
```bash
for fichier in $(ls); do
    echo "Fichier : $fichier"
done
```

### **Vérifier l’existence d’un fichier**
```bash
if [ -e fichier.txt ]; then
    echo "Le fichier existe"
else
    echo "Le fichier n'existe pas"
fi
```

---

## **9. Scripts avancés**
### **Redirections**
- Rediriger la sortie vers un fichier :
  ```bash
  echo "Bonjour" > fichier.txt
  ```
- Ajouter à un fichier :
  ```bash
  echo "Comment ça va ?" >> fichier.txt
  ```

### **Pipes**
- Utiliser la sortie d’une commande comme entrée d’une autre :
  ```bash
  ls | grep "script"
  ```

### **Tâches planifiées**
- Ajouter un script au **cron** pour exécution automatique :
  ```bash
  crontab -e
  ```
  Exemple : 
  ```
  0 6 * * * /chemin/vers/script.sh
  ```

---

## **10. Exercices pratiques**
1. **Script de calculatrice :**
   Créez un script qui demande deux nombres et effectue les opérations (+, -, *, /).
   
2. **Backup automatique :**
   Écrivez un script qui copie tous les fichiers d’un répertoire vers un dossier `backup`.

3. **Analyseur de logs :**
   Écrivez un script qui compte le nombre d'occurrences d'une chaîne dans un fichier donné.

---

## **11. Conclusion**
Le scripting shell est un outil puissant pour tout administrateur ou développeur. En maîtrisant ces bases, vous serez en mesure d'automatiser de nombreuses tâches et de mieux comprendre le fonctionnement des systèmes Unix/Linux. Pour aller plus loin, explorez des concepts comme les commandes `awk`, `sed` et les scripts interactifs.
