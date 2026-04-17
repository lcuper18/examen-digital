# Examen Digital - Sistema de Exámenes

![Versión](https://img.shields.io/badge/version-1.0.0-blue)
![Estado](https://img.shields.io/badge/FASE-3%20COMPLETADA-brightgreen)
![Licencia](https://img.shields.io/badge/licencia-MIT-green)

Sistema de exámenes digitales con soporte para múltiples bancos de preguntas, búsqueda, filtros y funcionalidad completa de examen en línea.

---

## 📋 Tabla de Contenidos

1. [Descripción General](#descripción-general)
2. [Estructura del Proyecto](#estructura-del-proyecto)
3. [Formatos de Archivos](#formatos-de-archivos)
4. [Características Implementadas](#características-implementadas)
5. [Estado del Proyecto](#estado-del-proyecto)
6. [Uso](#uso)
7. [API de Configuración](#api-de-configuración)
8. [Desarrollo Futuro](#desarrollo-futuro)

---

## 📖 Descripción General

Este proyecto es una aplicación web de exámenes digitales que permite:

- **Banco de Exámenes**: Sistema de selección con búsqueda y filtros
- **Múltiples Exámenes**: Soporte para múltiples bancos de preguntas
- **Exámenes Dinámicos**: Preguntas barajadas aleatoriamente en cada intento
- **Retroalimentación Inmediata**: Evaluación en tiempo real de respuestas
- **Auto-Guardado**: Recuperación de examen en progreso mediante localStorage
- **Exportación**: Resultados en PDF y portapapeles
- **Modo Revisión**: Revisión completa de respuestas después de entregado

---

## 📁 Estructura del Proyecto

```
/Examen
├── index.html                    # Aplicación principal (banco de exámenes)
├── preguntas.json               # Examen: Mantenimiento de Laptops
├── examenes.json                # Índice centralizado de exámenes
├── Examenes/
│   └── GestionCalidad.json      # Examen: Gestión de Calidad
├── docs/
│   ├── FASE3-PLAN.md            # Plan de trabajo FASE 3
│   └── TESTING-GUIDE.md         # Guía de pruebas manuales
├── backups/
│   ├── index.html.latest.bak    # Backup más reciente
│   └── index.html.*.bak         # Backups con timestamp
├── .gitignore                   # Archivos ignorados por git
├── README.md                    # Este archivo
└── LICENSE                     # Licencia MIT
```

---

## 📂 Formatos de Archivos

### 1. Archivo de Índice (examenes.json)

Archivo central que lista todos los exámenes disponibles.

```json
{
  "version": "1.0",
  "ultima_actualizacion": "2026-04-17",
  "examenes": [
    {
      "id": "mantenimiento-laptops",
      "titulo": "Mantenimiento de Laptops",
      "archivo": "preguntas.json",
      "descripcion": "Examen sobre mantenimiento y reparación de laptops",
      "institucion": "CTP Las Palmitas",
      "nivel": "Undécimo Nivel",
      "categoria": "Tecnología",
      "dificultad": "Intermedia",
      "preguntas": 30,
      "duracion": 60,
      "porcentaje_aprobacion": 60,
      "tags": ["hardware", "laptops", "reparación"]
    }
  ]
}
```

### 2. Archivo de Examen (formato con metadatos)

Cada examen contiene metadatos y el banco de preguntas.

```json
{
  "metadata": {
    "id": "mantenimiento-laptops",
    "titulo": "Mantenimiento de Laptops",
    "descripcion": "Examen sobre mantenimiento y reparación de laptops",
    "institucion": "CTP Las Palmitas",
    "nivel": "Undécimo Nivel",
    "duracion_minutos": 60,
    "preguntas_totales": 30,
    "porcentaje_aprobacion": 60,
    "categoria": "Tecnología",
    "dificultad": "Intermedia",
    "tags": ["hardware", "laptops", "reparación"],
    "version": "1.0",
    "fecha_creacion": "2025-01-15"
  },
  "preguntas": [
    {
      "id": "q1",
      "tema": "Componentes Internos de la Computadora Portátil",
      "texto": "¿Cuál es el componente principal...?",
      "opciones": [
        {"id": "a", "texto": "Opción A"},
        {"id": "b", "texto": "Opción B"},
        {"id": "c", "texto": "Opción C"}
      ],
      "respuesta_correcta": "b",
      "dificultad": "media",
      "explicacion": "La tarjeta madre es el componente central..."
    }
  ]
}
```

---

## ✅ Características Implementadas

### 🏦 Banco de Exámenes

- ✅ Índice centralizado (`examenes.json`)
- ✅ Búsqueda por título, descripción y tags
- ✅ Filtros por categoría (Tecnología, Gestión)
- ✅ Filtros por dificultad (Fácil, Intermedia, Avanzada)
- ✅ Filtros por duración máxima (30, 60, 90 min)
- ✅ Vista de tarjetas con información resumida
- ✅ Selección de examen con transición suave
- ✅ Encabezado dinámico según examen seleccionado

### 📝 Sistema de Exámenes

- ✅ Registro de estudiantes (nombre, sección, cédula opcional)
- ✅ Carga dinámica de preguntas desde JSON
- ✅ Temporizador configurable con advertencias automáticas
- ✅ Barajado aleatorio de preguntas en cada intento
- ✅ Retroalimentación inmediata (correcta/incorrecta)
- ✅ Navegación entre preguntas con indicador de estado
- ✅ Explicaciones detalladas para cada pregunta
- ✅ Soporte para formato nuevo (metadata) y antiguo

### 📊 Resultados y Estadísticas

- ✅ Calificación por letra (A-F)
- ✅ Desglose por tema
- ✅ Historial de intentos guardado
- ✅ Exportación a PDF
- ✅ Copiar resultados al portapapeles

### 💾 Persistencia

- ✅ Auto-guardado cada 30 segundos en localStorage
- ✅ Recuperación de examen en progreso
- ✅ Historial de últimos 5 intentos por examen
- ✅ expiry de datos de 7 días

### 🔧 Debugging y Deployment

- ✅ Backups automáticos con timestamp
- ✅ Verificación de sintaxis JavaScript
- ✅ Normalización de datos para compatibilidad
- ✅ Despliegue a GitHub

---

## 📈 Estado del Proyecto

### Progreso General

| Fase | Estado | Descripción |
|------|--------|-------------|
| **FASE 1** | ✅ Completada | Migración de estructura de datos |
| **FASE 2** | ✅ Completada | Repositorio GitHub |
| **FASE 3** | ✅ Completada | Interfaz de usuario (banco de exámenes) |

### Tareas Completadas (32/32)

```
✅ Tareas 1-9:   HTML/CSS para banco de exámenes (9/9)
✅ Tarea 10:    Probar estilos existentes (1/1)
✅ Tareas 11-22: JavaScript - Carga dinámica y catálogo (12/12)
✅ Tareas 23-28: Pruebas funcionales (6/6)
✅ Tarea 29:    Debugging y fixes (4 errores corregidos)
✅ Tarea 30:    Backup del index.html (2 backups)
✅ Tareas 31-32: Deployment a Git y GitHub (2/2)
─────────────────────────────────────────────────
TOTAL: 32/32 tareas (100%)
```

### Commits Realizados

| Commit | Descripción |
|--------|-------------|
| `042a766` | Initial commit: Sistema de examenes digitales |
| `d3678a9` | docs: Agregar plan de trabajo FASE 3 |
| `43f2d00` | feat: Implementar estructura HTML/CSS para banco de examenes |
| `7afa47b` | feat: Implementar JavaScript para banco de examenes |
| `26b03ce` | test: Completar tareas 23-28 - Verificacion de pruebas |
| `a49abda` | chore: Add backups to .gitignore |

---

## 🚀 Uso

### Requisitos

- Navegador moderno (Chrome, Firefox, Safari, Edge)
- Servidor web local o hosting (requiere fetch para JSON)

### Instalación

```bash
# Clonar el repositorio
git clone https://github.com/lcuper18/examen-digital.git

# Entrar al directorio
cd examen-digital
```

### Ejecución Local

```bash
# Con Python
python3 -m http.server 8000

# Con Node.js (http-server)
npx http-server -p 8000

# Con PHP
php -S localhost:8000
```

Luego abrir: **http://localhost:8000**

### Agregar Nuevo Examen

1. Crear archivo JSON en el formato especificado
2. Agregar entrada en `examenes.json`
3. Subir cambios a Git

```json
{
  "id": "nuevo-examen",
  "titulo": "Título del Examen",
  "archivo": "ruta/al/examen.json",
  "descripcion": "Descripción del examen",
  "institucion": "Nombre de la institución",
  "nivel": "Nivel educativo",
  "categoria": "Categoría",
  "dificultad": "Fácil/Intermedia/Avanzada",
  "preguntas": 30,
  "duracion": 45,
  "porcentaje_aprobacion": 60,
  "tags": ["tag1", "tag2"]
}
```

---

## ⚙️ API de Configuración

### Constante EXAM_CONFIG

```javascript
const EXAM_CONFIG = {
  totalQuestions: 30,              // Número de preguntas (se actualiza dinámicamente)
  timeLimit: 60 * 60,             // Límite de tiempo en segundos (se actualiza dinámicamente)
  timeWarnings: [15 * 60, 5 * 60, 1 * 60], // Advertencias de tiempo
  passPercentage: 60,              // Porcentaje para aprobar (se actualiza dinámicamente)
  autoSaveInterval: 30000,         // Intervalo de auto-guardado (ms)
  maxAttempts: 5,                  // Intentos máximos en historial
  storageKey: 'exam_data',       // Clave para localStorage
  storageExpiry: 7 * 24 * 60 * 60 * 1000 // Expiración de datos (7 días)
};
```

### Variables de Estado del Banco

```javascript
let examenesDisponibles = [];   // Lista de exámenes cargados
let examenesFiltrados = [];     // Lista filtrada para mostrar
let examenSeleccionado = null;  // Examen actualmente seleccionado
let examMetadata = {};          // Metadatos del examen actual
```

### Funciones Principales

| Función | Descripción |
|---------|-------------|
| `cargarCatalogoExamenes()` | Carga el índice desde `examenes.json` |
| `renderizarCatalogoExamenes()` | Genera las tarjetas de exámenes |
| `crearTarjetaExamen(examen)` | Crea HTML para una tarjeta de examen |
| `filtrarExamenes()` | Aplica filtros de búsqueda y categoría |
| `seleccionarExamen(examId)` | Selecciona un examen y muestra formulario |
| `actualizarInformacionExamen()` | Actualiza UI con info del examen |
| `loadQuestions(examFile)` | Carga preguntas desde archivo específico |
| `startExam()` | Inicia el examen seleccionado |
| `answer(qIdx, optIdx)` | Registra una respuesta |
| `submitExam()` | Finaliza y calcula resultados |
| `newAttempt()` | Reinicia para nuevo intento |
| `exportResults(format)` | Exporta resultados (PDF/clipboard) |
| `viewReview()` | Muestra modo revisión |

---

## 🔮 Desarrollo Futuro

### Versión 2.0 - Planeada

- [ ] Modo práctica sin temporizador
- [ ] Explicaciones detalladas por pregunta
- [ ] Sistema de puntos y gamificación
- [ ] Modo competitivo entre estudiantes
- [ ] Importación de exámenes desde CSV

### Versión 3.0 - Planificada

- [ ] Panel de administración completo
- [ ] Editor visual de preguntas
- [ ] API REST para gestión remota
- [ ] Integración con LMS (Moodle, Canvas)
- [ ] Certificados digitales

---

## 📄 Licencia

MIT License - Uso educativo libre.

---

## 👥 Créditos

| Rol | Asignación |
|-----|------------|
| **Frontend Dev** | Implementación HTML/CSS/JavaScript |
| **QA** | Pruebas funcionales |
| **DevOps** | Backup y deployment |
| **Git Expert** | Gestión del repositorio |

**Proyecto:** Sistema de Exámenes Digitales - CTP Las Palmitas  
**Fecha:** 2026-04-17  
**Repositorio:** https://github.com/lcuper18/examen-digital
