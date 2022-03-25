# search_everywhere
Chercher partout un texte en clair

Forme générale (élaboré par moi même, non trouvé tout fait et en plus elle est simple à comprendre
```sh
user@host:~# IFS=$'\n' ; for d in $( ls -1 / | grep -Ev "dev|proc|run|sys" ) ; do CODE ; done ; unset IFS
```
où CODE utilise le dossier de niveau 2 /$d comme point de départ

Par exemple trouver toutes les occurrences de l'interface ens3 après renommage (rappel : grep -I ne traite pas les fichiers binaires)
```sh
user@host:~# IFS=$'\n' ; for d in $( ls -1 / | grep -Ev "dev|proc|run|sys" ) ; do grep -Ir ens3 /$d ; done ; unset IFS
```
