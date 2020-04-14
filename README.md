# Contenedores

Esto es un archivo readme para la utilizacion de el vagrant para una demo de contenedores

# Requisitos

Necesitas tener instalado en su equipo Vagrant ( version 2.2.7 ) VirtualBox ( Version 6.1 ) estes tramites fueran hechos en equipos Linux Fedora 31 y Windows 10 pero deven de jalar bien en MacOs de la misma forma.

# Links :

1 - https://www.vagrantup.com/downloads.html

2 - https://www.virtualbox.org/wiki/Downloads

# Instalacion de podman en Centos 8 / RHEL 8 -- que no estan utilizando esta recepta de Vagrant --

# Centos 8:

[root@miequipo ~]# dnf install podman

# RHEL 8:

[root@miequipo ~]# dnf module install container-tools -y

Ps.: Para RHEL 8 necesitas de una subscripcion valida para el download de los paquetes requeridos
Ps.2: Para los que estan utilizando Vagrant de esto repositorio la instalacion de podman ya se hace cuando arranca el equipo


# Despues de instalar Vagrant y VirtualBox haga lo que sigue :

1 - Copia el contenido de este repositorio utilizando comandos de git o haciendo download de el contenido por el browser

2 - Una vez que tenga los archivos en una pasta/directorio ( deven de ser 2, el Vagrantfile y el README.md )

3 - Ejecuta el comando utilizando el prompt de POWERSHELL de Windows / O BASH Linux / O Linea de comando de MacOs

                                             vagrant up
** Ps.: Necesita utilizar el comando de dentro de el directorio donde esta el Vagrantfile. **

4 - este comando va a arrancar la VM ya con el Podman instalado y listo para se utilizar

# Comandos de podman para el DEMO de podman

# Verifica que su instalacion de podman se funciona:

sudo podman ps
sudo podman info


# Vamos a jalar un contenedor?

sudo podman run hello-world

# Miro todo que he pasado ?
# Podman tiene muchos repositorios de donde pode sacar imagenes ( incluso se configura localmente...).
# Verifica sus imagenes:

sudo podman image ls -a

# Verifica sus contenedores:

sudo podman ps -a

# Remove contenedores:

sudo podman rm <id de lo comando arriba>

# Remove imagenes:

sudo podman image rm <id de la imagen>

# Bueno, me gustaria tener um Web Server. ¿Como hacerlo?
# Creando un Dockerfile desde cero:
# Crea el archivo Dockerfile con el contenido

FROM centos:latest
RUN yum -y install httpd
CMD [“/usr/sbin/httpd”, “-D”, “FOREGROUND”]
EXPOSE 80

# Listo!

# Comando de construir:

sudo podman build .     <--- haga caso a el pequño punto, es tu directorio actual donde creo su Dockerfile

# Verifica tu imagen y pone a jalar!

sudo podman run -dit -p 80:80 

# Ahora acesa la direction IP con el comando Curl

curl -I http://localhost:80

# Listo
