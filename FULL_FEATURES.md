# 📋 Funcionalidades de la App — VANT (Control de Gastos)

Este documento centraliza todas las capacidades del sistema VANT, combinando los requerimientos funcionales con la arquitectura lógica del repositorio.

---

### 1. Registro de Gastos
*   **Manual:** Formulario con ítem (autocompletado), categorías (N1/N2/N3), cantidad, unidad, monto, fecha, medio de pago (Efectivo, Débito, Crédito, Transferencia) y observaciones.
*   **Por Voz (NLP):**
    *   Procesamiento de lenguaje natural: "leche 2 litros 1500".
    *   Conversión de números: "ochenta mil" → 80.000.
    *   Detección automática de cuotas y tarjetas.
    *   **Bandeja de Revisión:** Captura registros no reconocidos para completar categoría o agregar al catálogo.
*   **Compras con Tarjeta y Cuotas:**
    *   Gestión de 2 a 120 cuotas.
    *   Generación automática de registros futuros según día de cierre.
    *   Etiquetado de progresión: "(1/3)", "(2/3)", etc.

### 2. Categorización en 4 Niveles
*   **N1 (Tipo):** Fijos, Variables, Extraordinarios, Imprevistos.
*   **N2 (Área):** Alimentación, Servicios, Transporte, etc.
*   **N3 (Subcategoría):** Verdulería, Bebidas, etc.
*   **N4 (Ítem):** Cebolla, Pan, Leche (específico).
*   *Catálogo editable por el usuario con unidades por defecto.*

### 3. Dashboard e Indicadores
*   **KPIs:** Total mes, promedio diario, gasto máximo, delta vs mes anterior.
*   **Visualización:**
    *   Gráfico de dona por tipo (N1).
    *   Gráfico de barras: Top 8 subcategorías.
*   **Selector Temporal:** Hoy, semana, mes, año, personalizado.
*   **Widgets:** Interfaz personalizable en orden y visibilidad.

### 4. Radar de Inflación Personal
*   **Rastreo de Precio Unitario:** Análisis de evolución (Monto / Cantidad).
*   **Proyecciones:** Regresión lineal para estimar precios futuros.
*   **Análisis de Impacto:** Identificación del producto más afectado y estimación de ahorro "si no hubiera subido".

### 5. Presupuestos y Alertas
*   **Límites:** Por categoría N1 o total general.
*   **Alertas Automáticas:**
    *   🔴 Excedido (≥100%).
    *   🟠 Cerca del límite (≥80%).
    *   🔴 Gastos > Ingresos.
    *   🟠 Crecimiento >20% vs mes anterior.
    *   🟠 Desviación del promedio histórico (6 meses).
*   **Centro de Notificaciones:** Sistema de badges en el header.

### 6. Gestión de Ingresos
*   **Fuentes:** Sueldo, Freelance, Alquiler, etc.
*   **Periodicidad:** Mensual, quincenal, semanal, único.
*   **Ratio:** Cálculo automático de la relación Gasto/Ingreso.

### 7. Gastos Recurrentes
*   **Automatización:** Diaria, semanal, mensual o personalizada (N días).
*   **Control:** Activar/Pausar recurrentes sin eliminar registros.

### 8. Listado y Auditoría
*   **Tabla Avanzada:** Columnas configurables, ordenamiento, filtros combinados y búsqueda libre.
*   **Edición Rápida:** Modificación de categoría y monto directamente en la grilla.

### 9. Asesor Virtual (Motor Determinista)
*   **Análisis Mensual:** Top ítems por monto y % del total.
*   **Sugerencias de Ahorro:** Identificación de compras al por mayor (ahorro estimado ~18%).
*   **Proyecciones:** Estimación de cierre de mes según ritmo actual.
*   **Consultas:** Interfaz de chat para preguntas financieras rápidas.

### 10. Configuración y UX
*   **Personalización:** Temas (Claro/Oscuro), 10+ Monedas, Formatos de fecha.
*   **Gestión de Activos:** Múltiples tarjetas de crédito con días de cierre.
*   **Onboarding:** Guía inicial para nuevos usuarios.
*   **PWA:** Instalable en móvil, acceso rápido `/quick-add`.
*   **Seguridad:** Supabase Auth + Row-Level Security (RLS).
