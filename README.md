# ¡Hola! Soy Gabriel Iborra

Desarrollador Web en Formación en el CIFP Carlos III (DAW) | Técnico en Sistemas en el IES Dos Mares (SMR)

---

### En qué estoy trabajando ahora

*   Finalizando el Grado Superior de **Desarrollo de Aplicaciones Web (DAW)** en el CIFP Carlos III.
*   **ERP a Medida para el Sector de la Construcción y Reformas (Odoo 18)**:
    Un sistema integral diseñado para automatizar la carga administrativa y mitigar pérdidas económicas mediante un control financiero estricto en tiempo real.
    *   **Backend & DB:** Diseño de 9 modelos principales en Python y PostgreSQL con lógica de persistencia, restricciones de negocio estrictas y auditoría de desgloses financieros. Los principales modelos son: Clientes, Especialistas, Gastos, Ingresos, Obras, PartesTrabajo, Presupuestos, Proveedores, Trabajadores.
    *   **Frontend Analítico:** Dashboard interactivo desarrollado con el framework **OWL (Odoo Workgroup Library)**, JS y CSS para renderizar KPIs de salud financiera y flujos de caja en vivo.

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
    Ecosistema frontend modular e inteligente para el análisis contable y control presupuestario de obras en tiempo real.
    *   **Características:** Arquitectura basada en componentes atómicos, filtrado predictivo relacional optimizado con `useMemo` (inmune a discrepancias de texto), y automatización interactiva de importes netos/IVA mediante React Hook Form y Zod.
    *   **Visualización:** Gráficos de balance e históricos con Recharts y sistema global de notificaciones reactivas a través de un contexto personalizado manejado por el hook `useToast`.
    *   **Despliegue Activo:** Ver despliegue [despliegue en Vercel](https://dashboard-financiero-kappa-blue.vercel.app/) | Ver repositorio [Ver repositorio de código](https://github.com/pdawgabriel-hub/dashboard-financiero.git)

*   **GeoAlquiler - Inteligencia Inmobiliaria y Análisis Espacial (R & Shiny)**
    Aplicación web analítica construida como paquete de R (framework `{golem}`) que transforma datos de anuncios de alquiler en inteligencia de mercado accionable, combinando geolocalización, Machine Learning y herramientas de decisión de inversión inmobiliaria. *Por ahora, los datos son ficticios (generados de forma simulada) y el despliegue está en desarrollo.*
    *   **Características:** Arquitectura modular en 14 módulos Shiny independientes siguiendo el patrón de Shiny Modules (`NS(id)` + `*UI()`/`*Server()`), filtros globales reactivos compartidos entre todos los módulos, y gestión de dependencias reproducible con `{renv}`.
    *   **Analítica & ML:** Modelo predictivo de precios por regresión, recomendador de inmuebles similares con K-Nearest Neighbors (KNN), detector automático de oportunidades de inversión y calculadora de rentabilidad con proyección de cash flow.
    *   **Visualización:** Mapa interactivo con capa de calor (`leaflet`/`leaflet.extras`), tablas interactivas (`DT`) y gráficos dinámicos con `plotly`.
    *   **Despliegue Planificado:** shinyapps.io (Cloud) | [Ver repositorio de código](https://github.com/pdawgabriel-hub/geo-alquiler)

---

### Próximamente

*   **LuzPredict - Predicción del Precio de la Luz (PVPC) con Python** *(idea en fase de planificación, aún sin repositorio)*
    Proyecto pensado para predecir el precio horario de la electricidad en España a partir de datos públicos reales de la API de ESIOS/REE, con un recomendador de las horas más económicas del día siguiente para el consumo doméstico.
    *   **Enfoque técnico previsto:** Ingesta desde una API pública real (no dataset estático), *feature engineering* temporal (lags, festivos, estacionalidad), modelos de forecasting (LightGBM / Prophet) con validación temporal correcta, y despliegue en Streamlit Community Cloud.

---

### Tecnologías y Herramientas

**Ecosistema ERP y Frameworks**
![Odoo](https://img.shields.io/badge/-Odoo-714B67?style=flat&logo=odoo&logoColor=white)
![OWL Framework](https://img.shields.io/badge/-OWL_Framework-007ACC?style=flat&logo=javascript&logoColor=white)
![Laravel](https://img.shields.io/badge/-Laravel-FF2D20?style=flat&logo=laravel&logoColor=white)
![React](https://img.shields.io/badge/-React-61DAFB?style=flat&logo=react&logoColor=black)
![Tailwind CSS](https://img.shields.io/badge/-Tailwind_CSS-06B6D4?style=flat&logo=tailwindcss&logoColor=white)

**Backend y Lógica**
![Python](https://img.shields.io/badge/-Python-3776AB?style=flat&logo=python&logoColor=white)
![Java](https://img.shields.io/badge/-Java-ED8B00?style=flat&logo=java&logoColor=white)
![PHP](https://img.shields.io/badge/-PHP-777BB4?style=flat&logo=php&logoColor=white)
![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Zod](https://img.shields.io/badge/-Zod-3E67B1?style=flat&logo=zod&logoColor=white)

**Frontend y Estilos**
![JavaScript](https://img.shields.io/badge/-JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Sass](https://img.shields.io/badge/-Sass-CC6699?style=flat&logo=sass&logoColor=white)
![Bootstrap](https://img.shields.io/badge/-Bootstrap-7952B3?style=flat&logo=bootstrap&logoColor=white)
![Vite](https://img.shields.io/badge/-Vite-646CFF?style=flat&logo=vite&logoColor=white)

**Ciencia de Datos & Analítica (R)**
![R](https://img.shields.io/badge/-R-276DC3?style=flat&logo=r&logoColor=white)
![Shiny](https://img.shields.io/badge/-Shiny-blue?style=flat&logo=rstudio&logoColor=white)
![Plotly](https://img.shields.io/badge/-Plotly-3F4F75?style=flat&logo=plotly&logoColor=white)
![Leaflet](https://img.shields.io/badge/-Leaflet-199900?style=flat&logo=leaflet&logoColor=white)

**Bases de Datos y Sistemas**
![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-336791?style=flat&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/-MongoDB-47A248?style=flat&logo=mongodb&logoColor=white)
![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/-Linux-FCC624?style=flat&logo=linux&logoColor=black)

---

### Contacto

*   **Email:** [pdawgabriel@gmail.com](mailto:pdawgabriel@gmail.com)
