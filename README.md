Columbia Esterel Compiler (sauvegarde)
==========================================

Ce dépot contient une sauvegarde du compilateur open-source du langage Esterel.
La version originale de ce compilateur est accessible [ici](http://www.cs.columbia.edu/~sedwards/cec/), toutefois la version présente dans ce dépôt est un fork d'une version modifiée établie par un certain dilawar accessible [ici](https://github.com/dilawar/cec-esteral).

La version d'origine proposée par LudvikGalois de cec ne peut plus être compilée aujourd'hui et sans le fork de dilawar le langage aurait complètement disparu. L'objectif de ce dépôt est donc avant tout de préserver une copie du compilateur afin d'éviter qu'il ne sombre définitivement.

La compilation de cec a été testée en Janvier 2020 sur Debian 10.1.0 à partir de l'image net minimale (utilisée sous qemu).

Pour compiler cec vous aurez besoin de :
 - git
 - gcc
 - g++
 - make
 - cmake
 - noweb
 - libexpat1 et libexpat1-dev

Vous pouvez peut-être vous en sortir sans libexpat1-dev, je n'ai pas essayé.

Afin de compiler cec (en détaillant toutes les étapes):
 - Si ce n'est pas déjà fait, intallez les dépendances : $ sudo apt install git gcc g++ make cmake noweb libexpat1 libexpat1-dev
 - Clonez ce dépôt : $ git clone https://github.com/minformatique/cec-esteral.git
 - Rendez vous de le dossier du dépôt cloné : $ cd cec-esteral
 - Configurez avec cmake : $ cmake .
 - Compilez avec make : $ make
 - Installez avec make : $ make install

Si jamais cec ne parvient pas à compiler et vous renvoie un message comme "libcec.so.0.4.1 is not found" ou quelque chose de semblable c'est parce que la librairie libcec.so a été placée dans /usr/lib/ qui n'est peut-être pas indexé. Pour régler le problème, vous pouvez soit indexer le dossier dans lequel se trouve libcec.so (par exemple avec ld) soit copier libcec.so et libicec.so.0.4.1 dans un emplacement indexé (par exemple /lib).

Attention cependant, il semble que cec n'est jamais été vraiment fini (Esterel en général non plus d'ailleurs) et le compilateur risque de ne pas toujours se comporter comme il le devrait.
