# Instrucciones del Proyecto para Gemini

## Resumen del Proyecto

Este es un proyecto de TypeScript que implementa un sistema simple de gestión de pedidos utilizando los principios de Clean Architecture.

## Tecnologías

- **Lenguaje:** TypeScript
- **Framework:** Fastify
- **Testing:** Vitest
- **Herramienta de Build:** `tsc`

## Cómo ejecutar el proyecto

- **Instalar dependencias:** `npm install`
- **Ejecutar en modo desarrollo:** `npm run dev`
- **Ejecutar tests:** `npm test`
- **Compilar para producción:** `npm run build`
- **Ejecutar en producción:** `npm start`

## Capas de Clean Architecture

- **Domain:** Contiene la lógica de negocio principal y las entidades.
- **Application:** Contiene los casos de uso y la lógica específica de la aplicación.
- **Infrastructure:** Contiene los detalles de implementación, como el servidor web, la base de datos, etc.
- **Composition:** Compone la aplicación conectando las diferentes capas.
