# search_everywhere
Chercher partout un texte en clair

Forme générale :
```sh
user@host:~# IFS=$'\n' ; for d in $( ls -d1 /* | grep -Ev "dev|proc|run|sys" ) ; do CODE ; done ; unset IFS
```
où CODE utilise le dossier de niveau 2 /$d comme point de départ

Nota : cette commande a été élaboré par moi même (inspiré par d'autres mais non trouvé tout fait) et elle a l'avantage d'être simple à comprendre.

Par exemple trouver toutes les occurrences de l'interface ens3 après renommage :
```sh
user@host:~# IFS=$'\n' ; for d in $( ls -d1 /* | grep -Ev "dev|proc|run|sys" ) ; do grep -Ir ens3 $d ; done ; unset IFS
```
Rappel :  grep -I ne traite pas les fichiers binaires
