# LibreGOB


LibreGOB es un Planificador de Recursos Gubernamentales (GRP) basado en <a href="https://www.odoo.com">Odoo</a>, esta diseñado para funcionar en cualquier equipo que permita utilizar una versión de docker superior o igual a 17.6, las pruebas se realizan sobre Ubuntu 16.04, concretamente sobre [Microwatt OS v10](http://planetwatt.com/new/index.php/downloads/). La compatibilidad con entornos Windows o distribuciones distintas no está garantizada y no se receptarán correcciones de errores para estas plataformas.

Usted puede clonar el proyecto directamente o hacer una bifurcación (fork), si desea contribuir al proyecto, recomendamos la bifurcación.

Una vez que hemos bifurcado el proyecto en Minka, procedemos a clonarlo en nuestra computadora local, de preferencia, debemos usar el protocolo https:

Puede clonarlo en la carpeta que desea, pero si planea utilizar las [herramientas de desarrollo](https://minka.gob.ec/fabricadesoftwarelibre/libregob-desarrollo/), recomendamos mantener los patrones determinados en el arcihvo yml de desarrollo, así podrá trabajar sin necesidad de realizar cambios a los demás archivos.

```
cd ~
mkdir -p /Repositorios/fabricadesoftwarelibre
cd Repositorios/fabricadesoftwarelibre
git clone https://minka.gob.ec/suusuariodeminka/libregob.git
```

Y agregamos el repositorio upstream para poder mantenernos actualizados.

```
cd libregob
git remote add upstream https://minka.gob.ec/fabricadesoftwarelibre/libregob.git
```

Los módulos adicionales a Odoo estándar, implementados por el proyecto LibreGOB, se encuentran en la carpeta `libregob-addons`, los principales son:

## l10n_ec_sri

Este módulo es la base para la localización contable/tributaria de Ecuatori, se enfoca en cumplir con los requerimientos del Servicio de Rentas Internas, facilitando la tributación en Ecuador.
