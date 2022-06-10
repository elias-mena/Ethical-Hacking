# Criptografía

## Tabla de contenido

1. [Hashes con Md5sum](#hashes-con-md5sum)

    1.1 [Ejemplo de uso de Md5sum](#ejemplo-de-uso-de-Md5sum)

    1.2 [Generar los hashes](#generar-los-hashes)

    1.3 [Verificar los hashes](#verificar-los-hashes)

2. [Hashes con Sha256sum](#hashes-con-sha256sum)
    
    2.1 [Crear hash](#crear-hash)
    
    2.2 [Verificar hash](#verificar-hash)

3. [Veracrypt](#veracrypt)

    3.1 [Instalación Veracrypt](#instalacion-veracrypt)

    3.2 [Crear volumen encriptado de archivos con AES y Ext4 como sistema de archivos](#crear-volumen-encriptado-de-archivos-con-aes-y-ext4-como-sistema-de-archivos)

    3.3 [Montar volumen y guardar archivos](#montar-volumen-y-guardar-archivos)

4. [Steghide](#steghide)

    4.1 [Instalación](#instalacion)

    4.2 [Incorporar archivo dentro de una imagen](#incorporar-archivo-dentro-de-una-imagen)

    4.3 [Extraer archivo de la imagen](#extraer-archivo-de-la-imagen)

---

## Hashes con Md5sum

Md5sum es un programa que realiza un hash MD5 de un archivo. La función de hash devuelve un valor que es prácticamente único para cada archivo, con la particularidad que una pequeña variación en el archivo provoca una salida totalmente distinta, lo que ayuda a detectar si el archivo sufrió alguna variación. Es una herramienta de seguridad que sirve para verificar la integridad de los datos.

---

### Ejemplo de uso de Md5sum

- Crear 5 archivos de texto e incluir contenido.

![Untitled](Images/Untitled%201.png)

### Generar los hashes

***`md5sum file1.txt file2.txt file3.txt file4.txt file5.txt > hashes`***

[Volver al inicio⬆](#tabla-de-contenido)

---

### Verificar los hashes

***`md5sum --check hashes`***

![Untitled](Images/Untitled%202.png)

[Volver al inicio⬆](#tabla-de-contenido)

---

## Hashes con **sha256sum**

### Crear hash

`sha256sum archivo.txt > archivo.txt.sha256`

![Untitled](Images/Untitled%203.png)

[Volver al inicio⬆](#tabla-de-contenido)

---

### Verificar hash

`sha256sum -c archivo.txt.sha256`

![Untitled](Images/Untitled%204.png)


[Volver al inicio⬆](#tabla-de-contenido)

---

## **Veracrypt**

*VeraCrypt es una aplicación informática gratuita que sirve para realizar cifrado de disco, empleando para ello diferentes algoritmos de cifrado como: AES, Serpent y Twofish, o una combinación de los mismos. Permite crear un volumen virtual cifrado en un archivo o en una partición o bien (en Windows, Linux) cifrar un dispositivo de almacenamiento entero con autenticación previa al arranque.*

---

### Instalación Veracrypt

```bash
// Luego de correr los comandos buscamos la app en el menu principal
sudo apt install libwxgtk3.0-gtk3-0v5 libwxbase3.0-0v5
wget https://launchpad.net/veracrypt/trunk/1.24-update7/+download/veracrypt-1.24-Update7-Ubuntu-20.04-amd64.deb
sudo dpkg -i veracrypt-1.24-Update7-Ubuntu-20.04-amd64.deb
```

[Volver al inicio⬆](#tabla-de-contenido)

---

### Crear volumen encriptado de archivos con AES y Ext4 como sistema de archivos

![Untitled](Images/Untitled%205.png)

![Untitled](Images/Untitled%206.png)

![Untitled](Images/Untitled%207.png)

Antes de este paso debemos crear un archivo vació en alguna parte de la computadora, para luego buscarlo y sobre este crear el volumen encriptado, luego lo seleccionamos buscando su ruta en esta ventana.

![Untitled](Images/Untitled%208.png)

![Untitled](Images/Untitled%209.png)

![Untitled](Images/Untitled%2010.png)

![Untitled](Images/Untitled%2011.png)

![Untitled](Images/Untitled%2012.png)

![Untitled](Images/Untitled%2013.png)

![Untitled](Images/Untitled%2014.png)

![Untitled](Images/Untitled%2015.png)

![Untitled](Images/Untitled%2016.png)

[Volver al inicio⬆](#tabla-de-contenido)

---

### **Montar volumen y guardar archivos**

En este paso debemos buscar el archivo sobre el que creamos el volumen, luego que lo buscamos y seleccionamos, damos click en “Mount”.

![Untitled](Images/Untitled%2017.png)

![Untitled](Images/Untitled%2018.png)

Una vez montado el volumen se puede acceder a este buscándolo en el directorio donde lo creamos y luego ejecutando el comando **lsblk** 
en la terminal para ver su ruta, una vez acá podemos crear y almacenar todo tipo de archivos dentro del volumen.

![Untitled](Images/Untitled%2019.png)

![Untitled](Images/Untitled%2020.png)

[Volver al inicio⬆](#tabla-de-contenido)

---

## **Steghide**

*Steghide es un programa de **esteganografía** que puede ocultar datos en varios tipos de archivos de imagen y audio. Sus características incluyen el compactado y el encriptado de los datos adjuntos, y revisión automática de integridad usando  un  checksum. Se reconocen los formatos de archivo JPEG, BMP, WAV y AU para usar como archivos de portada. No existen  restricciones en el formato de los datos ocultos*

---

### Instalación

***`sudo apt install steghide`***


[Volver al inicio⬆](#tabla-de-contenido)

---

### Incorporar archivo dentro de una imagen

**`steghide embed -cf imagen.jpg -ef secreto.txt`**

Funciona con varios tipos de archivos, podriamos ocultar un audio en la foto por ejemplo.

![Untitled](Images/Untitled%2021.png)

[Volver al inicio⬆](#tabla-de-contenido)

---

### Extraer archivo de la imagen

**`steghide extract -sf imagen.jpg`**

![Untitled](Images/Untitled%2022.png)

[Volver al inicio⬆](#tabla-de-contenido)

---