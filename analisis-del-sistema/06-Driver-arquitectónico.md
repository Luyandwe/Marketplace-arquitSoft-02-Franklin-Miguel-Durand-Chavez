# Drivers arquitectónicos

Los drivers arquitectónicos representan las necesidades y condiciones
que influyen directamente en las decisiones de arquitectura del
Marketplace de productos para mascotas.

## Drivers arquitectónicos

| ID | Driver arquitectónico | Origen | ¿Por qué influye? |
|---|---|---|---|
| DA01 | Escalabilidad | AC04 - Escalabilidad | El sistema debe soportar un incremento progresivo de usuarios y transacciones. |
| DA02 | Rendimiento | AC01 - Rendimiento | El sistema debe responder adecuadamente ante situaciones de alta concurrencia. |
| DA03 | Seguridad | AC02 - Seguridad | El sistema manejará información de usuarios, pedidos y pagos que debe estar protegida. |
| DA04 | Integración con pago externo | RF06 - Pagos | El sistema debe comunicarse con una pasarela de pagos externa. |
| DA05 | API REST | RC03 - REST API | El frontend y backend deben comunicarse mediante una API REST. |
| DA06 | Mantenibilidad / evolución modular | AC05 - Mantenibilidad | Influye en la separación de responsabilidades, modularidad y dependencias internas. |

## DA06 - Mantenibilidad / evolución modular

**ID:** DA06

**Driver arquitectónico:** Mantenibilidad / evolución modular

**Origen:** AC05 - Mantenibilidad

**Descripción:**  
El sistema debe permitir modificar funcionalidades sin afectar
innecesariamente otros módulos.

**Influencia arquitectónica:**  
Influye en la separación de responsabilidades, modularidad y
dependencias internas del sistema.

## Tabla de decisiones asociadas

| Driver | Problema que plantea | Decisión que responde |
|---|---|---|
| DA01 - Escalabilidad | Aumentarán los usuarios durante campañas y periodos de alta demanda. | Monolito modular con posibilidad de escalamiento horizontal. |
| DA02 - Rendimiento | Habrá situaciones de alta concurrencia. | Incorporar caché y optimizar la comunicación y el procesamiento. |
| DA03 - Seguridad | El sistema manejará datos sensibles. | Implementar autenticación y autorización. |
| DA04 - Pago externo | El sistema debe comunicarse con una pasarela de pagos externa. | Integración mediante API y adaptadores. |
| DA05 - API REST | El frontend y backend deben comunicarse mediante REST. | Separar la interfaz y el backend mediante una API REST. |
| DA06 - Mantenibilidad | Los cambios no deben afectar innecesariamente otros módulos. | Modularidad + Clean Architecture. |