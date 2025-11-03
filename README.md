# Microservicios de Pedidos
- **Dominio**: Order, Price, SKU, Quantity, eventos de dominio.
- **Application**: casos de uso CreateOrder, AddItemToOrder, puertos y DTOs.
- **Infra**: repositorio InMemory, pricing estàtico, event bus no-op.
- **HTTP**: endpoints minimo con Fastify.
- **Composicion**: container.ts como composicion root.
- **Tests**: dominio + aceptacion de casos de uso.

## Comportamiento
- 'POST /orders' crea un pedido
- 'POST /orders/:orderId/Items' agrega una linea (SKU + qty) con precio actual.
- Devuelve el total del pedido.

## Estructura de Carpetas
```
.
├── src
│   ├── application
│   │   ├── dto
│   │   │   ├── add-item-to-order-dto.ts
│   │   │   └── create-order-dto.ts
│   │   ├── ports
│   │   │   ├── clock.ts
│   │   │   ├── event-bus.ts
│   │   │   ├── order-repository.ts
│   │   │   ├── pricing-service.ts
│   │   │   └── server-dependencies.ts
│   │   ├── use-cases
│   │   │   ├── add-item-to-order.ts
│   │   │   └── create-order.ts
│   │   └── errors.ts
│   ├── composition
│   │   └── container.ts
│   ├── domain
│   │   ├── entities
│   │   │   └── order.ts
│   │   ├── errors
│   │   ├── events
│   │   │   ├── domain-event.ts
│   │   │   ├── item-added-to-order.ts
│   │   │   └── order-created.ts
│   │   └── value-objects
│   │       ├── currency.ts
│   │       ├── money.ts
│   │       ├── order-item.ts
│   │       ├── quantity.ts
│   │       └── sku.ts
│   ├── infrastructure
│   │   ├── http
│   │   │   ├── controllers
│   │   │   │   └── order-controller.ts
│   │   │   ├── server.ts
│   │   │   └── StaticPricingService.ts
│   │   ├── messaging
│   │   │   └── NoopEventBus.ts
│   │   └── persistence
│   │       └── in-memory
│   │           └── in-memory-order-repository.ts
│   └── shared
│       └── result.ts
├── tests
│   ├── acceptance
│   │   └── add-item-to-order.spec.ts
│   ├── domain
│   │   ├── money.spec.ts
│   │   └── order.spec.ts
│   ├── ejemplo.spec.ts
│   └── result.spec.ts
├── main.ts
├── package.json
├── tsconfig.json
└── vitest.config.ts
```