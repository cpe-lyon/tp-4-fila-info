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
![image](https://user-images.githubusercontent.com/97104312/193518902-e641f31d-6245-47d0-85a0-2eae71d6f7c2.png)

![image](https://user-images.githubusercontent.com/97104312/193518105-90bdc1a3-cce5-4619-94d4-5511c93958f0.png)

# Exercice 8. Création de dépôt personnalisé

![image](https://user-images.githubusercontent.com/97104312/193065877-b21d71a6-d870-4dfa-839a-2f667ff97538.png)

![image](https://user-images.githubusercontent.com/97104312/193065978-a38e32e8-c6a4-419b-8e95-92fac3bfd52a.png)

![image](https://user-images.githubusercontent.com/97104312/193068055-82105398-557b-4cfd-982d-0ed9ea627f14.png)
