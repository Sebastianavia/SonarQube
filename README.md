# SonarQube

<p align="justify">SonarQube es una plataforma de código abierto diseñada para ayudar a los equipos de desarrollo de software a mejorar la calidad de su código fuente. Proporciona una variedad de herramientas y funciones para realizar análisis automáticos del código, identificar problemas de calidad, errores, vulnerabilidades de seguridad y áreas de mejora.</p>

[SonarQube](https://docs.sonarsource.com/sonarqube/latest/)

---

## Implementación

En esta ocasión usaremos Docker compose para ejecutar sonarqube (El archivo YAML esta en el repositorio).



<p align="justify">
Este archivo YAML define dos servicios Docker, SonarQube y una base de datos PostgreSQL, configurados para ejecutarse en una red interna llamada "sonarnet", donde SonarQube se conecta a la base de datos utilizando variables de entorno para la URL JDBC y las credenciales. Además, se definen volúmenes para persistir los datos de SonarQube y PostgreSQL entre reinicios de contenedores.
</p>

Ejecutaremos docker compose up para levantar los contenedores.

    docker compose up

---


<p align="center">
  <img src="https://github.com/Sebastianavia/SonarQube/assets/71205906/38b2504d-456c-43ed-989f-805b2c5f552e" width="380">
</p>

---
<p align="center">
Contenedores:
</p>

![image](https://github.com/Sebastianavia/SonarQube/assets/71205906/ebace205-5a5e-4a25-96aa-352613f61656)

---

Ingresamos a SonarQube a través de la URL `localhost:9000`. Las credenciales de autenticación predeterminadas son:
- **Usuario:** admin
- **Contraseña:** admin

---
<p align="center">
  <img src="https://github.com/Sebastianavia/SonarQube/assets/71205906/7e7a7f24-7cad-401c-8585-4056d8ee4fce"width="350">
</p>

---

- Crear un peoyecto local


<p align="center">
  <img src="https://github.com/Sebastianavia/SonarQube/assets/71205906/ea448e0e-7570-465f-9aae-ca960e881f70" width="380">
</p>

---

<p align="justify">
Primero, necesitas asignar un nombre al proyecto, así como una clave única que lo identifique. Además, debes definir cuál será la rama principal del proyecto, ya que esta rama será la que se revise en las evaluaciones posteriores.

Una vez hecho esto, puedes utilizar la configuración global predeterminada para el proyecto. Esto significa que se utilizarán los ajustes generales que vienen por defecto.

Después, debes elegir el método de análisis local para el proyecto. Esto implica que el análisis del código se realizará en el entorno local, es decir, en tu propio equipo, en lugar de en un servidor remoto o en la nube.
</p>

---


<p align="center">
  <img src="https://github.com/Sebastianavia/SonarQube/assets/71205906/bd598861-3355-494e-b453-abdd6f43d016" width="380">
</p>



<p align="center">
  <img src=https://github.com/Sebastianavia/SonarQube/assets/71205906/7aec9a73-297d-458e-878e-05cafd7bd061
  width="380">
</p>

---

<p align="justify">
Necesitamos crear un token de autenticación que se utilizará para realizar los análisis de código del proyecto. Este token servirá como una forma segura de autenticar y autorizar los análisis que se realizarán en SonarQube.
</p>

<p align="center">
  <img src=
https://github.com/Sebastianavia/SonarQube/assets/71205906/0b90ef81-cc6a-4979-93fb-fb8f195a2a76
width="380">
</p>

<p align="center">
  <img src=
https://github.com/Sebastianavia/SonarQube/assets/71205906/6e5cc8fe-1c79-4e3c-b469-72b9a2973f92
width="380">
</p>


<p align="center">
  <img src=
https://github.com/Sebastianavia/SonarQube/assets/71205906/51db8673-d0a6-4a55-b3f3-74dfbad3aac4
width="380">
</p>

---

Antes de continuar, necesitamos instalar Sonar-Scanner.

<p align="justify">
- Necesitamos obtener el archivo comprimido que contiene la última versión del Sonar-Scanner. Una vez que lo tengamos, lo extraemos para acceder a los archivos y carpetas que contiene. Este paso nos permitirá preparar el Sonar-Scanner para su uso posterior en nuestros análisis de código.
</p>

Puede que necesites...

    sudo apt install wget
    sudo apt install unzip


- En esta pagina encontraras el paso a paso para instalarlo y configurarlo.

https://docs.sonarsource.com/sonarqube/10.5/analyzing-source-code/scanners/sonarscanner/

<p align="center">
  <img src=
https://github.com/Sebastianavia/SonarQube/assets/71205906/fe76d3ba-3f84-42ee-9305-0844fe7b5c95
width="380">
</p>


<p align="justify">
Dirígete al directorio principal de tu proyecto y ejecuta el escáner. Después de esto, espera a que el escáner complete las verificaciones y el análisis del código. Una vez que el análisis esté completo, recarga la página del dashboard en SonarQube para ver los resultados del análisis y cualquier problema identificado en el código.
</p>

    sonar-scanner \

- Este comando escanea el código.


<p align="center">
  <img src=https://github.com/Sebastianavia/SonarQube/assets/71205906/1740b1a8-6663-4676-b255-fbe96cb5b169
  width="400">
</p>

---

<p align="justify">
Una vez finalizado el análisis del código, podrás ver los resultados en el panel de control de SonarQube. Aquí encontrarás un resumen de la calidad del código, que incluye métricas como la cantidad de problemas detectados, la cobertura del código, la duplicación y la complejidad.
</p>


<p align="center">
  <img src=
https://github.com/Sebastianavia/SonarQube/assets/71205906/15b4ecea-67c2-4613-978a-3ab0280b5a76
width="400">
</p>
