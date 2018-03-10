# LibreGOB

## Generalidades e instalación.
LibreGOB es un Planificador de Recursos Gubernamentales (GRP) basado en <a href="https://www.odoo.com">Odoo</a>, esta diseñado para funcionar en cualquier equipo que permita utilizar una versión de docker superior o igual a 17.6, las pruebas se realizan sobre [Ubuntu 16.04 LTS](https://www.ubuntu.com/download/desktop/contribute?version=16.04.4&architecture=amd64), concretamente sobre [Microwatt OS v10](http://planetwatt.com/new/index.php/downloads/), por lo tanto, la presente guía y toda la documentación se basa en este entorno de trabajo. La compatibilidad con entornos Windows o distribuciones distintas no está garantizada y no se receptarán correcciones de errores para estas plataformas.

Una vez que hemos instalado uno de los sistemas operativos soportados, procedemos a instalar las dependencias, a continuación ejemplificamos la forma más sencilla de instalación, si desea información más completa o actualizada, puede remitirse a las guías oficiales de cada aplicativo:

Instalamos [Git](https://git-scm.com/)

```console
foo@bar:~$ apt install git
```
[Docker](https://www.docker.com/)

```console
foo@bar:~$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
foo@bar:~$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
foo@bar:~$ sudo apt-get update
foo@bar:~$ apt-cache policy docker-ce
foo@bar:~$ sudo apt-get install -y docker-ce
foo@bar:~$ sudo usermod -aG docker ${USER}
```
[Docker-compose](https://docs.docker.com/compose/overview/)

```console
foo@bar:~$ sudo curl -L https://github.com/docker/compose/releases/download/1.19.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
foo@bar:~$ sudo chmod +x /usr/local/bin/docker-compose
```
Usted puede clonar el proyecto directamente o hacer una bifurcación (fork), si desea contribuir al proyecto, recomendamos la bifurcación. Una vez que hemos bifurcado el proyecto en Minka, procedemos a clonarlo en nuestra computadora local, de preferencia, debemos usar el protocolo https:

Puede clonarlo en la carpeta que desee, pero si planea utilizar las [herramientas de desarrollo](https://minka.gob.ec/fabricadesoftwarelibre/libregob-desarrollo/), recomendamos mantener los patrones determinados en el arcihvo yml de desarrollo, así podrá trabajar sin necesidad de realizar cambios a los demás archivos.

```console
foo@bar:~$ mkdir -p ~/Repositorios/fabricadesoftwarelibre
foo@bar:~$ cd ~/Repositorios/fabricadesoftwarelibre
foo@bar:~$ git clone https://minka.gob.ec/suusuariodeminka/libregob.git
```

Y agregamos el repositorio upstream para poder mantenernos actualizados.

```console
foo@bar:~$ cd libregob
foo@bar:~$ git remote add upstream https://minka.gob.ec/fabricadesoftwarelibre/libregob.git
```

## Entorno de desarrollo.

Si hemos seguido los pasos de instalación de manera exacta, podrémos levantar nuestro entorno de desarrollo de la siguiente manera:

```console
foo@bar:~$ cd ~/Repositorios/fabricadesoftwarelibre/libregob-desarrollo
foo@bar:~$ docker-compose -f desarrollo.yml up
```

Al ejecutarlo, debemos esperar unos segundos hasta que el contenedor de la base de datos indíque que se encuentra lista y aceptando conexiones.

Podrémos acceder a nuestro nuevo entorno de desarrollo ingresando a la dirección `localhost:8069` en nuestro navegador, la contraseña del administrador, que nos permitirá crear, duplicar y modificar bases de datos es `libregob`

## Módulos.
### l10n_ec_sri

Este módulo es la base para la localización contable/tributaria de Ecuatori, se enfoca en cumplir con los requerimientos del Servicio de Rentas Internas, facilitando la tributación en Ecuador.