# 1- INSTALAR APACHE
`sudo apt install apache2`
## 1.1- AJUSTE DEL CORTAFUEGOS
Primero solicitamos la información del perfil **Apache Full**
`sudo ufw app info "Apache Full"`
Para permitir el tráfico de entrada HTTP y HTTPS:
`sudo ufw allow in "Apache Full"`
## 1.2- COMPROBAR QUE TODO HA IDO BIEN
Ingresa en el navegador la dirección `http://localhost`

# 2- INSTALAR MYSQL
`sudo apt install mysql-server mysql-client`
## 2.1- ASEGURAR ACCESO A BASES DE DATOS (OPCIONAL)
`sudo mysql_secure_installation`
Preguntará si quieres configurar el conector de validación de contraseña **VALIDATE PASSWORD PLUGIN**
Si decimos Y nos pedirá un nivel de fuerza.
Independientemente del que escojamos nos dirá si es adecuada o no.
En las siguientes preguntas, responde siempre **y**

# 3- INSTALAR PHP
`sudo apt install php libapache2-mod-php php-mysql`
No olvides resetear el servidor Apache:
`sudo service apache2 restart`

# 4- INSTALAR PHPMYADMIN
`sudo apt install phpmyadmin php-mbstring php-gettext`
Esto te lanzará una serie de preguntas
* Selección del servidor, **apache2**
* Para la database, escoger la opción **dbconfig-common** con _yes_
* Escribir y confirmar la contraseña para acceder a phpMyadmin (luego hay que cambiarlo)
## 4.1 - HABILITAR EXTENSION mbstring
Dentro del directorio _/etc/apache2/conf-enabled/_
`sudo phpenmod mbstring`
Reiniciamos el servidor Apache
## 4.2 - CONFIGURACIÓN DEL ACCESO AL USUARIO ROOT
`sudo mysql`
Dentro debemos actualizar el usuario root con una nueva contraseña (debe ser fuerte)
`ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'jesus';`
Reseteamos los privilegios
`FLUSH PRIVILEGES;`
Salimos con _quit_
## 4.3 - CONFIGURACIÓN DEL ACCESO A UN NUEVO USUARIO
Al volver a entrar se nos requerirá una contraseña para el usuario root
`sudo mysql -u root -p`
Creamos un usuario foo con contraseña bar:
`CREATE USER 'foo'@'localhost' IDENTIFIED BY 'bar';`
Añadimos todos los privilegios
`GRANT ALL PRIVILEGES ON *.* TO 'foo'@'localhost' WITH GRANT OPTION;`

