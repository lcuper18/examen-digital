# Examen Digital - Sistema de Exámenes

Sistema de exámenes digitales con soporte para múltiples bancos de preguntas, búsqueda, filtros y funcionalidad completa de examen en línea.

## Tabla de Contenidos

1. [Descripción General](#descripción-general)
2. [Estructura del Proyecto](#estructura-del-proyecto)
3. [Formatos de Archivos](#formatos-de-archivos)
4. [Características](#características)
5. [Uso](#uso)
6. [API de Configuración](#api-de-configuración)
7. [Desarrollo Futuro](#desarrollo-futuro)

---

## Descripción General

Este proyecto es una aplicación web de exámenes digitales que permite:

- **Múltiples exámenes**: Sistema de banco de exámenes con búsqueda y filtros
- **Exámenes dinámicos**: Preguntas barajadas aleatoriamente en cada intento
- **Retroalimentación inmediata**: Evaluación en tiempo real de respuestas
- **Auto-guardado**: Recuperación de examen en progreso mediante localStorage
- **Exportación**: Resultados en PDF y portapapeles
- **Modo revisión**: Revisión completa de respuestas después de entregado

---

## Estructura del Proyecto

```
/Examen
├── index.html                    # Aplicación principal
├── preguntas.json               # Banco de preguntas (formato con metadatos)
├── examenes.json                # Índice de exámenes disponibles
├── Examenes/
│   └── GestionCalidad.json      # Banco de preguntas Gestión de Calidad
└── README.md                    # Documentación
```

---

## Formatos de Archivos

### 1. Archivo de Índice (examenes.json)

Archivo central que lista todos los exámenes disponibles.

```json
{
  "version": "1.0",
  "ultima_actualizacion": "2025-04-14",
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
      "tags": ["hardware", "laptops", "reparación"],
      "version": "1.0",
      "fecha_creacion": "2025-01-15"
    }
  ]
}
```

### 2. Archivo de Examen (formato con metadatos)

Cada examen contiene metadatos y el banco de preguntas.

```
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

## Características

### ✅ Banco de Exámenes (Implementado)

- **Índice centralizado** (`examenes.json`): Lista todos los exámenes disponibles
- **Búsqueda por título y descripción**: Encuentra exámenes rápidamente
- **Filtros por categoría, dificultad y duración**: Narrows down options
- **Vista de tarjetas**: Muestra información resumida de cada examen
- **Sistema de selección**: Interfaz para elegir entre múltiples exámenes

### ✅ Sistema de Exámenes (Implementado)

- Registro de estudiantes (nombre, sección, cédula opcional)
- Temporizador configurable con advertencias automáticas
- Barajado aleatorio de preguntas en cada intento
- Retroalimentación inmediata (correcta/incorrecta)
- Navegación entre preguntas con indicador de estado
- Explicaciones detalladas para cada pregunta (nuevo formato)

### ✅ Resultados y Estadísticas (Implementado)

- Calificación por letra (A-F)
- Desglose por tema
- Historial de intentos guardado
- Exportación a PDF
- Copiar resultados al portapapeles

### ✅ Persistencia (Implementado)

- Auto-guardado cada 30 segundos en localStorage
- Recuperación de examen en progreso
- Historial de últimos 5 intentos por examen

### 🚀 Próximas Funcionalidades

1. **Modo Práctica**: Sin límite de tiempo, ver respuesta correcta inmediatamente
2. **Sistema de Favoritos**: Marcar exámenes como favoritos
3. **Estadísticas Avanzadas**: Mejores puntajes, gráficos de progreso
4. **Modo Administrador**: Panel de gestión, editor de preguntas

---

## Uso

### Requisitos

- Navegador moderno (Chrome, Firefox, Safari, Edge)
- Servidor web local o hosting (requiere fetch para JSON)

### Instalación

1. Clonar o descargar el proyecto
2. Asegurarse de tener un servidor web disponible
3. Colocar los archivos en el directorio del servidor

### Ejecución Local

```bash
# Con Python
python -m http.server 8000

# Con Node.js (http-server)
npx http-server -p 8000

# Con PHP
php -S localhost:8000
```

### Agregar Nuevo Examen

1. Crear archivo JSON con el formato de examen
2. Agregar entrada en `examenes.json`
3. Actualizar índice si es necesario

---

## API de Configuración

### Constante EXAM_CONFIG

```javascript
const EXAM_CONFIG = {
  totalQuestions: 30,           // Número de preguntas
  timeLimit: 60 * 60,           // Límite de tiempo en segundos
  timeWarnings: [15 * 60, 5 * 60, 1 * 60], // Advertencias de tiempo
  passPercentage: 60,           // Porcentaje para aprobar
  autoSaveInterval: 30000,       // Intervalo de auto-guardado (ms)
  maxAttempts: 5,               // Intentos máximos en historial
  storageKey: 'exam_data',      // Clave para localStorage
  storageExpiry: 7 * 24 * 60 * 60 * 1000 // Expiración de datos (7 días)
};
```

### Funciones Principales del Sistema

| Función | Descripción |
|---------|-------------|
| `cargarCatalogoExamenes()` | Carga el índice de exámenes desde `examenes.json` |
| `filtrarExamenes()` | Aplica filtros de búsqueda y categoría |
| `renderizarExamenes()` | Genera las tarjetas de exámenes en la UI |
| `seleccionarExamen(id)` | Selecciona un examen y carga sus datos |
| `cargarExamen(id)` | Carga el archivo JSON del examen específico |
| `iniciarExamen()` | Inicia el examen seleccionado |
| `responder(index)` | Registra una respuesta |
| `entregarExamen()` | Finaliza y calcula resultados |
| `exportarPDF()` | Exporta resultados a PDF |
| `revisarRespuestas()` | Muestra modo revisión |

---

## Desarrollo Futuro

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
- [ ] Certificates digitales

---

## Licencia

MIT License - Uso educativo libre.

---

## Créditos

Desarrollado para CTP Las Palmitas - Undécimo Nivel
