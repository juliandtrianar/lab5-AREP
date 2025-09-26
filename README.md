### link repositorio con las evidencias del Taller JPA y Workshop AWS-CLI ⬇️
https://github.com/juliandtrianar/TALLER_JPA_AREP.git
# lab5-AREP Taller de trabajo individual en patrones arquitecturales

# TALLER  SISTEMA CRUD PARA GESTIONAR PROPIEDADES

En este taller se elaboró una aplicación para gestionar propiedades inmobiliarias implementando un sistema CRUD para crear, listar, actualizar y eliminar dichas "entidades". Para su despliegue, se configuraron dos instancias EC2 en AWS. La primera instancia aloja el componente de Spring, que incluye tanto el backend como el frontend. Esta instancia se comunica con la segunda, donde está implementada la base de datos MySQL, logrando así una arquitectura distribuida. Adicionalmente, se realizaron las validaciones de campos, los respectivos filtros por precio, tamaño y dirección y los mensajes para el usuario de exito o error de las operaciones del CRUD.   

## Arquitectura

1. **Componente Spring (Backend + Frontend):**
   - El frontend está integrado en el mismo servidor que el backend y se comunica directamente con los controladores y servicios REST expuestos por el backend de Spring.
   - El backend, además de servir el frontend, maneja la lógica de negocio para realizar las operaciones CRUD, gestiona peticiones HTTP y usa los datos provenientes de la base de datos. Además, se utilizó el patrón de diseño arquitectónico **Modelo-Vista-Controlador**
2. **Componente MySQL (Base de datos):** 
   - Este componente es la base de datos MySQL implementado en un servidor diferente.
     El componente Spring se comunica con MySQL a través de una conexión de red utilizando Spring Data JPA para realizar operaciones de lectura y escritura en la base de datos.
## Empezando

### Requisitos Previos
Para ejecutar este proyecto, necesitarás tener instalado:

- Java JDK 17.
- Un IDE de Java como IntelliJ IDEA, Eclipse, o NetBeans.
- Maven para manejar las dependencias preferiblemente la version 3.9.4 
- Un navegador web para interactuar con el servidor.

### Instalación

1. Tener instalado Git en tu máquina local
2. Elegir una carpeta en donde guardes tu proyecto
3. abrir la terminal de GIT --> mediante el click derecho seleccionas Git bash here
4. Clona el repositorio en tu máquina local:

   ```
   git clone https://github.com/juliandtrianar/lab5-AREP.git
   ```
5. Navegue al directorio del proyecto:
  
6. **IMPORTANTE**: 
   - En application.properties tiene que cambiar el usuario en ***spring.datasource.username*** por root o por un usuario que tenga predefinido.
   - En **spring.datasource.password** cambié la contraseña por su contraseña de base de datos.
   - Finalmente, cambie su IP en **spring.datasource.url** por localhost o una específica como las de AWS y no olvide que la base se llama arep.
     
 ![image](https://github.com/user-attachments/assets/a907b6f3-0c1b-49e5-844e-3ddcc160f56c)


## Deployment
1. Abre los dos proyectos con tu IDE favorito o navega hasta el directorio del proyecto
2. Desde la terminal para compilar y empaquetar el proyecto ejecuta:

   ```bash
   mvn clean install
   ```
3.  Compila el proyecto que contiene el método MAIN: AccessingDataJpaApplication o ejecuta desde la terminal

   ```bash
   mvn spring-boot:run
   ```
Verá que el servidor está listo y corriendo sobre el puerto 8080

4. Puedes interactuar con los endpoints RESTful API con:
    - http://localhost:8080/agregar
    ![image](https://github.com/user-attachments/assets/6961704f-c0a2-4a89-910d-5f41f3eda0d0)

   


   
## Despliegue en AWS

- **Video**: https://drive.google.com/file/d/1DVoURH6xqVPzev-y4S5eKsQM0iKMV6ld/view?usp=sharing

## Built With
* [Maven](https://maven.apache.org/) - Dependency Management

## Authors

* **Julián David Triana Roa** 


## Built With
* [Maven](https://maven.apache.org/) - Dependency Management

## Authors

* **Julián David Triana Roa** 
