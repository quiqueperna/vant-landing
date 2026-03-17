# 📋 Especificaciones Funcionales — VANT

**Slogan:** "Registra por voz, simplifica tu gestión, toma el control total para proteger tu dinero."

---

### 1. Registro de Gastos (Entrada Instantánea)
- **Voz NLP**: Procesamiento de lenguaje natural para carga sin fricción. Ejemplo: "Panadería 1200 con débito".
- **Manual**: Formulario optimizado con 4 niveles de detalle (N1-N4).
- **Validaciones**: En tiempo real para asegurar integridad de datos.

### 2. Gestión de Tarjetas y Deuda
- **Control de Cuotas**: Seguimiento de consumos de 2 a 120 cuotas.
- **Calendario de Cierres**: Cálculo automático de fechas según el día de cierre de cada tarjeta.
- **Visibilidad**: Sostiene y organiza el peso de compromisos financieros recurrentes.

### 3. Fluctuación y Valor Real
- **Rastreo Individual**: Evolución del precio unitario de cada producto mes a mes.
- **Detección de Variaciones**: Alertas sobre qué ítems están aumentando por encima del promedio.
- **Análisis Histórico**: Diferencia entre precio nominal y valor real del dinero.

### 4. Consola Analítica (Nivel N4)
- **Granularidad**: Tipo (N1), Área (N2), Subcategoría (N3), Ítem (N4).
- **Estadísticas Avanzadas**: Filtros dinámicos, listados rápidos y proyecciones de ahorro.
- **Asesor Virtual**: Motor determinista que sugiere optimizaciones (compras al por mayor, alertas de crecimiento).

### 5. Configuración y UX
- **Stack**: Next.js 15, Supabase (Auth + RLS), Recharts, PWA.
- **Identidad**: Estética "Linear/High-End", minimalismo de precisión.
- **Seguridad**: Datos aislados por usuario mediante Row-Level Security.
