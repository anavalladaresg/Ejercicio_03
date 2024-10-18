# Ejercicio 2  
**Ana Valladares González**

## 1. Descargamos la imagen 'httpd' de Apache, tag 2.4 y verificamos su presencia en el equipo.

Descargamos la imagen de Docker "httpd" de Apache, con la etiqueta 2.4, sin ejecutarla, utilizando el comando `docker pull`. Comprobamos que la imagen ha sido descargada correctamente al listar las imágenes disponibles.

**Comandos utilizados:**  
```bash 
docker pull httpd:2.4
```
```bash
docker images
```

## 2. Creamos un contenedor con el nombre 'dam_web1'.

Creamos un contenedor a partir de la imagen `httpd:2.4` asignándole el nombre `dam_web1`. Para verificar si está en ejecución y obtener el nombre automáticamente asignado, usamos el comando `ps`.

**Comandos utilizados:**
```bash
docker run -d --name dam_web1 httpd:2.4
```
```bash
docker ps -a
```

## 3. Si queremos poder acceder desde el navegador de el equipo, ¿que debemos hacer? Utilizamos bind mount para que el directorio del apache2 'htdocs' esté montado un directorio que elijamos.

Mapeamos el puerto del contenedor al puerto del host con `-p` y montamos el directorio `htdocs` del servidor web en un directorio del host con `-v`.

**Comandos utilizados:**
```bash
docker run -d --name dam_web1 -p 8080:80 -v ~/mi-web:/usr/local/apache2/htdocs httpd
```

## 4. Realizamos un 'hola mundo' en html y comprobamos que accedemos desde el navegador.

Creamos un archivo `index.html` en el directorio `htdocs` del host con el contenido "Hola Mundo". Accedemos a `localhost:8080` desde el navegador y verificamos que muestra "Hola Mundo".

**Comandos utilizados:**
```bash
echo "Hola Mundo" > ~/mi-web:/usr/local/apache2/htdocs httpd
```
```bash
http://localhost:8080
```