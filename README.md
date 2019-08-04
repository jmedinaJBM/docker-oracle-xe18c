[![][license img]][license]
<img src="images/Logo_v4.png" align="right" />

# Oracle18c-XE para OracleLinux7 en Docker

## Tabla de Contenido
- [I. Objetivo](#i-objetivo)
- [II. Requisitos](#ii-requisitos)
- [III. Consideraciones y Pre-Configuración](#iii-consideraciones-y-pre-configuración)



## I. Objetivo
Montar una Base de Datos Oracle18c XE en un Contenedor Oracle-Linux7

## II. Requisitos
1. Tener instalado [Linux Centos7][centos7] en una máquina virtual.
2. Tener instalado [Docker-CE][docker] en la MV Linux Centos7.
3. Tener instalado Git.
      ```
      $ su -
      $ yum install git
      ```
  4. Haber descargado el archivo de instalación en format RPM [oracle-database-xe-18c-1.0-1.x86_64.rpm][oracle].
  5. Espacio de almacenamiento requerido
      - 5.1- Al menos 8GB (Oracle recomienda 7680 MB) de espacio libre en **/opt** ; esta carpeta se ubica en el root folder **`/`** en la instalación    por defecto de Linux Centos7.
      - 5.2- Un Virtaul Disk de 20GB en el punto de montaje **/docker** ; montarlo después de haber instalado Linux Centos7 para evitar confusión.

## III. Consideraciones y Pre-Configuración
1. Tu máquina virtual Linux Centos7 es considerada la máquina host para efectos de esta guía.
2. Tu usuario Linux Centos 7 es el que se utiliza por defecto en esta guía a menos que se indique lo contrario.
3. Desactiva el firewall en Linux Centos 7.
4. Cambiar permisos a la carpeta **/docker**
      ```
      $ su -
      $ chmod 777 /docker
      ```
5. Crea las siguientes carpetas dentro de **/docker**
      ```
      $ cd /docker
      $ mkdir oracle_product
      $ mkdir ./oracle_product/18cxe
      $ mkdir ./oracle_product/18cxe/oradata
      ```
6. La carpeta de trabajo por defecto es /docker/oracle_product para efectos de esta guía.

[license img]:https://img.shields.io/badge/License-MIT-green.svg
[license]:https://github.com/jmedinaJBM/docker-oracle-xe18c/images/LICENSE
[centos7]:https://www.centos.org/download
[docker]:https://docs.docker.com/install/linux/docker-ce/centos
[oracle]:https://www.oracle.com/technetwork/database/database-technologies/express-edition/downloads/index.html
