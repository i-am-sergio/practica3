# Práctica 03:
# **Construcción Automática de Proyectos**

## ACTIVIDADES:
* Configurar la herramienta de construcción automática localmente o por medio de su IDE favorito.
* Crear un modelo (archivo de configuración) de construcción para el proyecto de software escogido. Este modelo debe describir la siguiente información:
  1. Información del proyecto: nombre, versión, tipo de archivo, ...
  2. Opciones de compilación: compilador, versión, ...
  3. Gestión de dependencias: Libs que hace uso el proyecto
* Construir el proyecto por medio del modelo creado.
* Visualizar resultados de construcción

## TUTORIAL
### Download JDK (JAVA 17) in Oracle:
[![image.png](https://i.postimg.cc/C5RvfkVc/image.png)](https://postimg.cc/PvkbgLJD)

* Installing JDK:

[![image-1.png](https://i.postimg.cc/SKKtpwv0/image-1.png)](https://postimg.cc/SnwG6t4V)

* Successfully installed JDK:
[![image.png](https://i.postimg.cc/TPyq0GsP/image.png)](https://postimg.cc/nsJDc8p8)

### Configure Your Environment variables:
'''
JAVA_HOME = C:\Program Files\Java\jdk-17 //(This could be another version of JDK)
MAVEN_HOME = C:\Program Files\Maven\apache-maven-3.9.4  //(This could be another version of Maven)
'''
Add to Path:
%JAVA_HOME%\bin
%MAVEN_HOME%\bin
