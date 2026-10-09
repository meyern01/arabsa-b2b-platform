<div align="center">

# Arabsa Industrial — Plataforma B2B de cotizaciones

**Plataforma SaaS que reemplaza las cotizaciones manuales por teléfono y WhatsApp para una empresa de venta industrial.**
<br/>
*B2B SaaS that replaces manual phone/WhatsApp quoting for an industrial sales company.*

![Estado](https://img.shields.io/badge/Estado-En_producci%C3%B3n-22c55e?style=for-the-badge)
![Proyecto de cliente](https://img.shields.io/badge/Proyecto_de_cliente-Client_project-13405C?style=for-the-badge)
![Hecho por Kodiak](https://img.shields.io/badge/Hecho_por-Kodiak-0B1F33?style=for-the-badge)

<img src="https://skillicons.dev/icons?i=nextjs,ts,supabase,postgres,tailwind,vercel,githubactions&theme=dark" alt="Stack" />

</div>

<!-- Agrega aquí una captura del dashboard (guárdala en /docs):
<p align="center"><img src="docs/dashboard.png" width="90%" alt="Dashboard de Arabsa" /></p>
-->

---

## El problema · The problem

Las cotizaciones se hacían a mano, por teléfono y WhatsApp: lentas, difíciles de rastrear y sin control de crédito ni facturación. La plataforma centraliza todo el proceso de venta en un solo sistema.

> *Quotes were handled manually by phone and WhatsApp. The platform centralizes the whole sales flow in one system.*

## Funcionalidades · Features

- **Roles con permisos** (Admin, Ventas, Facturación), con control de acceso **a nivel de base de datos** mediante Row Level Security.
- **Cotizaciones B2B** de principio a fin.
- **Módulo de crédito y facturación** con cálculo automático de vencimientos.
- **Catálogos PDF dinámicos** generados desde el sistema.
- **Panel de métricas en tiempo real** para la dirección.

## Seguridad · Security

Cada rol solo puede leer y modificar lo que le corresponde, y esa regla vive **en la base de datos** (políticas RLS de PostgreSQL), no solo en la interfaz. Aunque alguien manipule el frontend, no puede ver datos de otro rol.

```mermaid
flowchart LR
    U["Usuario"] --> APP["Next.js"]
    APP --> AUTH["Supabase Auth"]
    AUTH -- "rol: admin · ventas · facturación" --> RLS{"Políticas RLS"}
    RLS -- "permitido" --> DB[("PostgreSQL")]
    RLS -. "denegado" .-> X["Sin acceso"]
```

## Stack

| Capa | Tecnología |
|---|---|
| Frontend | Next.js 16 · TypeScript · Tailwind CSS |
| Backend / Datos | Supabase (PostgreSQL, Auth, Row Level Security) |
| CI/CD | GitHub Actions |
| Despliegue | Vercel |

## Capturas · Screenshots

<!-- Agrega capturas en /docs (oculta datos reales del cliente) y descomenta:
| Cotizaciones | Crédito y facturación | Métricas |
|---|---|---|
| ![](docs/cotizaciones.png) | ![](docs/facturacion.png) | ![](docs/metricas.png) |
-->

## Código · Source code

El código es **privado por acuerdo con el cliente**. Puedo mostrar una demostración en vivo en entrevista.
<br/>*Source code is private under client agreement — live walkthrough available on request.*

---

<div align="center">

Desarrollado por **[Alfonso Méndez](https://github.com/meyern01)** · **[Kodiak](https://getkodiak.dev)**

</div>
