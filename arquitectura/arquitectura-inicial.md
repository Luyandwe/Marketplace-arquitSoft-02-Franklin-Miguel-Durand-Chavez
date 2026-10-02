# Arquitectura inicial del sistema

## Diagrama de arquitectura

```mermaid
flowchart TD

    subgraph ACTORES["ACTORES"]
        Cliente["Cliente"]
        Seller["Seller"]
        Admin["Administrador"]
    end

    subgraph PRESENTACION["PRESENTACIÓN"]
        Web["Aplicación Web"]
        API["API REST"]
    end

    subgraph NEGOCIO["LÓGICA DE NEGOCIO"]
        Usuarios["Usuarios"]
        Sellers["Sellers"]
        Catalogo["Catálogo"]
        Carrito["Carrito"]
        Pedidos["Pedidos"]
    end

    subgraph DATOS["DATOS"]
        BD["Base de datos"]
    end

    subgraph EXTERNOS["SISTEMAS EXTERNOS"]
        Pago["Pasarela de pago"]
        Envio["Servicio de envío"]
        Facturacion["Servicio de facturación"]
        ERP["ERP"]
    end

    Cliente --> Web
    Seller --> Web
    Admin --> Web

    Web --> API
    API --> NEGOCIO

    NEGOCIO --> BD

    Pedidos --> Pago
    Pedidos --> Envio
    Pedidos --> Facturacion
    Catalogo --> ERP

    Usuarios ~~~ Sellers
    Sellers ~~~ Catalogo
    Catalogo ~~~ Carrito
    Carrito ~~~ Pedidos
```

## Descripción

La arquitectura inicial se organiza en tres capas principales:

### Presentación

Permite la interacción de los usuarios con el sistema mediante la aplicación web y la API REST.

### Lógica de negocio

Contiene los principales módulos responsables de las funcionalidades del sistema:

* Usuarios
* Sellers
* Catálogo
* Carrito
* Pedidos

### Datos

Permite almacenar y consultar la información mediante una base de datos.

### Sistemas externos

El sistema se integra con una pasarela de pago, un servicio de envío, un servicio de facturación y un ERP.
