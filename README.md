clase-de-github - en la rama mejorandola 
===============

Este es un ejemplo de Github para la comunidad de #mejorandola 

Una vez instalas GIT, debes configurarlo:

git config --global user.name "Christian"
git config --global user.email "xxxxxx@xxxx.com"

Generando tu Public Key:

ssh-keygen 

Leyendo tu llave para copiarla a Github:

cat ~/.ssh/id_rsa.pub

Arrancando tu proyecto:

git init

touch README

git add README

git commit -m "tu primer commit"

git push origin master