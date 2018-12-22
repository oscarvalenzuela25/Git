# Recordatorio personalizado sobre el uso de Git y GitHub :octocat:

## Temario 
:pencil:
1. [Comenzando nuestra área de trabajo](#1-comenzando-nuestra-área-de-trabajo)
2. [Identificandonos](#2-identificandonos)
3. [Examinando el historial y los estados](#3-examinando-el-historial-y-los-estados-log-status-show-reflog)
   * [log](#git-log)
   * [status](#git-status)
   * [show](#git-show-v100)
   * [reflog](#git-reflog)
4. [Trabajando con Git](#4-trabajando-con-git-add-mv-reset-rm-commit)
   * [add](#git-add----)
   * [mv](#git-mv-heroeshtml-villanohtml)
   * [reset](#git-reset-xml) 
   * [rm](#git-rm-archivo)
   * [commit](#git-commit--m-nombre)
5. [Ignorando Archivos](#5-ignorando-archivos)
6. [Trabajando con Ramas](#6-trabajando-con-ramas-branch-checkout-diff-tags-rebase-merge)
   * [branch](#git-branch)
   * [checkout](#git-checkout-nombre_rama)
   * [diff](#git-diff)
   * [tags](#git-tag)
   * [rebase](#git-rebase-master-nombre_rama)
   * [merge](#git-merge-nombre_rama)
7. [Trabajando colaborativamente](#7-trabajando-colaborativamente-fetch-pull-push)
   * [fetch](#fetch)
   * [pull](#pull)
   * [push](#push)
8. [Shortcuts](#8-shortcuts-atajos)
9. [GITHUB](#9-github)

## Si estas retomando todo lo que es git o te ha ocurrido algun error, consulta la seccion de casos.

:eyes:

[Ir a Casos](https://github.com/oscar8232003/Materias/blob/master/Git/casos.md#casos)

![Diagrama explicado](https://image.ibb.co/gor8ff/Diagrama-en-blanco.png)

## 1 Comenzando nuestra área de trabajo.
#### git help 
> Sirve para ver información de ayuda en git pero general.
#### git help comando 
> Sirve para ver la información de ayuda de un comando en específico.
#### git clone  
> Clona un repositorio en una carpeta específica.
#### git init   
> Inizializa un repositorio nuevo.

[Volver al inicio](#temario)

## 2 Identificandonos
:person_with_blond_hair::woman:
#### git config --global user.name "Oscar" 
> Sirve para identificarse con un nombre.
#### git config --global user.email "correo@gmail.com" 
> Sirve para identificarse con un email.
#### grit config --global -e 
> Sirve para ver la información global de nuestro repositorio(si quieren salir es :q sin guardar y :w con guardar).

[Volver al inicio](#temario)

## 3 Examinando el historial y los estados (log, status, show, reflog)
:coffee:
#### git log 
> Muestra los commit hechos desde el último hasta el más reciente.
#### git log --oneline 
> Muestra los logs pero con commit cortos y los nombres.
#### git status 
> Muestra en qué branch estamos trabajando, si hay archivos en rojo esos están modificados o fuera del stage y si están en verde es porque ya están en el stage para poder hacer un commit.
#### git show v1.0.0 
> Muestra información de un tag.
#### git reflog 
> Sirve para ver el historial de logs, esta todo lo que se ha hecho, sirve para reestablecer versiones que no se encuentran visibles en el log. 

[Volver al inicio](#temario)

## 4 Trabajando con Git (add, mv, reset, rm, commit).
:package:
#### git add -- . 
> Agrega todos los elementos a la carpeta git con el ..
#### git add *.png 
> Agrega todos los elementos a la carpeta pero con extensión .png.
#### git add img/ 
> Agrega todos los elementos de la carpeta img.
#### git add "*.txt" 
> Agrega todos los archivos .txt del proyecto.
#### git add *.txt 
> Agrega todos los archivos modificados del Directorio actual.
#### git add css/*.css 
> Agrega todos los .css de la carpeta css.
#### git add -A 
> Agregar todos los archivos que fueron modificados o que no están en el stage.
#### git mv heroes.html villano.html  
> Cambia el nombre de un archivo (actual, nuevo).
#### git reset *.xml  
> Saca todos los elementos con la extensión .xml del stage.
#### git reset --soft README.md 
> Saca de la carpeta git el elemento hacia el stage.
#### git reset --soft HEAD^ 
> Saca de la carpeta git el ultimo commit hacia al stage.
#### git reset --soft version 
> Saca de la carpeta git una versión que uno quiera, tener en cuenta que toda versión que estuvo después de esta se restablece y queda en el stage.
#### git reset --hard version 
> Devuelve todo a una versión que uno escoja, tener en cuenta que esto borra todo lo que uno hizo antes de esta versión.
#### git rm archivo 
> Borra un archivo, tener en cuenta que para que esto surta efecto hay que hacer un add y commit después de removerlo.
#### git rm directorio.html 
> Remueve del proyecto el archivo escogido.
#### git commit -m "Nombre"  
> Hace un commit, es decir lo saca del stage para guardarlo.
#### git commit -am “Mensaje” 
> Agrega y pone un mensaje de inmediato, solo sirve si el archivo fue modificado, si el archivo no ha entrado en el repositorio anteriormente no servirá.
#### git commit --amend -m “mensaje actualizado” 
> Actualiza el log del último commit.

[Volver al inicio](#temario)

## 5 Ignorando Archivos.
:hear_no_evil:
#### Para poder ignorar archivos que no encontremos que sean relevantes subir al repositorio se crea un archivo .gitignore dentro de la raíz del proyecto.
#### Después dentro del archivo se pone los archivos que se quieran ignorar, pueden ser archivos, directorios, etc.
#### Si quieres ignorar un conjunto de archivos puedes poner la extensión de los archivos que quieras ignorar.

[Volver al inicio](#temario)

## 6 Trabajando con Ramas (branch, checkout, diff, tags, rebase, merge).
:evergreen_tree::deciduous_tree:
#### git branch 
> Verifica las ramas creadas.
#### git branch nombre_rama  
> Crea una rama de trabajo nueva, las ramas sirven para trabajar con todo el proyecto antes de crear la rama, en mi opinión sirve para hacer pruebas ya que si cambias a la rama antes de crear esta, el proyecto vuelve antes de crear la rama.
#### git branch -d nombre_rama 
> Elimina la rama nombre_rama, si hay commit en esa rama te preguntará si la quieres borrar.
#### git branch -D nombre_rama 
> Elimina la rama nombre_rama con o sin commits que se hayan hecho en esa rama.
#### git checkout nombre_rama 
> Te cambia para trabajar en esa rama.
#### git checkout -b rama_nueva 
> Crea la rama y se une automáticamente. 
#### git checkout -- .   
> Restaura a la última versión en el cual se hizo el commit.
#### git diff 
> Muestra los cambios que existen en el archivo fuera del stage.
#### git diff --stage 
> Muestra los cambios del archivo en el stage.
#### git diff rama-villanos master 
> Ve los cambios en la rama-villanos a diferencia del máster.
#### git tag 
> Sirve para ver los tags existentes.
#### git tag nombre_tag 
> Crea un tag al último commit que se ingresó.
#### git tag -a v1.0.0 -m “versión 1.0.0” 
> Crea el tag con un mensaje.
#### git tag -a v0.1.0 345d7de -m “versión alfa” 
> Crea el tag hacía una versión.
#### git tag -d nombre_tag 
> Elimina el tag.
#### git rebase master nombre_rama 
> Si se está en la rama master se ocupa este comando para dejar a nombre_rama antes que al master, queda de más decir que al rebasar todos los cambios hechos en master ahora se agregaran a nombre_rama.
#### git rebase master 
> Si se está en la rama nombre_rama se puede ocupar este comando.
#### git merge nombre_rama 
> Une la rama nombre_rama hacia el master, hay que estar en el máster para poder unirlas.

[Volver al inicio](#temario)

## 7 Trabajando colaborativamente (fetch, pull, push).
:couple:
#### fetch     
> Comprueba si hay cambios en el repositorio remoto ante nuestro repo local.
#### pull       
> Si hay cambios en el repositorio remoto y no los tienes en el local, con el pull puedes hacer los cambios que se hicieron en el remoto.
#### push       
> Actualizamos el repositorio remoto con información de tu repositorio local.

[Volver al inicio](#temario)

## 8 Shortcuts (Atajos!).
:thumbsup:
#### git config --global alias.nombre_alias "comando" 
> Creamos un shortcut personalizado.
#### git config --global -e  
> Sirve para ver las configuraciones globales(:q para salir).
#### git config --global alias.lg “log --oneline --decorate --all --graph”  
> Crea un comando que al digitar lg es la abreviación de toda la sentencia que está entre comillas, este comando sirve para reemplazar el log.
#### git config --global alias.s “status -s -b” 

[Volver al inicio](#temario)

## 9 GITHUB.
:kissing_heart::octocat:
#### Primero hay que crear un nuevo repositorio dentro de github.
#### Aparecerán estas 2 líneas, el remote add origin es para dejar puesto las credenciales del repositorio.
#### git remote add origin https://github.com/oscar8232003/udemy-heroes.git.
#### git push -u origin master (origin es dentro del origen y master es hacia la rama master).
#### Para verificar si esta todo correcto digita.
#### git remote -v.
#### Si tienes problemas con las credenciales digita git credential-manager uninstall y desinstala el manager de credenciales e install si lo quieres volver a instalar.
#### El fork es para copiar el repositorio a tu repositorio y hacer los cambios que quieras, es como clonar un proyecto pero este lo sube automáticamente a tu repo.

#### git push --tags 
> Sirve para subir los tags.
#### git push 
> Sube todos los cambios de mi repo local al repo remoto.
#### git push :rama-eliminada 
> Se elimina la rama de git local y después se manda a el repo remoto.
#### git pull 
> Copiamos los cambios del repositorio remoto al repositorio local.
#### git pull --all 
> Si hay problemas con el pull, se le pone el --all.
#### git fetch 
> Organiza los cambios que se le hicieron al proyecto, es decir, si hay cambios en ambos repositorios, el fetch sirve para que se cree una rama con los cambios del repositorio remoto.
#### git clone https://github.com/oscar8232003/udemy-heroes.git 
> Vamos a la carpeta donde queremos poner el proyecto navegando por la terminal y ponemos el comando.
#### git clone https://github.com/oscar8232003/udemy-heroes.git demo-10 
> Vamos a la carpeta donde queremos poner el proyecto, ponemos el comando y lo pone con el nombre demo 10.
#### git push origin rama_destinataria 
> Hace un push con el contenido a la rama_destinataria.

[Volver al inicio](#temario)
