# ¡Hola! Soy Gabriel Iborra

Desarrollador Web en Formación en el CIFP Carlos III (GSDAW) | Técnico en Sistemas en el IES Dos Mares (GMSMR)

---

### En qué estoy trabajando ahora

*   Finalizando el Grado Superior de **Desarrollo de Aplicaciones Web (DAW)** en el CIFP Carlos III.
*   **Rock & Roll Pizza — Web para un cliente real (Astro & Sanity)**:
    Proyecto real para una pizzería, con la que sustituyo un WordPress inicial por una web más ligera. Aún en fase de diseño y maquetación.
    *   **Funciones:** portada, oferta de la semana editable por el cliente (con fecha de inicio y fin), carta (imágenes y PDF descargable), sección "Quiénes somos" y contacto con dirección, teléfono y horario.
    *   **Gestión de contenido:** el cliente cambia la oferta y los datos del negocio desde un panel propio (Sanity Studio), con correo y contraseña, sin tocar código; la web se reconstruye sola al publicar.
    *   **Estado:** en desarrollo, trabajando el diseño y el contenido antes de conectar el panel y pasar a producción. El repositorio es privado por tratarse de un proyecto de cliente.
    *   **Demo (previa a producción):** [Ver demo en Vercel](https://rock-and-roll-pizza.vercel.app/)

<details>
<summary><b>Haz clic aquí para ver la estructura del proyecto</b></summary>

<br>

```
rock-and-roll-pizza/
├── web/                  # Astro + Tailwind
│   ├── src/
│   │   ├── assets/       # logo, imágenes
│   │   ├── components/   # Header, Hero, Oferta, Carta, Nosotros, Contacto, Footer
│   │   ├── data/         # datos de ejemplo (site, oferta)
│   │   ├── layouts/
│   │   └── pages/
│   └── public/
└── studio/               # Sanity Studio (panel del cliente)
```

</details>

*   **ERP a Medida para el Sector de la Construcción y Reformas (Odoo 18)**:
    Un sistema integral diseñado para automatizar la carga administrativa y mitigar pérdidas económicas mediante un control financiero estricto en tiempo real. Cubre todo el ciclo de una obra — cliente → presupuesto (con IVA y líneas de reforma) → obra → ejecución (partes de trabajo, especialistas y proveedores) → cierre financiero (ingresos, gastos, beneficio real y saldo pendiente) — con roles de usuario diferenciados y un panel de Análisis Financiero agregado de toda la cartera de obras. Desarrollado para una empresa real de construcción y reformas; preparado para su despliegue en el servidor del cliente.
    *   **Backend & DB:** Diseño de 14 modelos de negocio en Python sobre PostgreSQL (41 tablas: 35 de datos, incluidos los historiales de observaciones e incidencias y los adjuntos, y 6 tablas puente), con restricciones de negocio (`@api.constrains`), campos calculados que se recalculan en tiempo real y 19 tests automatizados sobre la lógica financiera y la integridad de los datos. Modelos principales: Clientes, Trabajadores, Proveedores, Especialistas, Obras, Presupuestos (+ Líneas de Reforma), Gastos, Ingresos, Partes de Trabajo (+ Líneas), Partes de Especialista, Partes de Proveedor y Faltas de Trabajadores.
    *   **Integridad de datos:** Presupuestos e ingresos siempre del cliente de su obra, todo cobro ligado a una obra, obras con cobros protegidas contra el borrado, borrados en cascada a través del ORM (recalculando los acumulados y eliminando también los ficheros adjuntos), ficha financiera 1:1 que nace y desaparece con su obra, y migraciones de datos versionadas para cambios con la base de datos ya en producción.
    *   **Frontend Analítico:** Dashboard interactivo desarrollado con el framework **OWL (Odoo Web Library)**, JS y CSS para renderizar KPIs de salud financiera y flujos de caja en vivo. Interfaz adaptada también a móvil.
    *   **Infraestructura y Despliegue:** Docker Compose con Odoo, PostgreSQL y Nginx Proxy Manager (HTTPS con Let's Encrypt), volúmenes persistentes con nombre, puertos internos accesibles solo en local, copias de seguridad automáticas de la base de datos y de los adjuntos con restauración verificada, plantillas de configuración y flujo de ramas `develop`/`main`. Los datos de demostración solo se generan en bases de datos de desarrollo, para no trabajar nunca con datos reales de clientes fuera de producción.
    *   **Documentación:** Informe técnico completo (arquitectura, cada modelo con sus campos, relaciones y métodos, y las reglas de negocio independientes del framework con una guía para reimplementarlo en otro stack: modelo relacional, equivalencias de conceptos de Odoo y escenario de pruebas), esquema SQL contrastado con la base de datos real y diagramas entidad-relación, guía de usuario de 37 páginas (cada pantalla, campo, filtro y agrupación explicados sin tecnicismos) y guía de despliegue paso a paso con lista de comprobación para producción — base para la futura migración de este mismo proyecto a otro stack (ver "Próximamente").

<details>
<summary><b>Haz clic aquí para ver las capturas de la interfaz y reportes del ERP</b></summary>

<br>

#### 1. Analytics & Dashboard Financiero

| KPIs & Rentabilidad | Distribución de Costes |
| :---: | :---: |
| <img src="assets/dashboard-kpis-rentabilidad.png" width="400" alt="KPIs y Rentabilidad"> | <img src="assets/dashboard-distribucion-costes.png" width="400" alt="Distribución de Costes"> |
| *Análisis de salud financiera e indicadores clave de rendimiento* | *Desglose analítico de costes directos e indirectos* |

| Tesorería & Flujo de Caja | Evolución & Proyecciones |
| :---: | :---: |
| <img src="assets/dashboard-tesoreria.png" width="400" alt="Tesorería"> | <img src="assets/dashboard-proyecciones.png" width="400" alt="Evolución y Proyecciones"> |
| *Control de liquidez, entradas y salidas en tiempo real* | *Previsiones presupuestarias e históricos de balance* |

---

#### 2. Vistas de Gestión y Modelos de Datos

| Vista Kanban (Gestión de Obras / Proyectos) | Vista Formulario (Gestión de Partes de Trabajo) |
| :---: | :---: |
| <img src="assets/vista-kanban-obras.png" width="400" alt="Vista Kanban Obras"> | <img src="assets/vista-formulario-partes.png" width="400" alt="Vista Formulario Partes"> |
| *Flujo visual de estados y seguimiento analítico por etapa* | *Lógica relacional avanzada, validaciones y restricciones de negocio* |

**Modelo de Datos**

```mermaid
erDiagram
  CLIENTES ||--o{ OBRAS : tiene
  CLIENTES ||--o{ PRESUPUESTOS : recibe
  OBRAS ||--o{ PRESUPUESTOS : "se presupuesta en"
  OBRAS ||--|| GASTOS : "ficha financiera 1:1"
  OBRAS ||--o{ INGRESOS : cobra
  OBRAS ||--o{ PARTES_TRABAJO : registra
  OBRAS ||--o{ PARTES_ESPECIALISTA : registra
  OBRAS ||--o{ PARTES_PROVEEDOR : registra
  TRABAJADORES ||--o{ PARTES_TRABAJO : "imputa horas"
  TRABAJADORES ||--o{ FALTAS : tiene
  ESPECIALISTAS ||--o{ PARTES_ESPECIALISTA : factura
  PROVEEDORES ||--o{ PARTES_PROVEEDOR : suministra
```

*Vista simplificada con las entidades principales. El modelo completo tiene 41 tablas, incluidos los historiales de observaciones e incidencias, los adjuntos y 6 tablas puente: [ver esquema relacional completo](assets/esquema-er-completo.svg).*

---

#### 3. Documentos y Reportes Impresos (PDF/QWeb)

| Presupuesto de Obra | Informe de Estado de Obra | Parte de Trabajo Diario |
| :---: | :---: | :---: |
| <img src="assets/reporte-presupuesto.png" width="260" alt="Reporte Presupuesto"> | <img src="assets/reporte-informe-obra.png" width="260" alt="Reporte Informe Obra"> | <img src="assets/reporte-parte-trabajo.png" width="260" alt="Reporte Parte Trabajo"> |
| *Presupuesto detallado para cliente con impuestos e imprevistos* | *Resumen ejecutivo de costes, avance y desviaciones* | *Control diario de mano de obra y materiales consumidos* |

</details>

---

### Portfolio y Proyectos Destacados

*   **ERP Construcción - Dashboard Financiero (React & TypeScript)**
    Ecosistema frontend modular e inteligente para el análisis contable y control presupuestario de obras en tiempo real, adaptando a una versión 100% frontend (sin backend ni base de datos física, persistencia en `localStorage` versionado) el modelo de negocio de 13 entidades del ERP a medida hecho sobre Odoo.
    *   **Características:** Vistas intercambiables de tarjetas/lista con tarjetas totalmente clicables, registros relacionados tipo "smart button" en cada ficha (Cliente, Obra, Trabajador...), calendario mensual tipo Google Calendar, autocompletado con combobox buscable en los selectores de relación, y filtrado predictivo relacional optimizado con `useMemo` (inmune a discrepancias de texto).
    *   **Formularios y Documentos:** Automatización interactiva de importes netos/IVA mediante React Hook Form y Zod, y exportación a PDF (Presupuestos, Partes de Trabajo, seguimiento de Gastos) vía páginas de impresión dedicadas y `window.print()`.
    *   **Visualización:** Gráficos de balance e históricos con Recharts y sistema global de notificaciones reactivas a través de un contexto personalizado manejado por el hook `useToast`.
    *   **Despliegue Activo:** Ver despliegue [despliegue en Vercel](https://dashboard-financiero-kappa-blue.vercel.app/) | Ver repositorio [Ver repositorio de código](https://github.com/pdawgabriel-hub/dashboard-financiero.git)

*   **GeoAlquiler - Inteligencia Inmobiliaria y Análisis Espacial (R & Shiny)**
    Aplicación web analítica construida como paquete de R (framework `{golem}`) que transforma datos de anuncios de alquiler en inteligencia de mercado accionable, combinando geolocalización, Machine Learning y herramientas de decisión de inversión inmobiliaria. Los precios por zona proceden de fuentes reales (Generalitat de Catalunya, Generalitat Valenciana y Gobierno Vasco) mediante un pipeline de ingesta propio, con anclas documentadas a mano donde no existe fuente oficial.
    *   **Características:** Arquitectura modular en 14 módulos Shiny independientes siguiendo el patrón de Shiny Modules (`NS(id)` + `*UI()`/`*Server()`), filtros globales reactivos compartidos entre todos los módulos, y gestión de dependencias reproducible con `{renv}`.
    *   **Analítica & ML:** Modelo predictivo de precios por regresión, recomendador de inmuebles similares con K-Nearest Neighbors (KNN), detector automático de oportunidades de inversión, calculadora de rentabilidad con proyección de cash flow e informe ejecutivo descargable.
    *   **Visualización y Rendimiento:** Mapa interactivo con capa de calor (`leaflet`/`leaflet.extras`) agregado por barrio en servidor, tablas interactivas (`DT`) y gráficos dinámicos con `plotly` nativo (histogramas pre-agregados y submuestreo en gráficos densos) para un buen rendimiento incluso en móvil.
    *   **Despliegue Activo:** [Ver despliegue en shinyapps.io](https://pdawgabriel-hub.shinyapps.io/geoalquiler/) | [Ver repositorio de código](https://github.com/pdawgabriel-hub/geo-alquiler)

---

### Próximamente

*   **Migración del ERP de Construcción a SAP ABAP / HANA** *(planificación)*
    Llevar el ERP de gestión de obras (hoy en Odoo 18) a SAP S/4HANA, reimplementando el mismo modelo de datos y la misma lógica de negocio — presupuestos, obras, partes de trabajo/especialista/proveedor y seguimiento financiero — en ABAP sobre HANA, apoyándose en la documentación técnica ya generada del proyecto original (esquema relacional, modelos y métodos) como base de la migración.

*   **LuzPredict - Predicción del Precio de la Luz (PVPC) con Python** *(idea en fase de planificación, aún sin repositorio)*
    Proyecto pensado para predecir el precio horario de la electricidad en España a partir de datos públicos reales de la API de ESIOS/REE, con un recomendador de las horas más económicas del día siguiente para el consumo doméstico.
    *   **Enfoque técnico previsto:** Ingesta desde una API pública real (no dataset estático), *feature engineering* temporal (lags, festivos, estacionalidad), modelos de forecasting (LightGBM / Prophet) con validación temporal correcta, y despliegue en Streamlit Community Cloud.

---

### Tecnologías y Herramientas

**Lenguajes**
![Python](https://img.shields.io/badge/-Python-3776AB?style=flat&logo=python&logoColor=white)
![Java](https://img.shields.io/badge/-Java-ED8B00?style=flat&logo=java&logoColor=white)
![PHP](https://img.shields.io/badge/-PHP-777BB4?style=flat&logo=php&logoColor=white)
![JavaScript](https://img.shields.io/badge/-JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![R](https://img.shields.io/badge/-R-276DC3?style=flat&logo=r&logoColor=white)

**Frontend & UI**
![React](https://img.shields.io/badge/-React-61DAFB?style=flat&logo=react&logoColor=black)
![Astro](https://img.shields.io/badge/-Astro-BC52EE?style=flat&logo=astro&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/-Tailwind_CSS-06B6D4?style=flat&logo=tailwindcss&logoColor=white)
![Sass](https://img.shields.io/badge/-Sass-CC6699?style=flat&logo=sass&logoColor=white)
![Bootstrap](https://img.shields.io/badge/-Bootstrap-7952B3?style=flat&logo=bootstrap&logoColor=white)
![Vite](https://img.shields.io/badge/-Vite-646CFF?style=flat&logo=vite&logoColor=white)
![Zod](https://img.shields.io/badge/-Zod-3E67B1?style=flat&logo=zod&logoColor=white)

**Backend, ERP & Frameworks**
![Odoo](https://img.shields.io/badge/-Odoo-714B67?style=flat&logo=odoo&logoColor=white)
![OWL Framework](https://img.shields.io/badge/-OWL_Framework-007ACC?style=flat&logo=javascript&logoColor=white)
![Laravel](https://img.shields.io/badge/-Laravel-FF2D20?style=flat&logo=laravel&logoColor=white)

**Ciencia de Datos & Analítica (R)**
![Shiny](https://img.shields.io/badge/-Shiny-blue?style=flat&logo=rstudio&logoColor=white)
![Plotly](https://img.shields.io/badge/-Plotly-3F4F75?style=flat&logo=plotly&logoColor=white)
![Leaflet](https://img.shields.io/badge/-Leaflet-199900?style=flat&logo=leaflet&logoColor=white)

**Bases de Datos, DevOps & Sistemas**
![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-336791?style=flat&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/-MongoDB-47A248?style=flat&logo=mongodb&logoColor=white)
![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/-Linux-FCC624?style=flat&logo=linux&logoColor=black)
![Sanity](https://img.shields.io/badge/-Sanity-F03E2F?style=flat&logo=sanity&logoColor=white)
![Vercel](https://img.shields.io/badge/-Vercel-000000?style=flat&logo=vercel&logoColor=white)

---

### Contacto

*   **Email:** [pdawgabriel@gmail.com](mailto:pdawgabriel@gmail.com)
