# Sistema-Seguridad-Stark
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

#### Spring Web:  Maneja las peticiones REST (API para sensores).
Spring Data JPA + H2	Persistencia en base de datos en memoria para registrar los eventos.
Spring Security	Control de acceso y autenticación por roles (ADMIN / OPERATOR).
Spring WebSocket	Comunicación en tiempo real para envío de alertas.
Spring Actuator	Monitorización y métricas del sistema.
@Async / @Scheduled	Procesamiento concurrente y generación automática de eventos.
