Curso de Git / Github Jonmircha
https://jonmircha.com//git

git --version
git config --global user.name "Jonathan MirCha"
git config --global user.email jonmircha@gmail.com
git config --global user.ui true
git config --global init.defaultBranch main
git config --list
# asignando visual studio code como editor de configuración de git
git config --global core.editor "code --wait"
git config --global -e
# para estandarizar los saltos de línea en windows
git config --global core.autocrlf true
# para estandarizar los saltos de línea en linux/mac
git config --global core.autocrlf input
# ver todas las opciones de la configuración en la terminal
git config -h
# ver todas las opciones de la configuración en el navegador
git help config

////////////////////////

ls para listar

git init
git add .
git commit -m "mensaje del commit"


////////////////////
# se agrega el origen remoto de tu repositorio de GitHub
git remote add origin https://github.com/usuario/repositorio.git
# la primera vez que vinculamos el repositorio remoto con el local
git push -u origin master
# para las subsecuentes actualizaciones, sino cambias de rama
git push


#para descargar los cambios del repositorio remoto al local
git pull


/////////////////
Para repositorios existentes

git branch -M main
git remote add origin https://github.com/usuario/repositorio.git
git push -u origin main


//////
Clonar repositorios

git clone https://github.com/usuario/repositorio.git

//////

git branch nombre-rama

# cambiar de rama
git checkout nombre-rama

# crear una rama y cambiarte a ella
git checkout -b rama

# eliminar rama
git branch -d nombre-rama

# eliminar ramas remotas
git push origin --delete nombre-rama

#eliminar rama (forzado)
git branch -D nombre-rama

# listar todas las ramas del repositorio
git branch

# lista ramas no fusionadas a la rama actual
git branch --no-merged

# lista ramas fusionadas a la rama actual
git branch --merged

# rebasar ramas
git checkout rama-secundaria
git rebase rama-principal

estamos

# hacer push en remoto
git push -u origin rama-a-subir

# merge de ramas
Nos posicionamos en la rama main (principal)
desde ahi hacemos 
git merge rama-a-fusionar

luego hacemos el push final para subir a remoto
git push -u origin rama-a-subir

# traer una rama  desde remoto (en este caso la rama es html)
git checkout -b html  origin/html


# borrar rama remota en este caso es css
git push origin --delete css


Cambios

Puedes agregar modificaciones al último cambio

# sin editar el mensaje del último commit
git commit --amend --no-edit

# editando el mensaje del último commit
git commit --amend -m "nuevo mensaje para el último commit"

# eliminar el último commit
git reset --hard HEAD~1

Podemos desplazarnos en el historial del repositorio hacia atrás o adelante en cambios o ramas , sin afectar el repositorio como tal.

# cambiar a una rama
git checkout nombre-rama

# cambiar a un commit en particular
git checkout id-commit

# poner un tag (etiqueta)
# listar etiquetas
git tag

# crea una etiqueta
git tag numero-versión

# eliminar una etiqueta
git tag -d numero-versión

# mostrar información de una etiqueta
git show numero-versión

# sincronizando la etiqueta del repositorio local al remoto
git add .
git  tag v1.0.0
git commit -m "v1.0.0"
git push origin numero-versión

# generando una etiqueta anotada (con mensaje de commit)
git add .
git tag -a "v1.0.0" -m "Mensaje de la etiqueta"
git push --tags