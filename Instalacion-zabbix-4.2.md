# Instalacion de zabbix 4.2 en Rhel 7.6 <h5>

> instalar un software libre de monitoreo en un equipo linux

__# yum install httpd__ =  Installar apache con el comando anterior
     = paquetes necesarios de php
   __# vim /e tc/php.ini__ = modificar archivo
     
     * # max_execution_time = 600 
     
     * #max_input_time = 600 
     
     * #memory_limit = 256M 
post_max_size = 32M 
upload_max_filesize = 16M 
date.timezone = Asia / Jakarta
    * # systemctl enable httpd 
    * # systemctl start hhtpd
__# rpm -Uvh  https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm__ = Agregar el repositorio de epel para instalarlo

    * # yum -y install epel-release
    
__# rpm -Uvh https://mirror.webtatic.com/yum/el7/webtatic-release.rpm__ = paquete de php 7
    
    * # yum -y install mod_php72w php72w-cli php72w-common php72w-devel php72w-pear php72w-gd php72w-mbstring php72w-mysql php72w-xml php72w-bcmath = paquetes necesarios de php
    
__# vim /etc/php.ini__ = modificar archivo
     
     * # max_execution_time = 600 
     
     * #max_input_time = 600 
     
     * #memory_limit = 256M 

     * #post_max_size = 32M 

     * #upload_max_filesize = 16M 
     
     * #date.timezone = America/Mexico_City 

__# rpm -ivh https://repo.zabbix.com/zabbix/4.2/rhel/7/x86_64/zabbix-release-4.2-1.el7.noarch.rpm__ = Agragar el repositorio de zabbix

__#yum install mariadb-server__ = instalar el gestor de base de datos que en esta ocasion va a ser mariadb
     
      * # systemctl start mariadb
      
      * # systemctl enable mariadb
      
      * # systemctl status mariadb
      
      * # mysql_secure_installation = paracolocar la contraseña del usuario con el que se va usar la base de datos
      
__# mysql -u root -p__ = para ingresar a la base de datos no va a pedir la contraseña que metimos en la seccion anterior

       * #create database zabbix; 
       
       * # grant all privileges on zabbix.* to zabbix@'localhost' identified by 'redhat'; 
       
       * # grant all privileges on zabbix.* to zabbix@'%' identified by 'redhat'; 
       
       * # flush privileges;
 
       *#Pasos para crear la base de datos#*
       
 __# yum install zabbix-server-mysql zabbix-proxy-mysql zabbix-web-mysql zabbix-get zabbix-agent__ = instalar zabbix
      


























