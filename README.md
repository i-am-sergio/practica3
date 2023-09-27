# Práctica 03: Construcción Automática de Proyectos

## TUTORIAL

### Descargar JDK (JAVA 17) de Oracle:
[![image.png](https://i.postimg.cc/C5RvfkVc/image.png)](https://postimg.cc/PvkbgLJD)

* Instalación de JDK:

[![image-1.png](https://i.postimg.cc/SKKtpwv0/image-1.png)](https://postimg.cc/SnwG6t4V)

* Instalación exitosa de JDK:

[![image.png](https://i.postimg.cc/TPyq0GsP/image.png)](https://postimg.cc/nsJDc8p8)

### Descargar Dependency Manager MAVEN:
Descargue Maven Manager en Binary zip en `https://maven.apache.org/download.cgi` y coloque el archivo extraido en su disco local `C:\Program Files\Maven`.

[![image.png](https://i.postimg.cc/L5982tG0/image.png)](https://postimg.cc/34qTZv8g)

### Configurar las variables de entorno:
JAVA_HOME = `C:\Program Files\Java\jdk-17` //(Esto podría ser otra versión de JDK)

MAVEN_HOME = `C:\Program Files\Maven\apache-maven-3.9.4` //(Esto podría ser otra versión de Maven)

Agregar a la variable Path: `%JAVA_HOME%\bin` `%MAVEN_HOME%\bin`

[![variables-entorno.png](https://i.postimg.cc/NjXR2b2y/variables-entorno.png)](https://postimg.cc/DS2StrgF)

### Instalar extensiones de Visual Studio Code:
- Spring Initializer Java Support (Para agregar dependencias a su proyecto)

[![image-2.png](https://i.postimg.cc/RCkvgTbQ/image-2.png)](https://postimg.cc/t7z0TFbY)

[![image-2.png](https://i.postimg.cc/RZR9VxCX/image-2.png)](https://postimg.cc/cvrPXjnn)

[![spring2.png](https://i.postimg.cc/rscQp3wN/spring2.png)](https://postimg.cc/xJxKxsHX)

[![image-2.png](https://i.postimg.cc/fLQvHpmQ/image-2.png)](https://postimg.cc/VS4Mv7KK)

[![image-2.png](https://i.postimg.cc/9XpBpxfs/image-2.png)](https://postimg.cc/bdZbY9kR)

- Language Support for Java

[![image-2.png](https://i.postimg.cc/Bvpvy11Z/image-2.png)](https://postimg.cc/t11ynJ58)

## Aplicación del Dependency Manager (Maven) en un Proyecto

### Ejecución del Proyecto

Para ejecutar nuestro proyecto, utilizamos el comando `mvn spring-boot:run`. A continuación, se detalla el proceso:

1. Ejecuta el comando `mvn spring-boot:run` en la terminal de tu sistema.

[![image.png](https://i.postimg.cc/NM2WX3Yh/image.png)](https://postimg.cc/5Y17dk6p)

2. El proyecto se ejecutará y estará disponible en `http://localhost:8080/`.

[![image-1.png](https://i.postimg.cc/qvjVHcQF/image-1.png)](https://postimg.cc/zybPngsw)

3. Al acceder a `http://localhost:8080/`, verás el mensaje "Hola Mundo!" que confirma que el proyecto se ha ejecutado correctamente.

[![spring2.png](https://i.postimg.cc/qq4Hdmf9/spring2.png)](https://postimg.cc/Pp3RWQ54)


## Archivo: pom.xml [Link](pom.xml)

1. `<project>`: Esta etiqueta raíz engloba todo el archivo POM y define el espacio de nombres predeterminado para las etiquetas dentro de este archivo. También contiene un atributo `xmlns:xsi` que se utiliza para definir el esquema XML y la ubicación del esquema.
	```xml
	<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
	.
	.
	.
	</project>
	```

2. `<modelVersion>`: Esta etiqueta especifica la versión del modelo POM utilizado en el archivo. La versión 4.0.0 es la más comúnmente utilizada en Maven.
	```xml
	<modelVersion>4.0.0</modelVersion>
	```

3. `<parent>`: Esta sección define el proyecto padre del proyecto actual. En este caso, el proyecto padre es `spring-boot-starter-parent`, que proporciona configuraciones y dependencias comunes para proyectos de Spring Boot. Incluye información como el `groupId`, `artifactId`, `version`, y `<relativePath>`, que se utiliza para buscar el proyecto padre en el repositorio local o remoto.
	```xml
	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>3.1.4</version>
		<relativePath/> <!-- lookup parent from repository -->
	</parent>
	```

4. `<groupId>`: Esta etiqueta especifica el identificador de grupo del proyecto. En este caso, el grupo es `com.unsa`.
	```xml
	<groupId>com.unsa</groupId>
	```

5. `<artifactId>`: Esta etiqueta especifica el identificador del artefacto (nombre del proyecto). Aquí, el artefacto se llama `proyecto1`.
	```xml
	<artifactId>proyecto1</artifactId>
	```

6. `<version>`: Define la versión del proyecto. En este caso, la versión es `0.0.1-SNAPSHOT`.
	```xml
	<version>0.0.1-SNAPSHOT</version>
	```

7. `<packaging>`: Especifica el tipo de archivo generado por el proyecto. En este caso, el tipo es `war`, que indica que se generará un archivo WAR (Web Application Archive).
	```xml
	<packaging>war</packaging>
	```

8. `<name>`: Proporciona un nombre descriptivo para el proyecto. En este caso, el nombre es `proyecto1`.
	```xml
	<name>proyecto1</name>
	```

9. `<description>`: Ofrece una descripción breve del proyecto. Aquí, se indica que es un proyecto de demostración para Spring Boot.
	```xml
	<description>Demo project for Spring Boot</description>
	```

10. `<properties>`: Esta sección permite definir propiedades personalizadas que se pueden utilizar en otros lugares del archivo POM. Aquí, se establece la versión de Java utilizada en el proyecto en `java.version`.
	```xml
	<properties>
		<java.version>17</java.version>
	</properties>
	```
11. `<dependencies>`: Esta sección define las dependencias del proyecto, es decir, las bibliotecas y módulos que el proyecto necesita para funcionar. En este caso, se incluyen dependencias de Spring Boot para la web y las pruebas.
	```xml
	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-data-jpa</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>

		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-tomcat</artifactId>
			<scope>provided</scope>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
			<scope>test</scope>
		</dependency>
	</dependencies>
	```

12. `<build>`: Esta sección define la configuración de construcción del proyecto. En este caso, se configura el plugin `spring-boot-maven-plugin` que se utiliza para construir proyectos de Spring Boot.
	```xml
	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>
	```