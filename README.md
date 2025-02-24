# StudyCiclos

Aquí tienes un `README.md` listo para que lo agregues a tu repositorio en GitHub. Explica paso a paso cómo configurar **Maven**, agregar **Spring Boot**, **JUnit 5**, y **JaCoCo**, y cómo ejecutar pruebas y generar reportes de cobertura. 🚀  

---  

## **README.md**  
```md
# 🚀 Proyecto Maven con Spring Boot, JUnit 5 y JaCoCo

Este repositorio contiene un proyecto Maven configurado con **Spring Boot**, **JUnit 5** y **JaCoCo**.  
Incluye pasos detallados para su instalación, configuración y ejecución.

---

## 📌 **1. Prerrequisitos**
Antes de comenzar, asegúrate de tener instalados:
- **Java JDK 17 o superior** → [Descargar JDK](https://adoptium.net/)
- **Apache Maven** → [Descargar Maven](https://maven.apache.org/download.cgi)
- **Git** → [Descargar Git](https://git-scm.com/downloads)

Para verificar la instalación, ejecuta en la terminal:
```sh
java -version
mvn -version
git --version
```
Si los comandos no son reconocidos, agrega las rutas de **Java** y **Maven** a la variable de entorno `PATH`.

---

## ⚙ **2. Crear y Configurar un Proyecto Maven**
1. Abre una terminal y ejecuta el siguiente comando para crear un nuevo proyecto:
   ```sh
   mvn archetype:generate -DgroupId=com.ejemplo -DartifactId=mi-proyecto -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
   ```
2. Ingresa a la carpeta del proyecto:
   ```sh
   cd mi-proyecto
   ```
3. Abre el archivo `pom.xml` y reemplázalo con la siguiente configuración:

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.ejemplo</groupId>
    <artifactId>mi-proyecto</artifactId>
    <version>1.0-SNAPSHOT</version>

    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>3.2.2</version>
        <relativePath/>
    </parent>

    <dependencies>
        <!-- Spring Boot -->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter</artifactId>
        </dependency>

        <!-- JUnit 5 -->
        <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter-api</artifactId>
            <scope>test</scope>
        </dependency>

        <!-- Dependencias para pruebas con Spring Boot -->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
        </dependency>
    </dependencies>

    <build>
        <plugins>
            <!-- Plugin para ejecutar pruebas -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-surefire-plugin</artifactId>
                <version>3.0.0-M7</version>
            </plugin>

            <!-- Plugin JaCoCo para reportes de cobertura -->
            <plugin>
                <groupId>org.jacoco</groupId>
                <artifactId>jacoco-maven-plugin</artifactId>
                <version>0.8.10</version>
                <executions>
                    <execution>
                        <goals>
                            <goal>prepare-agent</goal>
                        </goals>
                    </execution>
                    <execution>
                        <id>report</id>
                        <phase>verify</phase>
                        <goals>
                            <goal>report</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
        </plugins>
    </build>
</project>
```

---

## 🛠 **3. Configurar Git y Subir el Proyecto a GitHub**
1. Crea un repositorio en GitHub sin inicializarlo con README ni `.gitignore`.
2. Abre una terminal en la carpeta del proyecto y ejecuta:
   ```sh
   git init
   git remote add origin https://github.com/TuUsuario/mi-proyecto-maven.git
   ```
3. Agrega y sube el código al repositorio:
   ```sh
   git add .
   git commit -m "Subiendo proyecto Maven con Spring Boot, JUnit 5 y JaCoCo"
   git branch -M main
   git push -u origin main
   ```

---

## 🧪 **4. Ejecutar Pruebas con JUnit 5**
Para ejecutar pruebas unitarias con JUnit 5, usa:
```sh
mvn test
```

---

## 📊 **5. Generar Reporte de Cobertura con JaCoCo**
Para generar un reporte de cobertura de código con **JaCoCo**, usa:
```sh
mvn verify
```
Esto generará un reporte en:
```
target/site/jacoco/index.html
```
Para verlo, abre `index.html` en un navegador.

---

## 🎯 **6. Ejecutar la Aplicación Spring Boot**
Si el proyecto tiene una clase principal con `@SpringBootApplication`, ejecuta:
```sh
mvn spring-boot:run
```

---

## ✅ **7. Verificar que Todo Funciona**
1. **Compilar y construir el proyecto**:
   ```sh
   mvn clean install
   ```
2. **Ejecutar pruebas unitarias**:
   ```sh
   mvn test
   ```
3. **Generar reporte de cobertura con JaCoCo**:
   ```sh
   mvn verify
   ```

---

## 📝 **8. Notas Finales**
- Si GitHub solicita autenticación al hacer `git push`, usa un **token personal** en lugar de la contraseña. Puedes generarlo en:
  👉 [https://github.com/settings/tokens](https://github.com/settings/tokens)
- Para evitar subir archivos innecesarios, crea un archivo `.gitignore` en la raíz del proyecto con este contenido:
  ```
  target/
  .idea/
  .classpath
  .project
  .settings/
  *.iml
  ```
- Si necesitas actualizar dependencias en `pom.xml`, ejecuta:
  ```sh
  mvn dependency:tree
  ```

🚀 **¡Listo! Ahora tienes un proyecto Maven con Spring Boot, JUnit 5 y JaCoCo completamente funcional.**
```

---

Este `README.md` cubre **todo lo que aprendiste paso a paso**, sin omitir nada. Solo cambia `TuUsuario` por tu usuario de GitHub antes de subirlo. 😃
