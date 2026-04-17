# 🧪 PLAN DE PRUEBAS - FASE 3

## Objetivo
Verificar manualmente las funcionalidades implementadas en el banco de exámenes.

---

## PRUEBA 23: Carga del Catálogo de Exámenes

### Pasos para verificar:

1. **Abrir el archivo `index.html` en un navegador web**
   ```
   archivo://.../Examen/index.html
   ```

2. **Verificar que aparece la sección "Selecciona un Examen"**

3. **Verificar que se cargan las tarjetas de exámenes**
   - Deberían aparecer 2 exámenes: "Mantenimiento de Laptops" y "Gestión de Calidad"

4. **Verificar en la consola del navegador (F12)**
   ```
   ✅ Catálogo cargado: 2 exámenes
   ```

### Resultado esperado:
| Verificación | Estado |
|--------------|--------|
| Sección de selección visible | ⏳ |
| Tarjetas de exámenes visibles | ⏳ |
| Sin errores en consola | ⏳ |

---

## PRUEBA 24: Búsqueda y Filtros

### Pasos para verificar:

#### Búsqueda por texto:
1. Escribir "mantenimiento" en el campo de búsqueda
2. Debería mostrar solo 1 examen

#### Filtro por categoría:
1. Seleccionar "Tecnología" en el dropdown de categoría
2. Debería mostrar solo 1 examen

#### Filtro por dificultad:
1. Restablecer filtros
2. Seleccionar "Avanzada" en dificultad
3. Debería mostrar solo 1 examen

#### Filtro por duración:
1. Restablecer filtros
2. Seleccionar "≤ 30 min"
3. Debería mostrar 0 exámenes (el más corto es 45 min)

#### Combinación de filtros:
1. Limpiar todos los filtros
2. Buscar "calidad" Y seleccionar categoría "Gestión"
3. Debería mostrar 1 examen

### Resultado esperado:
| Verificación | Estado |
|--------------|--------|
| Búsqueda por texto funciona | ⏳ |
| Filtro por categoría funciona | ⏳ |
| Filtro por dificultad funciona | ⏳ |
| Filtro por duración funciona | ⏳ |
| Combinación de filtros funciona | ⏳ |

---

## PRUEBA 25: Selección de Examen

### Pasos para verificar:

1. Hacer clic en "Seleccionar Examen" de cualquier tarjeta

2. **Verificar transición:**
   - La sección de selección debería ocultarse
   - El formulario de estudiante debería mostrarse

3. **Verificar información del examen:**
   - Should show título del examen seleccionado
   - Debería mostrar duración y número de preguntas
   - El encabezado debería actualizarse con el título

4. **Verificar que el formulario tiene:**
   - Campo de nombre
   - Campo de sección
   - Campo de cédula (opcional)

### Resultado esperado:
| Verificación | Estado |
|--------------|--------|
| Transición a formulario funciona | ⏳ |
| Información del examen visible | ⏳ |
| Encabezado actualizado | ⏳ |
| Campos del formulario presentes | ⏳ |

---

## PRUEBA 26: Formato Nuevo vs Antiguo

### Pasos para verificar:

#### Formato nuevo (Gestión de Calidad):
1. Seleccionar "Gestión de Calidad"
2. Iniciar el examen
3. Verificar que:
   - La duración es 45 minutos
   - Hay 30+ preguntas

#### Formato nuevo (Mantenimiento de Laptops):
1. Volver a selección
2. Seleccionar "Mantenimiento de Laptops"
3. Iniciar el examen
4. Verificar que:
   - La duración es 60 minutos
   - Hay 30 preguntas

### Resultado esperado:
| Verificación | Estado |
|--------------|--------|
| Gestión de Calidad: 45 min, 30+ preg | ⏳ |
| Mantenimiento: 60 min, 30 preg | ⏳ |
| Configuración dinámica aplicada | ⏳ |

---

## PRUEBA 27: Diseño Responsivo

### Pasos para verificar:

#### Desktop (> 768px):
1. Verificar que las tarjetas están en grid de 2+ columnas

#### Móvil (< 600px):
1. Redimensionar ventana a menos de 600px
2. Verificar que las tarjetas pasan a 1 columna
3. Verificar que los filtros se apilan verticalmente

### Resultado esperado:
| Verificación | Estado |
|--------------|--------|
| Grid multi-columna en desktop | ⏳ |
| 1 columna en móvil | ⏳ |
| Filtros se apilan en móvil | ⏳ |

---

## PRUEBA 28: Flujos Completos

### Flujo 1: Inicio completo de examen
1. Abrir página → Seleccionar examen → Llenar formulario → "Comenzar Examen"
2. Verificar que el examen inicia correctamente
3. Verificar temporizador muestra duración correcta
4. Responder una pregunta
5. Verificar que se marca como respondida

### Flujo 2: Nuevo intento
1. Durante un examen, hacer clic en "Nuevo Intento" o en "Volver a Resultados"
2. Verificar que vuelve a la selección de exámenes
3. Verificar que los filtros y búsqueda están reseteados

### Flujo 3: Entrega de examen
1. Responder todas las preguntas (o entregar anticipadamente)
2. Confirmar entrega
3. Verificar pantalla de resultados
4. Hacer clic en "Nuevo Intento"
5. Verificar que vuelve a selección de exámenes

### Resultado esperado:
| Verificación | Estado |
|--------------|--------|
| Flujo 1: Inicio completo | ⏳ |
| Flujo 2: Nuevo intento | ⏳ |
| Flujo 3: Entrega y nuevo intento | ⏳ |

---

## CHECKLIST FINAL DE VERIFICACIÓN

| # | Prueba | Estado |
|---|-------|--------|
| 23.1 | Carga de catálogo | ⏳ |
| 23.2 | Sin errores en consola | ⏳ |
| 24.1 | Búsqueda por texto | ⏳ |
| 24.2 | Filtro categoría | ⏳ |
| 24.3 | Filtro dificultad | ⏳ |
| 24.4 | Filtro duración | ⏳ |
| 24.5 | Combinación de filtros | ⏳ |
| 25.1 | Transición a formulario | ⏳ |
| 25.2 | Info del examen visible | ⏳ |
| 25.3 | Encabezado actualizado | ⏳ |
| 26.1 | Formato nuevo (GC) | ⏳ |
| 26.2 | Formato nuevo (ML) | ⏳ |
| 27.1 | Responsivo desktop | ⏳ |
| 27.2 | Responsivo móvil | ⏳ |
| 28.1 | Flujo inicio examen | ⏳ |
| 28.2 | Flujo nuevo intento | ⏳ |
| 28.3 | Flujo entrega | ⏳ |

---

## EJECUTAR PRUEBAS

Para ejecutar las pruebas:

1. **Abrir en navegador:**
   ```bash
   # Usando Python
   cd /home/dw/workspace/Examen
   python3 -m http.server 8000

   # Abrir: http://localhost:8000
   ```

2. **Usar herramientas de desarrollador (F12):**
   - Consola: Ver logs de JavaScript
   - Network: Verificar peticiones a JSON
   - Elements: Inspeccionar HTML/CSS

3. **Verificar en consola:**
   ```
   ✅ Catálogo cargado: 2 exámenes
   ✅ Examen cargado: Gestión de Calidad
      Preguntas: 35
      Duración: 45 min
   ```

---

*Documento de pruebas - FASE 3*
*Última actualización: 2026-04-17*
