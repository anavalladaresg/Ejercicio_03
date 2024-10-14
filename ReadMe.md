# Ejercicio 2  
**Ana Valladares González**

## 1. Descargamos la imagen 'httpd' de Apache, tag 2.4 y verificamos su presencia en el equipo

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
