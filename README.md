# LibreGOB

## Generalidades e instalación.
LibreGOB es un Planificador de Recursos Gubernamentales (GRP) basado en <a href="https://www.odoo.com">Odoo</a>, esta diseñado para funcionar en cualquier equipo que permita utilizar una versión de docker superior o igual a 17.6, las pruebas se realizan sobre [Ubuntu 16.04 LTS](https://www.ubuntu.com/download/desktop/contribute?version=16.04.4&architecture=amd64), concretamente sobre [Microwatt OS v10](http://planetwatt.com/new/index.php/downloads/), por lo tanto, la presente guía y toda la documentación se basa en este entorno de trabajo. La compatibilidad con entornos Windows o distribuciones distintas no está garantizada y no se receptarán correcciones de errores para estas plataformas.

Una vez que hemos instalado uno de los sistemas operativos soportados, procedemos a instalar las dependencias, a continuación ejemplificamos la forma más sencilla de instalación, si desea información más completa o actualizada, puede remitirse a las guías oficiales de cada aplicativo:

Instalamos las dependencias:

[Git](https://git-scm.com/)

```console
foo@bar:~$ apt install git
```

Configuramos git.

```console
foo@bar:~$ git config --global user.name "Nombre de su usario de Minka"
foo@bar:~$ git config --global user.email correodelusuariode@minka.gob.ec
foo@bar:~$ git config --global push.default simple
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

El proyecto LibreGOB aporta varias herramientas para que nuestra curva de aprendizaje sea corta y podamos empezar a trabajar de manera rápida con nuestro sistema, para conocer sobre ellas, visíte el repositorio [libregob-desarrollo](https://minka.gob.ec/fabricadesoftwarelibre/libregob-desarrollo/).

## Editor de texto.

Para mejorar la eficiencia de nuestro desarrollo y facilitar el trabajo de nuestros colaboradores hemos creado [libregob-nvim](https://minka.gob.ec/fabricadesoftwarelibre/libregob-nvim). Este proyecto nos permite tener un editor de texto eficiente y ágil, con atajos que nos permiten trabajar en nuestros archivos de python y xml de manera sencilla. Está basado en [NeoVim](https://neovim.io/).

## Módulos.
### l10n_ec_sri

Este módulo es la base para la localización contable/tributaria de Ecuatori, se enfoca en cumplir con los requerimientos del Servicio de Rentas Internas, facilitando la tributación en Ecuador.

### l10n_ec_sri_rce

Este módulo permite importar datos de los documentos electrónicos recibidos, como la fecha, el número de autorización, establecimiento, punto de emisión, entre otros.

### l10n_ec_hr_payroll

Este módulo contiene las reglas y estructuras salariales, así como otras modificaciones que que permiten realizar el cálculo de la nómina en base a la legislación ecuatoriana.

Contiene la reglas salariales para:

1. Décimo tercera remuneración.
2. Décimo cuarta remuneración.
3. Provisión de vacaciones.
4. Aporte personal y patronal al IESS.


