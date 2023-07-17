# kong-course
Para evitar que tengas que instalar todo el software necesario para construir y ejecutar el proyecto en local,
este proyecto utiliza [Vagrant](https://www.vagrantup.com/).

Para que [Vagrant](https://www.vagrantup.com/) funcione, necesitarás instalar:

* [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
* [Vagrant](https://www.vagrantup.com/downloads.html)

Una vez tengas instalado [Vagrant](https://www.vagrantup.com/), ejectuando

```
$ vagrant up
```

levantarás una máquina virtual Ubuntu con:

* Docker

A la máquina virtual se accede mediante ```ssh```, ejecutando sobre la raiz del proyecto

```
$ vagrant ssh
```

La máquina virtual se puede detener, utilizando el comando

```
$ vagrant halt
```

o bien destruir, usando

```
$ vagrant destroy
```
