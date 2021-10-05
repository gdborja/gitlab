# Instalación de GitLab en Linux

En la siguiente guía se va a proceder a realizar la instalación de Gitlab y una breve configuración de la misma.

A la vez que ***Github***, ***GitLab*** es un servicio web de control de versiones y además un gestor de repositorios donde se puede alojar, por ejemplo, diferentes versiones para descargar un producto. La diferencia entre ambos es que este último es de código abierto y por lo tanto siempre gratuito.


# Requisitos

Será necesario Debian 11 o cualquier otra distro Linux, acceso a internet y permisos de administrador para el usuario.

# Instalación en local

Antes de comenzar actualizar los repositorios como el sistema operativo.

```console
sudo apt update && sudo apt upgrade
```
## Instalación de paquetes adicionales

Es necesario instalar los siguientes paquetes.

```console
sudo apt install -y vim curl ca-certificates apt-transport-https
```

## Instalación de GitLab

El equipo oficial de Gitlab proporciona un script de shell para configurar el repositorio APT en su sistema, así como para instalar algunas dependencias necesarias.

```console
curl -s https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | sudo bash
```

Continuar lanzando el siguiente comando.

```console
sudo apt install gitlab-ce
```

 Hasta finalizar con un  mensaje similar a:
```
Thank you for installing GitLab!
```

Para terminar la instalación deberá ejecutar el siguiente comando que llevará algo de tiempo terminar de configurar.

```console
sudo gitlab-ctlreconfigure
```  

Comenzará ejecutarse el proceso de configuración. Llevará unos minutos.

# Acceso

Para acceder debemos utilizar el navegador introduciendo en la url nuestra dirección IP o mediante localhost.

Nos mostrará un panel de login y como es nuestro primer acceso debemos configurar su contraseña. Para ello, seguimos el siguiente enlace  [congigurar usuario root desde linea comandos](https://lab.las3.de/gitlab/help/security/reset_root_password.md), y posteriormente volvemos reconfigurar Gitlab para que se gurarden los cambios.

```console
sudo gitlab-ctl reconfigure
  ```









