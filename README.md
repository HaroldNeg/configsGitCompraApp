CompraApp - Configs Git
========================

Este repositorio contiene los archivos de configuración para los diferentes componentes del sistema CompraApp. 
Su objetivo es centralizar y facilitar la gestión de configuraciones de los microservicios y del frontend Angular.

Descripción del Proyecto
-------------------------
CompraApp está compuesto por varios microservicios backend y un frontend moderno en Angular.

Componentes incluidos:
- config-server
- eureka-server
- gateway-server
- productos-service
- inventario-service
- compras-app (frontend Angular)

Tecnologías utilizadas
-----------------------
- Java 21
- Spring Boot 3.5.3
- Spring Cloud 2025.0.0
- Angular 20.1.0
- Node.js 22.17.0
- NPM 11.4.2

Arquitectura General
---------------------
El sistema está basado en microservicios:

[ Angular ] --> [ Gateway Server ] --> [ Eureka / Config / Servicios (Productos, Inventario) ]

- Los microservicios están registrados en Eureka y config-server maneja la configuración centralizada.
- El gateway-server enruta las peticiones al servicio correspondiente.
- inventario-service se comunica con productos-service mediante FeignClient.

Ejecución y Configuración
--------------------------
1. Clonar el repositorio:
   git clone https://github.com/HaroldNeg/configsGitCompraApp.git

2. Configurar las propiedades en application.yml o bootstrap.yml según el entorno (dev/prod).

3. Iniciar los servicios en este orden:
   - config-server
   - eureka-server
   - gateway-server
   - productos-service
   - inventario-service

4. Ejecutar Angular en el frontend:
   cd compras-app
   npm install
   ng serve

Seguridad
---------
- Endpoints protegidos mediante autenticación (por ejemplo JWT u OAuth2).
- Encriptación de datos sensibles.
- Validación de entradas para prevenir ataques comunes como inyección SQL o XSS.

Observabilidad
--------------
Se recomienda integrar herramientas como:
- Prometheus + Grafana para métricas.
- Spring Cloud Sleuth + Zipkin para trazabilidad.

Estructura del Repositorio
---------------------------
/
├── config-server/
├── eureka-server/
├── gateway-server/
├── productos-service/
├── inventario-service/
└── compras-app/

Contribuciones
--------------
- Usa ramas con nombres claros (feature/nombre, fix/bug, etc).
- Envía tus cambios mediante pull request.
- Incluye documentación o pruebas si es necesario.

Licencia
--------
Este proyecto está bajo una licencia de código abierto.

Contacto
--------
Para dudas o sugerencias, abre un issue en el repositorio o contacta al autor.
