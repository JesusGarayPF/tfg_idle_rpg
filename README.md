# Maïnlander – Stranded in Darkness (TFG) — Idle RPG Prototype (PC)

**Maïnlander – Stranded in Darkness** es un prototipo experimental para PC que fusiona **RPG** con **progresión pasiva gestionada con clicks** (idle / clicker).  
El objetivo del proyecto fue investigar la viabilidad de este tipo de producto y prototipar un núcleo jugable con **narrativa**, **exploración** y **gestión de estado**, con una base sólida para ampliar el bucle completo (combate, progreso, personajes).

Este repositorio contiene una **build jugable**, la **presentación del TFG** (sin código fuente) y **enlace a video demo**.

---

## Descarga (Build)

- **Windows x64:** *(enlace a Releases)*  
  Ve a **Releases** y descarga el `.zip` más reciente.

> Si la build no se abre en tu equipo, revisa la sección **Problemas conocidos** al final.

---

## Qué incluye el prototipo

### Mecánicas implementadas
- **Menú principal** con navegación y cambios de fondo / música.
- **Settings** con opciones (p. ej., brillo) y flujo de retorno al menú.
- **Sistema de escenas narrativas**:
  - diálogo con retratos
  - elecciones (hasta 3) y efectos sobre el estado de juego
  - bloqueo contextual de navegación durante escenas
- **Mapa de exploración** en cuadrícula (20x20) con:
  - exploración por celdas
  - actualización visual de información relevante al seleccionar zonas
  - barra de recursos como monitor persistente
- **Guardado y carga de partida** (estado de zonas, progreso y configuración).

### Contenido y herramientas internas mostradas en la demo
- **Editor de zonas** para gestionar las ~400 celdas del mapa.
- Generación y mantenimiento de un JSON extenso (más de 35.000 líneas) para datos de mapa/zona.
- Ilustración del mapa diseñada para **encajar 1:1** con la cuadrícula de botones y representar visualmente el contenido.

---

## Arquitectura (resumen conceptual)

Aunque este repositorio no incluye código, el proyecto se construyó con una estructura inspirada en separación por capas:

- **Pantallas (UI Toolkit):** cada pantalla tiene su **UXML/USS** y se gestiona como **GameObject** en Unity.
- **Controllers:** lógica de interacción y flujo entre pantallas (capa de “servicios”).
- **Managers:** acceso/carga de datos y mantenimiento de estado (capa de “datos”).
- **Modelos:** clases de datos para entidades (zonas, personajes, enemigos, etc.).
- **JSON externos al código fuente:**
  - **estáticos** (bibliotecas/configuración inicial)
  - **mutables** (estado de partida, progreso)
- **Assets:** imágenes, música y vídeo, asignados desde UI Builder o desde lógica de ejecución.

---

## Flujo de juego (actual)

Menú principal → Nueva partida / Cargar partida → Mapa → Entrada a zonas → Escenas narrativas → Guardado / Ajustes.

---

## Materiales del TFG

- Presentación: `presentation/`  
- Guion resumido: `script/`

---

## Estado del proyecto y trabajo pendiente

Este prototipo no llega todavía a un bucle completo. Quedó pendiente implementar:

- **Sistema de combate**
- **Progreso y gestión de personajes** (pantalla de grupo)
- Dinámicas avanzadas de supervivencia y estado: **luz, hambre, calor, cordura**
- **Segundo mapa** conectado al primero
- Mejoras opcionales:
  - asentamientos (gestión/mejora)
  - inventario (objetos clave)
  - registros: misiones, bestiario, logros, diálogos y elecciones

---

## Conclusiones (aprendizaje)

El proyecto fue una experiencia realista de desarrollo independiente, con foco en:
- modelado y manejo de datos
- lectura y persistencia de archivos
- diseño de interfaces (UI Toolkit)
- gestión de estados y navegación
- pruebas específicas tras compilación (bugs que no aparecen en Play Mode)

Tiempo estimado invertido: **> 80 horas** (aprox. 25% dedicado a depuración).

---

## Créditos y herramientas

- Motor: **Unity** (C# / UI Toolkit UXML/USS)
- Imágenes: generadas con asistencia de herramientas de IA
- Música: generada con asistencia de herramientas de IA

> Si algún asset adicional requiere atribución/licencia específica, se indicará en este repositorio.

---

## Problemas conocidos

- Algunas funcionalidades (zona / grupo) aparecen en UI pero **no están implementadas**.
- En algunas máquinas, Windows puede mostrar advertencias al ejecutar builds descargadas:
  - Descomprime el `.zip`
  - Ejecuta el `.exe`
  - Si aparece SmartScreen: “Más información” → “Ejecutar de todas formas” (bajo tu responsabilidad)

---

## Contacto

Para dudas sobre el proyecto o el TFG:  
**Jesús Garay Franco**  
LinkedIn: https://www.linkedin.com/in/jesus-garay-franco/  
Email: jesus.garay.f@gmail.com
