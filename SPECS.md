# Documento de Especificación: Panel de Administración - AgentHub

## 1. Descripción del Producto
**AgentHub** es una plataforma SaaS donde las empresas alquilan agentes de IA (asistentes inteligentes preconfigurados). El panel de administración es la herramienta interna para gestionar usuarios, agentes, habilidades (skills), contratos y monitorizar errores del sistema.

## 2. Stack Tecnológico y Restricciones
*   **HTML5 SEMÁNTICO:** Uso estricto de etiquetas semánticas (`<nav>`, `<header>`, `<main>`, `<section>`, `<table>`).
*   **CSS:** Tailwind CSS únicamente mediante CDN. Sin estilos en línea (`style`) ni archivos CSS externos.
*   **JavaScript:** JS Vanilla exclusivamente. Prohibido el uso de frameworks (React, Vue, etc.) o librerías (jQuery).
*   **Modo Oscuro:** Implementado con la utilidad `dark:` de Tailwind.

---

## 3. Especificaciones por Sección

### 3.1 Dashboard
*   **Tarjetas de Métricas:** Cuatro tarjetas (Ingresos, Pérdida por descuentos, Agentes activos, Agentes fallando) con icono, etiqueta y valor hardcodeado.
*   **Estilo:** Cada tarjeta debe usar un color de acento distinto y una sombra sutil.
*   **Placeholder:** Área de ancho completo con borde discontinuo para un "Gráfico de actividad semanal".

### 3.2 Gestión de Usuarios
*   **Tabla de Datos:** Listado de al menos 5 usuarios (Nombre, Email, Plan, Estado).
*   **Acciones:** Botón de tres puntos (`⋮`) que despliega un dropdown con "Ver detalle" y "Eliminar".
*   **Modal de Detalle:** Al pulsar "Ver detalle", abre un modal con el registro completo. Debe cerrarse con botón o clic en el backdrop.

### 3.3 Gestión de Agentes
*   **Listado:** Muestra nombre del agente, propietario, estado (activo/fallando) y lista de skills.
*   **Skills Colapsables:** Las habilidades están ocultas por defecto y se revelan con una transición suave al hacer clic.
*   **Configuración:** Dropdown con "Configurar" que abre un modal con un `<textarea>` para el system prompt[cite: 1].

### 3.4 Catálogo de Skills
*   **Contenido:** Mínimo 4 skills con nombre, descripción y contador de agentes que la usan.
*   **Contexto:** Incluye un texto breve explicando qué es una "skill" en AgentHub dentro del panel[cite: 1].
*   **Acciones:** Dropdown en cada fila con opciones de "Ver detalle" y "Eliminar".

### 3.5 Contrataciones de Agentes
*   **Tabla de Contratos:** Muestra Cliente, Agente, Skills, Fechas e Importe total.
*   **Desglose:** "Ver detalle" abre un modal con el precio individual de cada skill contratada.
*   **Consistencia:** Los nombres de los agentes deben coincidir con los de la sección de Gestión de Agentes.

### 3.6 Log de Errores
*   **Registro:** Mínimo 6 entradas con timestamp, agente, tipo de error y descripción breve.
*   **Visualización:** Uso de badges de colores según la gravedad o tipo de error[cite: 1].
*   **Acciones:** Dropdown con "Ver detalle" (abre traza del error en modal) y "Marcar como resuelto".

---

## 4. Tarea
Construye un dashboard funcional para el panel de administración para AgenHub
### 4.1 Inventario de Componentes UI
*   **Sidebar:** Navegación lateral persistente con enlaces a las 6 secciones.
*   **Modo Oscuro:** Toggle en la barra superior que cambia todo el panel y persiste entre secciones.
*   **Dropdowns:** Menús de acción que se cierran al hacer clic fuera de ellos.
*   **Modales:** Overlays con cierre mediante botón y clic en el área sombreada (backdrop).

### 4.2 Salida esperada
1.  **Interactividad:** Todos los dropdowns, modales y colapsables deben ser funcionales con JS Vanilla.
2.  **Responsividad:** El layout debe ser mobile first y usable en resoluciones de escritorio y tablet.
3.  **Consistencia de Datos:** El mismo nombre de agente debe aparecer en Gestión, Contrataciones y Logs.
