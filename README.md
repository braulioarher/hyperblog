# hyperblog

Un respositorio para practicar Git y GitHub

## Notas para el curso de Git y Git Hub

el comando siguiente sirve para traer los cambios de la plataforma de GitHub

        -git pull origin master
        -git config --global user.email "corre@acambiar.com"         -Permite cambiar le email

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