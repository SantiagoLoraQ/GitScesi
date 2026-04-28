# GIT
## Trabajo Individual

Santiago Leonardo Lora Quilla
## Clase 1
### ¿Que es GIT?
Git es un administrador de versiones que permite tener un control sobre estas misma

### ¿Cual es la historia de GIT?
Git fue creado para la poder gestionar las versiones del kernel de Linux dada 
la necesidad de Linus Torvalds por tener un software no privativo despues te 
tener problemas con otro software de control de versiones, git se creo en 
alrededor de dos a tres semanas despues de que Linus se enojara dadas las 
circunstancias

### Instalacion de GIT
#### Linux/Debian o derivados
* sudo apt install git

#### Windows
* Descargar el instalador de la pagina oficial
* Realizar el proceso de instalacion normal y listo

### Configurar usuario y correo
#### Configurar un nombre global para la maquina
* git config --global user.name "nombreUsuario"
#### Configurar un correo global para la maquina
* git config --global user.email "emailUsuario"

### Archivos presentes en los repositorios
* .gitignore
Para evitar tocar archivos sensibles
* README.md
Documentacion basica del proyecto

## Clase 2
### Estados de GIT
* Directorio de trabajo
Carpeta local donde git no tiene nada aun asegurado
- untraquet --> archivo nuevo sin seguimiento por parte de git
- modified --> archivo ya existente en git con alguna modificacion
* Stage Area
Area donde se espera a confirmar guardar
* Repositorio Local
Cambios ya guardados en el historial 

### Devolver archivo modificado a su estado original
git restore <archivo> (Borra fisicamente)

### Llevar archivo a stage area
git add <archivo>
git add .
#### Sacar archivo de stage area
git restore --staged <arvhivo>

### Repositorio local, crear punto de guardado
git commit -m "mensaje"
#### Deshacer ultimo commit
git reset --soft HEAD~1

### Historial de commits
 git log --> muestra todo el historial
 git log --oneline --> muestra log resumido

### Explicacion y desarrollo del archivo .gitignore
Busca evitar que git lea archivos que se coloquen acorde a nuestras necesidades, generalmente se usar para evitar mostrar o subir archivos con datos sencibles

### Buenas Practicas
- Commits atomicos: hacer commits cada que se algo pequeño pero que cambie la funcionalidad
-  Por ejemplo:
-   Incorrecto:
git commit -m "Metodos multiplicacion y suma"
-   Correcto:
git commit -m "Metodo multiplicacion"
git commit -m "Metodo suma"


### Reglas al describir un commit:
1. Usar verbos imperactivos
2. No uses punto final ni puntos suspensivos en tus mensajes
3. Usa como maximo 50 caracteres
4. Usa un prefijo para los commits
5. Añade todo el contexto que sea necesario en el commit


## Clase 3
### Creacion de cuenta en GitHub
Se mostro el como se registra un nuevo usuario en GitHub con un nombre de usuario, correo, contraseña y complertado de un captcha
luego de iniciar sesion se realizo la creacion de un nuevo repositorio publico

### Conexion maquina local con GitHub
Despues de tener configurado el correo y nombre de usuario en git y haber realizado diferentes commits se debe crear un enlace con GitHub con el siguiente comando:
git remote add origin git@github.com:usuario/nombre-del-repositorio.git
Para subir los archivos se ejecuta:
git push -u origin main (o la rama que se quiera usar

#### Creacion de llaves para SSH
En windows se hace desde git bash
En linux se hace desde la consola con el comando:
- ssh-keygen -t ed25519 -C "correo@gmail.com" 
ese comando genera un codigo en una ubicacion en la cual se puede acceder en la ubicacio indicada al generar el codigo

Se debe copiar el codigo y en los ajustes de GitHub debemos ir a la seccion ssh and gpg keys donde se le pone un nombre al codigo y se pega la key para luego agregar la key
Se pruba que todo haya funcionado bien con el comando:
- ssh -T git@github.com

### Beneficios de usar ssh
No pide credenciales a cada rato
Mejora el flujo de trabajo 
Sirve para un mejor acceso remoto y administracion de sistemas

### Beneficion de GitHub Universitario
Copilot gratis
Creditos
Dominios gratis
Varias herramientas de distintas plataformas

### Maximo a subir en un commit
- Limite por archivo individual:
100MB como tope y a los 50MG se da una advertencia
- Limite por commit:
Por recomendacion de 2GB
- Limite del repositorio
Se recomienda mantenerlo por debajo de 1GB - 5GB

## Clase 4
### Git remote
Es un comando para gestionar conexiones con los repositorios y sus direcciones
- git remote -v
Permite ver la direccion o url del repositorio
- git remote add <apodo> "url"
Agrega o vinclula el repositorio local con el de la nube
- git remote set-url <apodo> "urlNueva" 
Cambia la url actual por la nueva

### Tener varias ssh
Se puede configurar varias claves ssh acorde a las necesidades que se tengan
se debe generar el ssh con un nuevo nombre para evitar reemplazar el anterior con el ya creado
ssh-keygen -t miKey -C "correo@gmail.com" -f direccionDeGuardado

se debe crear un archivo llamado config donde se deben configurar las dos keys segun sea necesario

### Checkout
 inspeccionar
 restaurar
 experimentar
 cambiar
## Clase 4
### Ramas o branches
Las ramas son una caracteristica que permite al usuario subdividir su repositorio para tener un control acorde a las necesidades del usuario
#### git branch
comando para listar las ramas disponibles
#### git branch <rama>
crea una rama desde la rama en la que estamos ubicados
#### git branch -D <rama>
Elimina la rama

### git checkout en ramas
#### git checkout <rama>
cambiar la rama
#### git checkout -b <rama>
crea la rama y te pone en llamado
### Gitflow
Es un flujo de trabajo que nos permite tener una coherencia y logica mas organizada al momento de utilizar git y las ramas, si bien no es obligatorio tiende a ser algo justo y necesario para permitir un flujo adecuado de nuestros trabajo
### Ramas que se utilizan en Gitflow
main --> rama principal al momento de crear cualquier repostorio, solia usarse como master 
develop --> donde se prueban y preparan las nuevas caracteristicas 
feature --> desarrollo de las nuevas caracteristicas
release --> es la preparacion de las nuevas caracteristicas
hotfix --> donde se realiza el arreglo de bugs para evitar tocar el sistema en cambio constante


