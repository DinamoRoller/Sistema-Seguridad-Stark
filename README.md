# Sistema-Seguridad-Stark

## Desarrolladores

Administrador de Sistemas: Suren Joorablou Hashemi Alam

Ingeniero de Seguridad: Suren Joorablou Hashemi Alam

Desarrollador Frontend: Cintia Santillán García

Desarrollador Backend: María Díaz-Heredero López

## Sistema de Seguridad Inteligente

Proyecto desarrollado en Java con Spring Boot como parte del trabajo práctico de concurrencia, seguridad y comunicación en tiempo real.
El sistema simula una red de sensores inteligentes (movimiento, acceso, temperatura) que se comunican de forma concurrente con un servidor central para detectar posibles intrusiones y emitir alertas inmediatas.

## Objetivo del proyecto

Implementar un sistema de seguridad concurrente capaz de:

- Gestionar múltiples sensores de forma simultánea y eficiente.

- Procesar los datos en tiempo real utilizando hilos y tareas asíncronas.

- Controlar el acceso mediante Spring Security.

- Enviar notificaciones inmediatas ante eventos críticos utilizando WebSockets.

- Proveer una interfaz web sencilla para el operador del sistema.

  
## Arquitectura general

El sistema se basa en el ecosistema de Spring Boot con varios módulos integrados:

#### Spring Web: Maneja las peticiones REST (API para sensores).
#### Spring Data JPA + H2: Persistencia en base de datos en memoria para registrar los eventos.
#### Spring Security: Control de acceso y autenticación por roles (ADMIN / OPERATOR).
#### Spring WebSocket: Comunicación en tiempo real para envío de alertas.
#### Spring Actuator: Monitorización y métricas del sistema.
#### @Async / @Scheduled: Procesamiento concurrente y generación automática de eventos.

## Tecnologías utilizadas

- Java 17+
- Spring Boot 3.x
- Maven
- H2 Database (en memoria)
- Lombok (opcional)
- HTML

## Estructura del proyecto

src/
   main/
     java/com/stark/sistemaseguridad/
   
       SistemaSeguridadApplication.java     -> Clase principal
       config                               -> Configuración (seguridad, async, websocket)
       controller                           -> Endpoints REST y autenticación
       model                                -> Entidades JPA (SensorEvent)
       repository                           -> Repositorios de datos
       service                              -> Lógica concurrente y notificaciones
       websocket                            -> Configuración de canales WebSocket
       
    resources
        static/index.html                   -> Interfaz web del sistema
        application.properties              -> Configuración general

## Usuarios y roles

El sistema ya tiene dos tipos de usuarios cargados en memoria:

Usuario     Contraseña

admin       1234

tecnico     12345

Los usuarios se pueden modificar en la clase SecurityConfig.java.

## Procesamiento concurrente

Los sensores se simulan mediante la clase SensorSimulatorService, que genera eventos cada 5 segundos.

Cada evento se procesa de forma asíncrona con @Async usando un ThreadPoolTaskExecutor.

Los eventos se guardan en base de datos y, si son críticos, se notifican al panel en tiempo real.

## Dependencias
Se recomienda tener instaladas las siguientes dependencias para garantizar el correcto funcionamiento del código

Spring web
Spring Data JPA
H2 Database
Spring Security
Spring WebSocket
Spring Boot Actuator
Lombok (opcional)
