# Instalar Apache Maven con apt


 Instalar Maven en Ubuntu usando apt es un proceso simple y directo.

 Actualice el índice del paquete e instale Maven ingresando los siguientes comandos:

```
 sudo apt update
```
```
 sudo apt install maven
 
```

 <img src="imagenes/Maven 1.png" alt="Maven 1">
 
 Para verificar la instalación, ejecute mvn -version:
```
 mvn -version
```
<img src="imagenes/Maven 1.1.png" alt="Maven 1.1">

Comprobamos que tenemos el Maven instalado y la versión del mismo.  


### Instalar una versión concreta de Apache Maven

 En el momento de escribir este artículo, es la última versión de Apache Maven 3.8.2. Antes de continuar con el siguiente paso, visite la página de descarga de Maven para ver si hay una versión más nueva disponible.


 Descargue Apache Maven en el directorio /tmp:

```
wget https://www.apache.org/dist/maven/maven-3/3.8.2/binaries/apache-maven-3.8.2-bin.tar.gz -P /tmp
```


<img src="imagenes/Maven 2.png" alt="Maven 2">


 Una vez que se complete la descarga, extraiga el archivo en el directorio /opt
```
sudo tar xf /tmp/apache-maven-*.tar.gz -C /opt
```
 Para tener más control sobre las versiones y actualizaciones de Maven, que a crear un maven enlace simbólico que apunte al directorio de instalación de Maven:

```
sudo ln -s /opt/apache-maven-3.8.2 /opt/maven
```

<img src="imagenes/Maven 3.png" alt="Maven 3">


__Establecer variables de entorno__
 A continuación, necesitaremos establecer las variables de entorno. Para hacer esto, abra su editor de texto y cree un nuevo archivo llamado mavenenv.sh en el directorio /etc/profile.d/
```
sudo nano /etc/profile.d/maven.sh
```
Pega el siguiente código:

```
 export M2_HOME=/opt/maven
 export MAVEN_HOME=/opt/maven
 export PATH=${M2_HOME}/bin:${PATH}
```

 Guarde y cierre el archivo. Este script se utilizará al iniciar el shell.
 
 <img src="imagenes/Maven 4.png" alt="Maven 4">
 
 Ejecutamos el código anterior, guardamos y salimos. 

 
 Haga que el script sea ejecutable con chmod:

```
 sudo chmod +x /etc/profile.d/maven.sh
```
 Finalmente, cargue las variables de entorno usando el comando de source
```
 source /etc/profile.d/maven.sh
```

<img src="imagenes/Maven 5.png" alt="Maven 5">


__Verificar la instalación__

Para verificar que Maven está instalado, use el mvn -version que imprimirá la versión de Maven:

```
mvn -version
```

<img src="imagenes/Maven 5.png" alt="Maven 5">

Verificamos que Maven está instalado en la versión 3.8.2 

[Pagina principal](https://github.com/OscarDavid87/ETS-Entornos-de-desarrollo/blob/main/README.md)

