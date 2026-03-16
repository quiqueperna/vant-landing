# Gemini CLI - Control de Gastos

Este archivo contiene las directrices principales para el desarrollo del proyecto "Control de Gastos".

## 📜 Especificaciones Técnicas
Toda la lógica de negocio y funcionalidades deben seguir estrictamente lo definido en [REQUIREMENTS.md](./REQUIREMENTS.md).

## 🛠️ Stack Tecnológico (Confirmado)
- **Framework**: Next.js 15 (App Router)
- **Lenguaje**: JavaScript
- **Base de Datos/Auth**: Supabase (PostgreSQL + RLS)
- **Visualización**: Recharts
- **Estado**: React Context API
- **Estilos**: Vanilla CSS / globals.css (HSL Variables)
- **Middleware**: Implementado para protección de rutas y auth.

## 🎨 Identidad Visual
- **Primario**: `#2563eb` (Blue 600)
- **Ahorro/Éxito**: `#22c55e` (Green 500)
- **Fondo**: `#f8fafc` (Slate 50)
- **Gráficos**: Paleta dinámica de 10 colores vibrantes (Recharts).

## 📁 Estructura del Proyecto
- `/app`: Rutas y lógica de servidor (Next.js App Router).
- `/components`: Componentes modulares (Dashboard, List, Form).
- `/context`: Manejo de estado global (Auth, Gastos).
- `/lib`: Utilidades de Supabase y constantes del negocio (`constants.js`).
- `/public`: Activos estáticos.

## 🎯 Mandatos de Desarrollo
1. **Fidelidad al Producto**: Mantener la categorización de 4 niveles y la lógica de "unidad/cantidad".
2. **Seguridad**: Respetar el Row-Level Security (RLS) en cada operación con Supabase.
3. **Visualización**: Los gráficos deben ser dinámicos y reflejar los filtros aplicados en el dashboard.
4. **PWA**: El sistema debe ser instalable y optimizado para uso móvil (Voz + Acceso rápido).
