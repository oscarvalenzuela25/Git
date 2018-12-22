# Casos

## En el caso de que el repositorio local y el repositorio remoto tengan cambios por separado.

1. Primero se hacen los respectivos commits de los cambios que se hayan hecho en el repositorio local. 
2. Segundo se hace un fetch, el fetch sirve para que la rama del repositorio remoto se comporte como una rama aparte por ende al hacer el fetch queda como una rama suspendida.
3. Tercero no podemos subir nuestros cambios si el repositorio remoto tiene cambios pendiente por ende se debe hacer un git pull para sacar los cambios dentro del repositorio remoto hacia el repositorio local.
4. Cuarto teniendo los cambios hechos en el repositorio remoto hacia el repositorio local, ahora solamente queda subir los cambios que hicimos en el repositorio local hacia el remoto con un git push.
