#GIT
##Trabajo Individual

Santiago Leonardo Lora Quilla
##Clase 1
###¿Que es GIT?
Git es un administrador de versiones que permite tener un control sobre estas misma

###¿Cual es la historia de GIT?
Git fue creado para la poder gestionar las versiones del kernel de Linux dada 
la necesidad de Linus Torvalds por tener un software no privativo despues te 
tener problemas con otro software de control de versiones, git se creo en 
alrededor de dos a tres semanas despues de que Linus se enojara dadas las 
circunstancias

###Instalacion de GIT
####Linux/Debian o derivados
* sudo apt install git

####Windows
* Descargar el instalador de la pagina oficial
* Realizar el proceso de instalacion normal y listo

###Configurar usuario y correo
####Configurar un nombre global para la maquina
* git config --global user.name "nombreUsuario"
####Configurar un correo global para la maquina
* git config --global user.email "emailUsuario"

###Archivos presentes en los repositorios
* .gitignore
Para evitar tocar archivos sensibles
* README.md
Documentacion basica del proyecto

##Clase 2
###Estados de GIT
* Directorio de trabajo
Carpeta local donde git no tiene nada aun asegurado
- untraquet --> archivo nuevo sin seguimiento por parte de git
- modified --> archivo ya existente en git con alguna modificacion
* Stage Area
Area donde se espera a confirmar guardar
* Repositorio Local
Cambios ya guardados en el historial 

###Devolver archivo modificado a su estado original
git restore <archivo> (Borra fisicamente)

###Llevar archivo a stage area
git add <archivo>
git add .
####Sacar archivo de stage area
git restore --staged <arvhivo>

###Repositorio local, crear punto de guardado
git commit -m "mensaje"
####Deshacer ultimo commit
git reset --soft HEAD~1

###Historial de commits
 git log --> muestra todo el historial
 git log --oneline --> muestra log resumido

###Explicacion y desarrollo del archivo .gitignore
Busca evitar que git lea archivos que se coloquen acorde a nuestras necesidades, generalmente se usar para evitar mostrar o subir archivos con datos sencibles

###Buenas Practicas
- Commits atomicos: hacer commits cada que se algo pequeño pero que cambie la funcionalidad
-  Por ejemplo:
-   Incorrecto:
git commit -m "Metodos multiplicacion y suma"
-   Correcto:
git commit -m "Metodo multiplicacion"
git commit -m "Metodo suma"


###Reglas al describir un commit:
1. Usar verbos imperactivos
2. No uses punto final ni puntos suspensivos en tus mensajes
3. Usa como maximo 50 caracteres
4. Usa un prefijo para los commits
5. Añade todo el contexto que sea necesario en el commit
