## Format des fichiers de documentation

La documentation générale doit être rédigée en Français et intégrée à github par l'intermédiaire du wiki au format d'édition "markdown" (le plus simple pour utilisation avec github).

Pour cela, il suffit de créer un fichier au format "markdown" avec l'extension .markdown.

On peut utiliser [ce visualiseur online](http://markdownlivepreview.com/) pour visualiser le rendu final du document.

## Format des lignes de commande

Les arguments optionnels entre crochets : `[optionnel]`  
Les parties à remplacer entre chevrons : `<a changer>`

Exemple :

`$ ls [-R] <un/chemin/de/fichier>`

On peut taper :

`$ ls /home/user` ou `$ ls -R /home/user`

En début de chaque ligne pour préciser le type utilisateur on utilisera $ ou # :

    $ <commande utilisateur normal> 
    # <commande super-utilisateur>

## Système des fichiers de code

Le code, les commentaires et le README doivent êtres rédigés en anglais.

- Format d'encodage : UTF-8,
- Langage de programmation commun : C++ Version 11,
- Langage de script commun : bash,
- Langage autorisé : Python et C/C++,
- Règles de nommage :
  - Utilisation des accents et espaces prohibés,
  - Tout en minuscule avec underscore ( _ ) et tiret ( - ) autorisé,
  - Exception faite du Find<package>.cmake, README et LICENSE.

Organisation de l'arborescence d'un projet hors ROS :

- projet/
  - module_velocity/  
    - velocity.hpp  
    - velocity.cpp  
  - module2/  
    - ...  
  - share/  
    - script.sh  
    - Findmodule_velocity.cmake  
  - build/  
    - Makefile  
  - CMakeLists.txt  
  - README  
  - LICENSE  

Respecter l'organisation de l'arborescence ROS dans les projets ROS.

## Licence

Libre choix entre deux licences :

- BSD-3-Clause : http://opensource.org/licenses/BSD-3-Clause
- GPL-3.0 : http://opensource.org/licenses/GPL-3.0

Les templates sont disponibles sur le git \<ajouter un lien\>

## README

Devra contenir :

    <Nom du projet> : <description en moins de 80 caractères>

    <Une description plus longue si nécessaire dont les options d'installation/compilation etc.>

## Règles du “bon” code

### Include guard

Utilisation de l'include garde sous cette forme :

    ````
    #ifndef NOM_DU_FICHIER_HPP_	
    #define NOM_DU_FICHIER_HPP_
			
    ...code...
		
    #endif // NOM_DU_FICHIER_HPP_

### En-tête

Tout les fichiers de code doivent comporter l'en-tête suivant :

    /*****************************************************************************/			
    /* ASTUPS 			– PROJECT_NAME                            */		
    /*****************************************************************************/			
    /*			
    * Author : FirstName LastName – mail			
    * Creation Date : xx/xx/xxxx		
    * License : GPL-3.0 / BSD-3-Clause		
    */

### Commentaires - Documentation

- Utilisation de doxygen pour la documentation du code,
- Rédaction en **anglais**,
- Rédaction d'un commentaire par classe/structure décrivant l'objectif,
- Rédaction d'un commentaire par attribut et fonction membre.

### Indentation

Utilisation des tabulations : tous les éditeurs/IDE permettent d'utiliser la tabulation.

Configuration pour Code::Blocks :
  - aller dans Settings/Editor,
  - cocher "Use TAB character"

### Nom de variable - fonction - classe

Commencer les variables par une minuscule, sans caractères spéciaux sauf l'underscore.

- Defines / variables statiques : tout en majuscules,
- Noms de variables : nom_de_la_variable (tout en minuscules),
- Noms de variables membres : _nom_de_la_variable_membre (idem),
- Noms de fonctions (membre ou non) : nomDeLaFonction()
- Noms de classes : NomDeLaClasse

### Accolades

Pas de règles de placement.

### Pointeurs

Utilisation exclusive des pointeurs intelligents ([unique_ptr](http://www.cplusplus.com/reference/memory/unique_ptr/) et [shared_ptr](http://www.cplusplus.com/reference/memory/shared_ptr/)).

### Opérateur de copie

Utiliser l'idiom "[copy and swap](http://stackoverflow.com/a/3279550)"

### Flux de sortie (messages normaux/erreurs/alertes)

- Messages normaux dans : cout / printf,
- Messages d'erreurs et d'alertes dans : cerr / stderr (avec fprintf)
  - erreur : "ERROR : le message"
  - alerte : "WARNING : le message".

Exemple d'erreur avec fprintf :

`fprintf(stderr, "ERROR : wrong value");`

Exemple d'alerte avec cerr :

`std::cerr << "WARNING : negative value");`

### Gestion d'exception

- Utiliser principalement le return boolean false ou pointeur null sur les fonctions en cas d'erreur.
- Possibilité d'envoi des exceptions par throw.

### Flag de compilation

| Description | Argument |
|-------------|----------|
| Prise en compte de tous les warnings | -Wall
| Utilisation de C++ 11 | -std=c++0x |

## Procédure de récupération et démarrage d'un projet Astups

La liste des commandes :

    $ git clone https://github.com/astups/<project>.git
    $ cd <project>
    $ mkdir build
    $ cd build
    $ cmake ..
    $ make

Il est maintenant possible de modifier le projet, pour recompiler il suffit d'exécuter `$ make` à nouveau.