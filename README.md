# hyperblog

Un respositorio para practicar Git y GitHub

## Notas para el curso de Git y Git Hub

el comando siguiente sirve para traer los cambios de la plataforma de GitHub

        -git pull origin master
        -git config --global user.email "corre@acambiar.com"        -Permite cambiar le email
        -git branch branchName                                      -Crea una rama nueva
        -git checkout branchName                                    -Cambia de rama
        -git push origin branchName                                 -Publica la rama local en repositorio remoto

## Para crear una llave SSH

Para crear una llave privada y publica se hace lo siguiente

    1.- Se ejecuta el comando ssh-keygen -t rsa 4096 -C "braulio.arher@gmail.com" esto te genera las llaves y puedes crear una contrasennia para agregar un nivel mas de seguridas, tambien te crea un carpeta donde se almacenan tus llaves
    2.- Se ejecuta el comando siguiente para evaluar que si esta disponible la llave: eval $(ssh-agent -s)
    3.- Se agrega la llave a nuestro entorno con el comando: ssh-add ~/.ssh/id_rsa

Cada entorno o cada computadora debe tener una llave privada y publica individualmente

Una vez creada y aniadida la llave a nuestro dispositivo podemos compiar la llave publica y anniadirla a GitHub en la seccion de setting y en donde dice SSH and GPG keys

## Llaves publicas y privadas

Permite una comunicacion segura al mandar un mensaje cifrado con la llave publica solo la podra abrir quien tenga la llave privada

En GitHub se usa por temas de seguridad el protocolo SSH

Para cambiar de protoculo HTTPS a SSH anteriormete debimos de haber creado nuestras llaves despues ubicarnos en nuestra carpeta de nuetro repositorio y ejecutar el comando git remote set-url origin linkdelrepositorioQueViveenGitHub

## Clonar un repositorio

Para clonar un repositorio basta con usar el siguiente comando
    git clone SSHdelRepocitorio

## Tags y versiones en Git y Github

git log --all --graph --decorate --oneline

el comando anterior sirve para mostar la historia de nuestro repositorio de una forma mas grafica para que esta pueda ser leida

alias arbol="git log --all --graph --decorate --oneline"   sirve para crear un alias a un comando y acceder mas facilmente a el

git tag -a v0.1 -m "Resultado de las primeras clases del curso" #######         crea un nuevo tag

git tag                         -Muestra todos los tag disponibles en el repositorio
git show-ref --tags         -Muestra el id de los commits de cada tag

Los tags no son cambios pero son utilies en GitHub para que otras personas lo vea

git push origin --tags      -Envia a GitHub los tags creados en el repo

git tag -d nombretag        -Elimina el tag creado solamente en git esto no se ve refleja en gitHub
git push origin :refs/tags/nombretag  -Elimina el tag almacenado en GitHub

En esta clase se aprende a crear y eliminar tags tanto en Git como en GitHub

## Manejo de ramas en GitHub

git show-branch                     -Muestra ramas que existen y cual es su historia
git show-branch --all               -Muestra ramas que existen y cual es su historia pero con mas datos
gitk                                -Muestra de forma mas visual la historia del repo

## Configurar multiples coolaboradores en repositorio de GitHub

Debemos de autorizar a nuevos usuarios para que pueda hacer push en gitHub esto se hace de la siguiente manera:

en el repositorio se va a settings=>collaborators=>escribe el email a agregar o usuario

la persona que quiere colaborar recibira un correo para que pueda colaborar en el repositorio

## Flujo de trabajo profesional

Para poder desarrollar software de manera óptima y ordenada, necesitamos tener un flujo de trabajo profesional, que nos permita trabajar en conjunto sin interrumpir el trabajo de otros desarrolladores. Una buena práctica de flujo de trabajo sería la siguiente:

    1.- Crear ramas
    2.- Asignar una rama a cada programador
    3.- El programador baja el repositorio con git pull origin master
    4.- El programador cambia de rama
    5.- El programador trabaja en esa rama y hace commits
    6.- El programador sube su trabajo con git push origin #nombre_rama
    7.- El encargado de organizar el proyecto baja, revisa y unifica todos los cambios
