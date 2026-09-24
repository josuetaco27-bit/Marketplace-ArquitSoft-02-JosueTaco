flowchart TD
    %% =========================
    %% ACTORES
    %% =========================
    subgraph ACTORES["ACTORES"]
        Cliente["Cliente"]
        Seller["Seller"]
        Admin["Administrador"]
    end

    %% =========================
    %% PRESENTACIÓN
    %% =========================
    subgraph PRESENTACION["PRESENTACIÓN"]
        Web["Aplicación Web / API REST"]
    end

    %% =========================
    %% LÓGICA DE NEGOCIO
    %% =========================
    subgraph NEGOCIO["LÓGICA DE NEGOCIO"]
        Usuarios["Usuarios"]
        Sellers["Sellers"]
        Catalogo["Catálogo"]
        Carrito["Carrito"]
        Pedidos["Pedidos"]
    end

    %% =========================
    %% DATOS
    %% =========================
    subgraph DATOS["DATOS"]
        BD["Base de datos"]
    end

    %% =========================
    %% SISTEMAS EXTERNOS
    %% =========================
    subgraph EXTERNOS["SISTEMAS EXTERNOS"]
        Pago["Pasarela de pago"]
        ERP["ERP"]
        Envio["Servicio de envío"]
    end

    %% =========================
    %% FLUJO PRINCIPAL
    %% =========================
    Cliente --> Web
    Seller --> Web
    Admin --> Web

    Web --> Usuarios
    Web --> Sellers
    Web --> Catalogo
    Web --> Carrito
    Web --> Pedidos

    Usuarios --> BD
    Sellers --> BD
    Catalogo --> BD
    Carrito --> BD
    Pedidos --> BD

    %% =========================
    %% INTEGRACIONES EXTERNAS
    %% =========================
    Pedidos --> Pago
    Pedidos --> ERP
    Pedidos --> Envio

    %% =========================
    %% ESTILOS
    %% =========================
    style ACTORES fill:#222,stroke:#fff,stroke-width:2px,color:#fff
    style PRESENTACION fill:#222,stroke:#fff,stroke-width:2px,color:#fff
    style NEGOCIO fill:#222,stroke:#fff,stroke-width:2px,color:#fff
    style DATOS fill:#222,stroke:#fff,stroke-width:2px,color:#fff
    style EXTERNOS fill:#222,stroke:#fff,stroke-width:2px,color:#fff

    style Cliente fill:#333,stroke:#fff,color:#fff
    style Seller fill:#333,stroke:#fff,color:#fff
    style Admin fill:#333,stroke:#fff,color:#fff
    style Web fill:#333,stroke:#fff,color:#fff

    style Usuarios fill:#333,stroke:#fff,color:#fff
    style Sellers fill:#333,stroke:#fff,color:#fff
    style Catalogo fill:#333,stroke:#fff,color:#fff
    style Carrito fill:#333,stroke:#fff,color:#fff
    style Pedidos fill:#333,stroke:#fff,color:#fff

    style BD fill:#333,stroke:#fff,color:#fff

    style Pago fill:#333,stroke:#fff,color:#fff
    style ERP fill:#333,stroke:#fff,color:#fff
    style Envio fill:#333,stroke:#fff,color:#fff
