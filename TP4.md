# Exercice 1. Commandes de base

1. Mettre à jour le système : On utilise `sudo apt update` et `sudo apt upgrade`
2. Création de l'alias `alias maj = "sudo apt update && sudo apt upgrade"`
3. Ce fichier contient la liste de tous les paquets installés, pour obtenir les 5 derniers paquets installés il faut utiliser la commande `tail -n 5 /var/log/dpkg.log`
4. Pour avoir la liste des paquets de `apt install`, on utilise `apt list --installed`
5. **dpkg** contient énormément de noms de paquets il faut donc utiliser `wc -l` pour compter toutes les lignes. On utilise donc `dpkg -l | wc -l`, il y a 622 paquets pour **dpkg**. Egalement pour **apt**, `apt list --installed | wc -l`, il y a 615 paquets. La différence est que **dpkg** ne gères pas des dépendences.
6. `apt list | wc -l` il y a 68953 paquets disponibles.
7.  `glances` : afficher les informations du système linux  
    `tldr` : donner une explication simplifiée   
    `hollywood` : afficher des visuels/interfaces ressemblant à des écrans des hacker dans les films hollywood.   
8. On peut en trouver avec la commande `apt-cache search sudoku` pour trouver des paquets concernant sudoku.

# Exercice 2.
La commande est `dpkg -S` et en une seule commande pour trouver le paquet de ls `dpkg -S $(which -a ls) 2> /dev/null`
```bash
#!/bin/bash
find(){
    dpkg -S $(which -a $1)  2> /dev/null ;
}
find $1;
```
# Exercice 3.
On peut utiliser `apt list [NomDePaquet] | grep "installed" && echo "INSTALLé" || echo "NON INSTALLé"`

![image](https://user-images.githubusercontent.com/97104312/192953938-a9cb4af4-e1a7-4169-8380-78fe79b8d4b2.png)

# Exercice 4.
Pour lister les programmes livré par coreutils on utilise: `dpkg -L coreutils | xargs which`  
`[` est identique à la commande `test`: elle vérifie le type de fichier et comparer ses valeurs. 
# Exercice 5. aptitude
Etapes pour installer des paquets avec **interface aptitude**  
    -`sudo aptitude`  
    -`/` pour chercher le paquet souhaité  
    -`!` ou `+` pour sélectionner le paquet  
    -`g` pour installer  

# Exercice 6. Installation d’un paquet par PPA
2. Le fichier **/etc/apt/sources.list.d** contient tous dépôts de paquet.

# Exercice 7. Installation d’un logiciel à partir du code source


# Exercice 8. Création de dépôt personnalisé
