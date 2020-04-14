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

1 - copia el contenido de este repositorio utilizando comandos de git o haciendo download de el contenido por el browser

2 - Una vez que tenga los archivos en una pasta/directorio ( deven de ser 2, el Vagrantfile y el README.md )

3 - ejecuta el comando utilizando el prompt de POWERSHELL de Windows / O BASH desde Linux / O Linea de comando de MacOs

                                             vagrant up
** Ps.: Necesita utilizar el comando de dentro de el directorio donde esta el Vagrantfile. **

4 - este comando va a arrancar la VM ya con el Podman instalado y listo para se utilizar

# Comandos de podman para el DEMO
