# 📋 Funcionalidades de la App — Control de Gastos

---

### 1. Registro de Gastos

*Manual*
- Formulario con ítem (autocompletado del catálogo), categoría N1/N2/N3/N4, cantidad, unidad, monto, fecha, medio de pago (efectivo / débito / crédito / transferencia), y observaciones.
- **Implementación Actual**: Selectores en cascada dinámicos para los 4 niveles de categorización.
- Validaciones en tiempo real.

*Por Voz*
- Habla y la app entiende: "leche 2 litros 1500", "sábanas 3 cuotas visa 60000"
- Convierte números en palabras: "ochenta mil" → 80.000
- Detecta automáticamente: ítem, cantidad, monto, cuotas, medio de pago
- Si reconoce el ítem → guarda automáticamente
- Si no lo reconoce → guarda como "pendiente de revisión" para completar después

---

### 2. Categorización en 4 Niveles

- *N1* — Tipo: Fijos, Variables, Extraordinarios, Imprevistos
- *N2* — Área: Alimentación, Servicios, Transporte, etc.
- *N3* — Subcategoría: Verdulería, Bebidas, etc.
- *N4* — Ítem específico: Cebolla, Pan, Leche, etc.

Catálogo de ítems predefinidos con unidad por defecto. El usuario puede crear, editar y organizar sus propias categorías e ítems (gestionado vía `lib/constants.js` y `migration_categorias.sql`).

---

### 3. Dashboard e Indicadores

- **Tecnología**: Implementado con **Recharts**.
- *KPIs*: Total del mes, promedio diario, gasto máximo, delta vs mes anterior.
- *Gráfico dona*: Desglose por tipo de gasto (N1).
- *Gráfico de barras*: Top 8 subcategorías del período.
- *Ranking de ítems*: Visualización de los ítems con mayor peso en el gasto.
- *Selector de período*: Hoy, Esta semana, Últimos 7 días, Este mes, Mes anterior, Este año, Personalizado.

---

### 4. Dashboard de Inflación Personal

- Rastrea el precio unitario de cada ítem a lo largo del tiempo (precio = monto / cantidad).
- Muestra la variación % desde el primer registro.
- *Proyección futura* con regresión lineal.
- Identifica el producto más afectado por la inflación.
- Estimación de ahorro si los precios no hubieran subido.

---

### 5. Presupuestos y Alertas

- Definir límites de gasto por categoría N1 o total general.
- *Alertas automáticas*:
  - 🔴 Presupuesto excedido (≥ 100%)
  - 🟠 Cerca del límite (≥ 80%)
  - 🔴 Gastos superan los ingresos del mes
  - 🟠 Gastos llegan al 85% de los ingresos
- Notificaciones integradas en el Dashboard.

---

### 6. Ingresos

- Registrar múltiples fuentes: Sueldo, Freelance, Alquiler, Honorarios, Bono, etc.
- La app calcula automáticamente la relación gasto/ingreso del mes.

---

### 7. Gastos Recurrentes

- Crear gastos que se repiten automáticamente.
- Frecuencias: Diaria, Semanal, Quincenal, Mensual, Personalizado (N días).

---

### 8. Listado Completo de Gastos

- **Tabla Dinámica**: Columnas configurables (monto, medio de pago, ítem, cantidad, tipo, área, subcategoría, fecha, nota).
- **Filtros Avanzados**: Por período, tipo N1, medio de pago, texto libre.
- **Edición Inline**: Modificación rápida de monto y categoría directamente en la lista.

---

### 9. Revisión de Gastos por Voz

- Panel dedicado a gastos registrados por voz que no fueron reconocidos automáticamente.
- Opción de agregar el ítem al catálogo para aprendizaje del sistema.

---

### 10. Asesor Virtual

Motor de análisis determinista que genera:
- *Sugerencias de compra al por mayor*: identifica ítems frecuentes y estima el ahorro potencial (~18%).
- *Proyección de cierre de mes*: estima el gasto final basado en el ritmo actual.

---

### 11. Configuración y Personalización

- *Tema*: Soporte para modo claro/oscuro (HSL variables).
- *Moneda*: Múltiples divisas configurables (ARS, USD, EUR, etc.).
- *Tarjetas*: Gestión de múltiples tarjetas con sus días de cierre.

---

### 12. Identidad Visual (Branding)

- **Paleta de Colores**:
  - **Primario**: `#2563eb` (Blue 600) — Confianza y tecnología.
  - **Fondo**: `#f8fafc` (Slate 50) — Limpieza y claridad.
  - **Éxito**: `#22c55e` (Green 500) — Ahorro y crecimiento.
  - **Peligro**: `#ef4444` (Red 500) — Alertas y gastos críticos.
- **Tipografía**: Sans-serif moderna, enfocada en legibilidad de datos.
- **Estética**: Basada en "Data-Driven Design", limpia, minimalista, con gráficos coloridos (`Recharts`).

---

### 13. Experiencia de Usuario

- **Next.js 15 (App Router)**: Navegación rápida y moderna.
- **PWA**: Instalable en dispositivos móviles.
- **Supabase**: Sincronización en tiempo real y seguridad de nivel de fila (RLS).
