---LAB_START---
LAB_ID: 04-00-01
---MARKDOWN---
# Generación de resúmenes ejecutivos de casos legales, minutas de reuniones y organización de flujos de trabajo para asegurar el cumplimiento de hitos críticos en auditorías o cierres fiscales. Sesión 4 60 min

## Metadatos del Laboratorio

| Atributo | Detalle |
|---|---|
| **Duración total** | 60 minutos (50 minutos de práctica activa + 10 minutos de configuración inicial) |
| **Complejidad** | Media |
| **Nivel de Bloom** | Aplicar |
| **Módulo** | 4 — Gestión del Conocimiento y Coordinación Operativa en Auditoría |
| **Temas cubiertos** | 4.1 Resúmenes Ejecutivos y Minutas · 4.2 Flujos de Trabajo para Hitos de Auditoría |
| **Aplicaciones principales** | Microsoft Word · Microsoft Teams · Microsoft Outlook · Microsoft Planner |
| **Licencia requerida** | Microsoft 365 Copilot (asignada por administrador de TI) |

---

## Descripción General

En este laboratorio el participante integrará Microsoft 365 Copilot en un flujo de trabajo completo de cierre fiscal trimestral con auditoría interna en curso. Utilizando materiales de práctica ficticios —un expediente legal de 15 páginas, la transcripción de una reunión de auditoría y un plan de trabajo de cierre fiscal— el participante generará un resumen ejecutivo de una página, una minuta estructurada y un cronograma de seguimiento con comunicaciones automatizadas, aplicando las técnicas de prompting avanzado estudiadas en la lección 4.1. El laboratorio se divide en dos bloques prácticos de 25 minutos cada uno: síntesis documental y gestión de hitos.

> ⚠️ **Aviso de privacidad:** Todos los archivos de práctica son ficticios. **No cargue información real de clientes, contribuyentes ni expedientes legales** en Copilot durante este laboratorio. Revise la política de privacidad de su organización antes de continuar.

---

## Objetivos de Aprendizaje

Al finalizar este laboratorio, el participante será capaz de:

- [ ] **Generar** un resumen ejecutivo de una página de un expediente legal complejo utilizando Copilot en Word, con estructura de antecedentes, riesgos, estado procesal y recomendación.
- [ ] **Automatizar** la creación de una minuta de reunión de auditoría estructurada con acuerdos, responsables y fechas compromiso usando Copilot en Teams o Word.
- [ ] **Analizar** un plan de trabajo de cierre fiscal con Copilot para identificar tareas en la ruta crítica y generar un cronograma de seguimiento priorizado.
- [ ] **Redactar** comunicaciones de seguimiento y alertas de hitos próximos a vencer utilizando Copilot en Outlook.
- [ ] **Aplicar** el ciclo de refinamiento iterativo (prompt → revisión crítica → ajuste) para mejorar la calidad del output de Copilot antes de su uso profesional.

---

## Prerrequisitos

### Conocimientos previos requeridos

| Área | Nivel mínimo requerido |
|---|---|
| Uso de Microsoft 365 Copilot en Word | Básico — haber completado Labs 01, 02 y 03 |
| Navegación en Microsoft Teams | Básico — reuniones, canales y chat |
| Uso de Microsoft Outlook | Básico — redacción y envío de correos |
| Conceptos de auditoría y cierre fiscal | Básico — familiaridad con hitos y cronogramas |
| Técnicas de prompting para Copilot | Básico — estructura rol + entrada + formato + tono |

### Acceso y licencias requeridos

- [ ] Cuenta corporativa con licencia **Microsoft 365 Copilot** activa y verificada
- [ ] Acceso a **Microsoft Word** con Copilot habilitado (ícono de Copilot visible en la cinta)
- [ ] Acceso a **Microsoft Teams** con Copilot habilitado en reuniones y chat
- [ ] Acceso a **Microsoft Outlook** con Copilot habilitado (botón "Borrador con Copilot" disponible)
- [ ] Acceso a **Microsoft Planner** desde Teams o navegador
- [ ] Los tres archivos de práctica cargados en **OneDrive personal** del participante:
  - `Lab04_Expediente_Caso_Legal.docx`
  - `Lab04_Transcripcion_Reunion_Auditoria.docx`
  - `Lab04_Plan_Cierre_Fiscal.xlsx`

> 💡 **Verificación previa:** Si el ícono de Copilot no aparece en Word, Teams u Outlook, contacte al administrador de TI antes de iniciar el laboratorio. La habilitación de Copilot a nivel de tenant puede tomar hasta 24 horas.

---

## Entorno del Laboratorio

### Requisitos de hardware

| Componente | Mínimo requerido | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 8ª gen / AMD Ryzen 5 | Intel Core i7 / AMD Ryzen 7 |
| Memoria RAM | 8 GB | 16 GB |
| Almacenamiento libre | 2 GB (archivos de práctica) | 5 GB |
| Resolución de pantalla | 1920×1080 | Doble monitor 1920×1080 |
| Conexión a internet | 10 Mbps | 25 Mbps o superior |

### Requisitos de software

| Aplicación | Versión mínima | Estado requerido |
|---|---|---|
| Microsoft Word | M365 versión 2401 o superior | Abierto con Copilot activo |
| Microsoft Teams | Versión actual (nueva experiencia) | Sesión iniciada |
| Microsoft Outlook | M365 versión actual | Sesión iniciada |
| Microsoft Planner | Versión cloud actual | Accesible desde Teams o Edge |
| Microsoft Edge | Versión 120 o superior | Disponible como respaldo |
| Adobe Acrobat Reader DC | Versión actual | Para visualización de PDFs de referencia |

### Configuración inicial del entorno (10 minutos)

Realice los siguientes pasos **antes** de iniciar la práctica cronometrada:

**1. Verificar archivos en OneDrive**

```
1. Abra el navegador Microsoft Edge
2. Navegue a: https://onedrive.live.com (o portal.office.com → OneDrive)
3. Confirme que los siguientes archivos están presentes en su OneDrive:
   - Lab04_Expediente_Caso_Legal.docx
   - Lab04_Transcripcion_Reunion_Auditoria.docx
   - Lab04_Plan_Cierre_Fiscal.xlsx
4. Si algún archivo falta, descárguelo del repositorio del curso
   y cárguelo a OneDrive antes de continuar.
```

**2. Verificar Copilot en Word**

```
1. Abra Microsoft Word desde el menú de aplicaciones M365
2. Abra el archivo: Lab04_Expediente_Caso_Legal.docx
3. Confirme que el ícono de Copilot (estrella de colores) aparece
   en la cinta de opciones (pestaña Inicio o pestaña Copilot)
4. Haga clic en el ícono para abrir el panel lateral de Copilot
5. Si el panel no responde, cierre y reabra Word, o use
   el atajo: Alt + I (o el ícono en la barra de estado inferior)
```

**3. Verificar Copilot en Teams**

```
1. Abra Microsoft Teams
2. En cualquier conversación de chat, escriba el símbolo "/" en el
   cuadro de mensaje — Copilot debe aparecer como opción
3. Alternativamente, navegue a la pestaña "Copilot" en el panel
   izquierdo de Teams (ícono de estrella)
4. Confirme que puede interactuar con Copilot en Teams
```

**4. Verificar Copilot en Outlook**

```
1. Abra Microsoft Outlook
2. Haga clic en "Nuevo correo electrónico"
3. En la ventana de redacción, confirme que aparece el botón
   "Borrador con Copilot" o el ícono de Copilot en la cinta
4. Cierre el correo de prueba sin guardar
```

---

## Instrucciones Paso a Paso

---

### 🔵 BLOQUE 1: Resúmenes Ejecutivos y Minutas de Reunión (25 minutos)

---

### Paso 1: Generación del Resumen Ejecutivo del Caso Legal en Word

**Objetivo:** Utilizar Copilot en Word para sintetizar el expediente legal de 15 páginas en un resumen ejecutivo de una página orientado a la toma de decisiones gerenciales.

**Tiempo estimado:** 12 minutos

#### Instrucciones

**1.1 — Abrir el expediente y el panel de Copilot**

```
1. En Microsoft Word, confirme que el archivo
   Lab04_Expediente_Caso_Legal.docx está abierto
2. Haga clic en el ícono de Copilot en la cinta de opciones
   para abrir el panel lateral derecho
3. Asegúrese de que el documento esté guardado en OneDrive
   (Copilot requiere que el archivo esté en la nube para
   acceder a su contenido de forma contextual)
4. Verifique que en la parte superior del panel de Copilot
   aparezca la referencia al documento actual
```

**1.2 — Ejecutar el prompt principal de resumen ejecutivo**

Copie y pegue el siguiente prompt en el panel de Copilot de Word. Adapte los corchetes según el contenido del expediente de práctica:

```text
Actúa como abogado fiscalista con experiencia en litigios ante
autoridades tributarias.

A partir del expediente completo que tienes en este documento,
genera un RESUMEN EJECUTIVO con las siguientes secciones:

1. ANTECEDENTES DEL CASO (máximo 80 palabras)
   Describe brevemente el origen del conflicto, las partes
   involucradas y el período fiscal en disputa.

2. POSICIÓN DEL CONTRIBUYENTE
   Resume los argumentos principales de la empresa auditada
   en no más de 60 palabras.

3. POSICIÓN DE LA AUTORIDAD FISCAL
   Resume los hallazgos y la postura de la autoridad en
   no más de 60 palabras.

4. RIESGOS PROCESALES IDENTIFICADOS
   Lista los 3 principales riesgos legales o fiscales,
   en formato de viñetas, con el nivel de riesgo
   (Alto / Medio / Bajo) para cada uno.

5. ESTADO PROCESAL ACTUAL Y PRÓXIMAS FECHAS CLAVE
   Indica la etapa procesal actual y las 2-3 fechas
   más críticas próximas a vencer.

6. RECOMENDACIÓN DE ACCIÓN INMEDIATA
   Proporciona una recomendación concreta en máximo 50 palabras.

Formato: documento Word formal con encabezados numerados.
Tono: técnico-legal, formal.
Extensión total: máximo 400 palabras.
Clasificación del documento: CONFIDENCIAL.
```

**1.3 — Insertar el resultado en el documento**

```
1. Revise el resumen generado en el panel de Copilot
2. Si el resultado es satisfactorio, haga clic en "Insertar"
   para añadirlo al documento
3. Si requiere ajustes, continúe con el paso 1.4 antes de insertar
```

**1.4 — Refinamiento iterativo (si es necesario)**

Si alguna sección del resumen es insuficiente o imprecisa, use los siguientes prompts de refinamiento:

```text
[Para ampliar la sección de riesgos:]
Desarrolla con más detalle la sección de RIESGOS PROCESALES.
Para cada riesgo, agrega: (a) la norma o artículo legal
que lo fundamenta, (b) la consecuencia económica potencial
estimada, y (c) la acción mitigadora recomendada.
```

```text
[Para corregir datos específicos:]
En la sección de ANTECEDENTES, corrige la fecha del
requerimiento original. Según el expediente, la fecha
correcta es [FECHA DEL EXPEDIENTE]. Actualiza el texto
manteniendo el mismo formato y extensión.
```

```text
[Para ajustar el tono:]
Reformula la sección de RECOMENDACIÓN DE ACCIÓN INMEDIATA
con un tono más ejecutivo y directo, adecuado para
presentar al Consejo de Administración. Máximo 40 palabras.
```

**1.5 — Revisión crítica obligatoria**

Antes de dar por finalizado el resumen, verifique manualmente los siguientes elementos contra el documento fuente:

```
□ Nombres de las partes (contribuyente, autoridad, representantes)
□ Período fiscal en disputa (años, trimestres)
□ Montos mencionados (créditos fiscales, multas, actualizaciones)
□ Fechas procesales críticas
□ Referencias a artículos legales o normativos
□ Conclusiones o recomendaciones que Copilot haya inferido
  sin base explícita en el texto del expediente
```

> ⚠️ **Punto crítico de validación:** Copilot tiene alta probabilidad de error en fechas, montos y nombres propios. La verificación manual no es opcional en contextos legales o fiscales reales.

**1.6 — Guardar el resumen**

```
1. Guarde el documento con el nombre:
   Lab04_Resumen_Ejecutivo_[SusIniciales].docx
2. Guárdelo en la misma carpeta de OneDrive donde están
   los archivos de práctica
3. Confirme que el archivo se sincronizó correctamente
   (ícono de nube con palomita en la barra de estado)
```

#### Resultado esperado

Un documento Word de aproximadamente una página que contenga las seis secciones del resumen ejecutivo, con lenguaje técnico-legal formal, estructura numerada clara y marcación de confidencialidad. El documento debe poder leerse en menos de 5 minutos y proporcionar suficiente información para que un directivo tome una decisión informada sobre el caso.

#### Verificación del Paso 1

```
□ El resumen contiene las 6 secciones solicitadas
□ La extensión total no supera las 400 palabras
□ Los 3 riesgos tienen nivel asignado (Alto/Medio/Bajo)
□ Se identifican al menos 2 fechas procesales próximas
□ Se realizó la revisión crítica manual de datos numéricos y fechas
□ El archivo fue guardado en OneDrive con el nombre correcto
```

---

### Paso 2: Generación de la Minuta de Reunión de Auditoría

**Objetivo:** Utilizar Copilot (en Teams o en Word) para transformar la transcripción de la reunión de auditoría en una minuta estructurada, accionable y lista para distribución.

**Tiempo estimado:** 13 minutos

#### Instrucciones

**2.1 — Abrir la transcripción de la reunión**

```
Opción A — Si usa Copilot en Teams (recomendado):
1. Abra Microsoft Teams
2. Navegue a la pestaña "Copilot" en el panel izquierdo
3. En el chat de Copilot, escriba: "Voy a pegarte la transcripción
   de una reunión de auditoría para que generes la minuta formal."
4. Confirme que Copilot está listo para recibir el texto

Opción B — Si usa Copilot en Word (alternativa):
1. Abra el archivo Lab04_Transcripcion_Reunion_Auditoria.docx en Word
2. Abra el panel lateral de Copilot
3. Continúe con el paso 2.2
```

**2.2 — Ejecutar el prompt de generación de minuta**

Copie y pegue el siguiente prompt, seguido del contenido de la transcripción:

```text
Eres un asistente ejecutivo especializado en reuniones de
auditoría fiscal y cumplimiento corporativo.

A partir de la siguiente transcripción de reunión, genera
una MINUTA FORMAL con exactamente esta estructura:

---
MINUTA DE REUNIÓN — [NOMBRE DEL PROYECTO/AUDITORÍA]
---

DATOS GENERALES:
- Fecha y hora de la reunión:
- Lugar / Modalidad (presencial / virtual):
- Convocante:
- Participantes (nombre y cargo):
- Elaboró la minuta:

OBJETIVO DE LA REUNIÓN:
[Una oración clara que describa el propósito de la sesión]

RESUMEN EJECUTIVO DE LA REUNIÓN:
[Párrafo breve de máximo 80 palabras con los temas principales tratados]

ACUERDOS Y DECISIONES TOMADAS:
[Lista numerada de cada acuerdo o decisión, redactada de forma
afirmativa y clara. Ej: "Se acordó presentar el reporte de
hallazgos al Comité antes del viernes 15."]

TAREAS ASIGNADAS:
[Tabla con columnas: N° | Tarea | Responsable | Fecha Límite | Prioridad]

PUNTOS DE SEGUIMIENTO PENDIENTES:
[Lista de temas que requieren seguimiento pero no tuvieron
resolución definitiva en esta reunión]

PRÓXIMA REUNIÓN:
- Fecha propuesta:
- Objetivo:
- Convocatoria a cargo de:

---
Tono: formal y ejecutivo.
Instrucción especial: Si algún dato no está explícito en la
transcripción, indica [A CONFIRMAR] en lugar de inventar
información.
---

[PEGAR AQUÍ EL CONTENIDO DE Lab04_Transcripcion_Reunion_Auditoria.docx]
```

> 💡 **Nota técnica:** La instrucción "indica [A CONFIRMAR] en lugar de inventar información" es una técnica de prompting que reduce las alucinaciones de Copilot en datos específicos como fechas, nombres y cargos. Úsela siempre en documentos formales.

**2.3 — Revisar y ajustar la tabla de tareas asignadas**

La tabla de tareas asignadas es el elemento más crítico de la minuta. Verifique que:

```
□ Cada tarea tiene un único responsable (no grupos genéricos
  como "el equipo")
□ Las fechas límite son específicas (día/mes/año), no relativas
  ("la próxima semana")
□ El nivel de prioridad es consistente (use: Alta / Media / Baja)
□ No hay tareas duplicadas o solapadas
```

Si la tabla necesita ajustes, use este prompt de corrección:

```text
Revisa la tabla de TAREAS ASIGNADAS y aplica las siguientes
correcciones:
1. Reemplaza todas las fechas relativas (como "próxima semana"
   o "en 3 días") por fechas absolutas. Asume que la reunión
   fue el [FECHA DE LA REUNIÓN DEL EXPEDIENTE].
2. Si una tarea tiene múltiples responsables, divídela en
   sub-tareas individuales con un responsable por línea.
3. Agrega una columna "Estado" con el valor "Pendiente" para
   todas las tareas recién asignadas.
```

**2.4 — Preparar la minuta para distribución**

```
1. Inserte el resultado en el documento Word
   (o copie desde Teams a un nuevo documento Word)
2. Guarde el archivo como:
   Lab04_Minuta_Reunion_[SusIniciales].docx
   en su carpeta de OneDrive
3. Revise que el encabezado de la minuta incluya la marca
   de confidencialidad apropiada
```

**2.5 — Verificación cruzada con la transcripción original**

```
Abra en paralelo Lab04_Transcripcion_Reunion_Auditoria.docx
y Lab04_Minuta_Reunion_[SusIniciales].docx

Verifique:
□ Todos los participantes mencionados en la transcripción
  aparecen en la minuta
□ Los acuerdos numerados corresponden a decisiones reales
  tomadas en la reunión (no inferidas)
□ Las fechas límite de las tareas son razonables y consistentes
  con el contexto del proyecto
□ No hay compromisos omitidos que aparezcan en la transcripción
```

#### Resultado esperado

Una minuta de reunión formal de 1 a 2 páginas con estructura completa: datos generales, resumen ejecutivo, acuerdos numerados, tabla de tareas con responsables y fechas, puntos de seguimiento y datos de la próxima reunión. El documento debe ser directamente distribuible al equipo de auditoría sin modificaciones mayores.

#### Verificación del Paso 2

```
□ La minuta contiene todas las secciones del formato solicitado
□ La tabla de tareas tiene al menos 3 filas con responsable,
  fecha límite y prioridad definidos
□ Los datos faltantes están marcados como [A CONFIRMAR]
  en lugar de inventados
□ Se realizó la verificación cruzada con la transcripción original
□ El archivo fue guardado en OneDrive con el nombre correcto
```

---

### 🟢 BLOQUE 2: Flujos de Trabajo y Hitos de Auditoría (25 minutos)

---

### Paso 3: Análisis del Plan de Cierre Fiscal con Copilot

**Objetivo:** Utilizar Copilot para analizar el plan de trabajo de cierre fiscal, identificar las tareas en la ruta crítica y generar un cronograma de seguimiento priorizado.

**Tiempo estimado:** 12 minutos

#### Instrucciones

**3.1 — Abrir el plan de cierre fiscal**

```
1. Abra el archivo Lab04_Plan_Cierre_Fiscal.xlsx en Microsoft Excel
2. Revise brevemente la estructura del archivo (2-3 minutos):
   - Identifique las columnas disponibles (tarea, responsable,
     fecha inicio, fecha fin, estado, dependencias, etc.)
   - Identifique cuántas tareas están en el plan
   - Note qué tareas tienen estado "En riesgo" o "Retrasada"
3. Guarde el archivo en OneDrive si aún no está sincronizado
```

**3.2 — Exportar el contenido relevante para Copilot**

Dado que Copilot en Word procesa texto mejor que tablas de Excel complejas, realice este paso de preparación:

```
Opción A — Usar Copilot en Excel (si está disponible):
1. En Excel, haga clic en el ícono de Copilot en la cinta
2. Use el prompt del paso 3.3 directamente en Excel

Opción B — Copiar datos a Word para análisis con Copilot:
1. Seleccione todas las celdas con datos del plan (Ctrl+A)
2. Copie (Ctrl+C)
3. Abra un nuevo documento Word en blanco
4. Pegue como texto sin formato (Ctrl+Shift+V → Solo texto)
5. Abra el panel de Copilot en este documento Word
```

**3.3 — Ejecutar el prompt de análisis de ruta crítica**

```text
Actúa como consultor de gestión de proyectos especializado
en auditorías fiscales y cierres contables trimestrales.

Analiza el siguiente plan de trabajo de cierre fiscal y
proporciona:

1. ANÁLISIS DE RUTA CRÍTICA
   Identifica las 5 tareas más críticas cuyo retraso
   impactaría directamente la fecha de cierre. Para cada una:
   - Nombre de la tarea
   - Responsable asignado
   - Fecha límite
   - Por qué es crítica (dependencias o impacto)

2. TAREAS EN RIESGO
   Lista todas las tareas que actualmente tienen estado
   "En riesgo", "Retrasada" o equivalente, con:
   - Días de retraso estimado
   - Impacto en el cronograma general (Alto/Medio/Bajo)

3. CUELLOS DE BOTELLA IDENTIFICADOS
   Identifica si algún responsable tiene sobrecarga de tareas
   críticas simultáneas o si hay dependencias bloqueadas.

4. CRONOGRAMA DE SEGUIMIENTO RECOMENDADO
   Propón una frecuencia de revisión para las próximas
   2 semanas (reuniones diarias, semanales, por área) con
   el enfoque específico de cada sesión.

5. TOP 3 ACCIONES PRIORITARIAS
   Las tres acciones que el líder del proyecto debe tomar
   HOY para evitar el incumplimiento del cierre fiscal.

Formato de salida: encabezados numerados con listas claras.
Tono: ejecutivo y orientado a la acción.

[PEGAR AQUÍ EL CONTENIDO DEL PLAN DE CIERRE FISCAL]
```

**3.4 — Crear tareas en Microsoft Planner**

Una vez identificadas las tareas críticas, créelas en Planner:

```
1. Abra Microsoft Teams
2. En el panel izquierdo, haga clic en los tres puntos (...)
   y busque "Planner" o "Tareas"
   (Alternativa: abra tasks.office.com en Microsoft Edge)
3. Cree un nuevo plan llamado:
   "Cierre Fiscal Q[TRIMESTRE] - Auditoría Interna"
4. Para cada una de las 5 tareas críticas identificadas por
   Copilot, cree una tarjeta en Planner con:
   - Título de la tarea
   - Responsable asignado
   - Fecha de vencimiento
   - Prioridad (Urgente / Importante / Normal)
   - Etiqueta: "RUTA CRÍTICA"
5. Para las tareas en riesgo identificadas, cree tarjetas
   adicionales con etiqueta: "EN RIESGO"
```

**3.5 — Generar texto de descripción de tareas con Copilot**

Para las 3 tareas de mayor prioridad en Planner, use Copilot para generar descripciones claras:

```text
Para la tarea "[NOMBRE DE LA TAREA CRÍTICA]" en el contexto
del cierre fiscal trimestral, redacta una descripción de tarea
para Microsoft Planner que incluya:
- Objetivo específico de la tarea (1 oración)
- Entregable esperado (qué debe producirse al completarla)
- Criterio de aceptación (cómo saber que está bien hecha)
- Dependencias (qué debe estar completado antes)

Extensión: máximo 100 palabras. Tono: instruccional y claro.
```

#### Resultado esperado

Un análisis estructurado del plan de cierre fiscal con ruta crítica identificada, tareas en riesgo priorizadas y cronograma de seguimiento recomendado. En Planner, al menos 5 tarjetas de tareas críticas y las tareas en riesgo identificadas, con responsables, fechas y etiquetas asignadas.

#### Verificación del Paso 3

```
□ Se identificaron al menos 5 tareas en la ruta crítica
□ Se identificaron las tareas con estado "En riesgo" o "Retrasada"
□ El cronograma de seguimiento incluye frecuencia y enfoque
  para las próximas 2 semanas
□ Se crearon al menos 5 tarjetas en Microsoft Planner
  con etiqueta "RUTA CRÍTICA"
□ Las tareas en riesgo tienen etiqueta "EN RIESGO" en Planner
□ Al menos 3 tareas tienen descripción generada con Copilot
```

---

### Paso 4: Generación de Comunicaciones de Seguimiento con Copilot en Outlook

**Objetivo:** Utilizar Copilot en Outlook para redactar correos de recordatorio y alertas de hitos próximos a vencer, dirigidos a los equipos y partes interesadas del proceso de auditoría.

**Tiempo estimado:** 13 minutos

#### Instrucciones

**4.1 — Identificar los hitos próximos a vencer**

Basándose en el análisis del Paso 3, identifique:

```
□ Hito #1: Tarea crítica que vence en los próximos 3 días
  (o la más próxima según el plan de práctica)
□ Hito #2: Tarea en riesgo que requiere escalamiento
□ Hito #3: Reunión de seguimiento que debe convocarse
```

**4.2 — Redactar correo de recordatorio de hito crítico**

```
1. Abra Microsoft Outlook
2. Haga clic en "Nuevo correo electrónico"
3. En la ventana de redacción, haga clic en el ícono de Copilot
   o en el botón "Borrador con Copilot"
4. En el panel de Copilot, seleccione "Borrador" y use
   el siguiente prompt:
```

```text
Redacta un correo electrónico formal de recordatorio
con las siguientes características:

CONTEXTO: Proceso de cierre fiscal trimestral con auditoría
interna en curso. El hito crítico "[NOMBRE DEL HITO]" vence
en [NÚMERO] días. El responsable es [NOMBRE DEL RESPONSABLE]
del área de [ÁREA].

DESTINATARIO: [Nombre del responsable] y su supervisor directo
EN COPIA: Líder del proyecto de auditoría

ESTRUCTURA DEL CORREO:
- Asunto: [Urgente/Importante según nivel de riesgo] |
  Recordatorio: [Nombre del hito] — Vence [Fecha]
- Saludo formal
- Párrafo 1: Contexto del recordatorio (qué hito, cuándo vence)
- Párrafo 2: Impacto en el cronograma general si no se completa
  a tiempo (sin ser amenazante, sí enfatizando la criticidad)
- Párrafo 3: Solicitud específica de acción o confirmación
  de avance para hoy [FECHA ACTUAL]
- Párrafo 4: Ofrecimiento de apoyo o escalamiento si hay
  bloqueos
- Cierre formal con nombre del remitente y cargo

Tono: profesional, directo, colaborativo (no intimidante).
Extensión: máximo 200 palabras en el cuerpo del correo.
```

**4.3 — Redactar alerta de tarea en riesgo con escalamiento**

Cree un segundo correo para la tarea en riesgo identificada:

```text
Redacta un correo de alerta ejecutiva para escalar
una tarea en riesgo en el proceso de auditoría fiscal.

SITUACIÓN: La tarea "[NOMBRE DE LA TAREA EN RIESGO]"
presenta un retraso de [X] días respecto al cronograma
original. El responsable es [NOMBRE] del área de [ÁREA].
El impacto en el cierre fiscal es [ALTO/MEDIO].

DESTINATARIO: Director/Gerente de [ÁREA RESPONSABLE]
EN COPIA: Líder de Auditoría, CFO o equivalente

ESTRUCTURA:
- Asunto: [ALERTA] Tarea en riesgo — Impacto en Cierre Fiscal Q[N]
- Resumen ejecutivo del problema (3 líneas máximo)
- Tabla de impacto: Tarea | Retraso | Impacto | Acción requerida
- Solicitud de decisión o recurso adicional específico
- Próximos pasos propuestos con fechas
- Cierre con disponibilidad para llamada de emergencia

Tono: ejecutivo, urgente pero constructivo.
Extensión: máximo 180 palabras más la tabla.
```

**4.4 — Redactar convocatoria de reunión de seguimiento**

```text
Redacta la convocatoria para una reunión urgente de
seguimiento del cierre fiscal con estas especificaciones:

TIPO: Reunión de seguimiento de hitos críticos
DURACIÓN: 30 minutos
FECHA PROPUESTA: [FECHA — 2 días hábiles desde hoy]
HORA: [Hora de preferencia del instructor]
MODALIDAD: Microsoft Teams (incluir enlace genérico)

PARTICIPANTES REQUERIDOS:
- Líder del proyecto de auditoría
- Responsables de las 3 tareas en ruta crítica
- Representante del área fiscal

AGENDA (en el cuerpo del correo):
1. Estado de hitos críticos (10 min)
2. Resolución de bloqueos identificados (15 min)
3. Compromisos y próximos pasos (5 min)

MATERIALES A PREPARAR: Cada responsable debe traer
el estado actualizado de su tarea y los bloqueos actuales.

Tono: formal, claro, que transmita urgencia sin generar pánico.
Incluye en el asunto: [REUNIÓN URGENTE] para que sea prioridad.
```

**4.5 — Revisar y ajustar los borradores**

```
Para cada uno de los 3 correos generados:
1. Revise que el tono sea apropiado para la jerarquía
   del destinatario
2. Verifique que los datos específicos (nombres, fechas,
   áreas) sean correctos y estén completos
3. Reemplace todos los marcadores [A CONFIRMAR] o
   [NOMBRE/FECHA] con datos reales del ejercicio
4. Use el refinamiento de Copilot si necesita ajustes:
```

```text
[Prompt de ajuste de tono:]
El correo anterior es demasiado formal/informal para el
contexto. Ajusta el tono para que sea [más directo /
más diplomático / más ejecutivo], manteniendo la misma
estructura y datos. No excedas las [X] palabras.
```

**4.6 — Guardar borradores (no enviar)**

```
⚠️ IMPORTANTE: NO envíe los correos durante el laboratorio.
Estos son ejercicios de práctica con datos ficticios.

1. Para cada correo, haga clic en "Guardar borrador"
   (Ctrl+S en la ventana de redacción)
2. Confirme que los 3 borradores aparecen en la carpeta
   "Borradores" de Outlook
3. Tome una captura de pantalla de los 3 borradores
   en la lista de Borradores para evidencia del laboratorio
```

#### Resultado esperado

Tres borradores de correo electrónico profesionales guardados en Outlook: (1) recordatorio de hito crítico próximo a vencer, (2) alerta ejecutiva de tarea en riesgo con escalamiento, y (3) convocatoria de reunión urgente de seguimiento. Cada correo debe estar listo para envío real con solo completar los datos del destinatario.

#### Verificación del Paso 4

```
□ Se redactaron los 3 correos usando Copilot en Outlook
□ El correo de recordatorio tiene asunto con formato
  [Urgente/Importante] | Recordatorio: [Hito] — Vence [Fecha]
□ El correo de alerta incluye tabla de impacto
□ La convocatoria tiene agenda estructurada con tiempos
□ Los 3 correos están guardados como borradores en Outlook
□ Ningún correo fue enviado (datos ficticios)
□ Se realizó al menos un refinamiento iterativo con Copilot
```

---

## Validación y Pruebas Finales

Al concluir los cuatro pasos, realice la siguiente validación integral del laboratorio:

### Lista de verificación de entregables

| Entregable | Archivo / Ubicación | Estado |
|---|---|---|
| Resumen ejecutivo del caso legal | `Lab04_Resumen_Ejecutivo_[Iniciales].docx` en OneDrive | ☐ Completado |
| Minuta de reunión de auditoría | `Lab04_Minuta_Reunion_[Iniciales].docx` en OneDrive | ☐ Completado |
| Análisis de ruta crítica | Documento Word o sección en el resumen | ☐ Completado |
| Tareas en Planner | Plan "Cierre Fiscal Q[N] - Auditoría Interna" | ☐ Completado |
| Correo de recordatorio de hito | Borrador en Outlook | ☐ Completado |
| Correo de alerta con escalamiento | Borrador en Outlook | ☐ Completado |
| Convocatoria de reunión urgente | Borrador en Outlook | ☐ Completado |

### Prueba de calidad del resumen ejecutivo

Comparta su `Lab04_Resumen_Ejecutivo_[Iniciales].docx` con un compañero y pídanle que responda estas preguntas **solo con la información del resumen** (sin ver el expediente original):

```
1. ¿Cuál es la disputa principal del caso?
2. ¿Cuáles son los 3 riesgos más importantes y su nivel?
3. ¿Qué acción debe tomarse inmediatamente?
4. ¿Cuándo vence la próxima fecha procesal crítica?
```

Si su compañero puede responder las 4 preguntas correctamente, el resumen ejecutivo cumple su propósito de comunicación gerencial.

### Prueba de accionabilidad de la minuta

Revise su `Lab04_Minuta_Reunion_[Iniciales].docx` y verifique:

```
□ ¿Cada tarea asignada tiene exactamente UN responsable?
□ ¿Todas las fechas límite son absolutas (día/mes/año)?
□ ¿Los acuerdos están redactados en forma afirmativa
  ("Se acordó X" en lugar de "Se habló de X")?
□ ¿Los puntos [A CONFIRMAR] han sido resueltos o están
  claramente marcados para seguimiento?
```

### Prueba de coherencia entre documentos

Verifique que existe coherencia entre los cuatro entregables:

```
□ Los responsables mencionados en la minuta coinciden
  con los asignados en las tarjetas de Planner
□ Las fechas límite de las tareas en Planner son consistentes
  con las fechas mencionadas en los correos de Outlook
□ Las tareas identificadas como "en ruta crítica" por Copilot
  en el Paso 3 están reflejadas en los correos del Paso 4
```

---

## Solución de Problemas

### Problema 1: Copilot en Word no accede al contenido del documento y genera resúmenes genéricos o vacíos

**Síntoma:** Al ejecutar el prompt de resumen ejecutivo, Copilot responde con texto genérico que no refleja el contenido del expediente, o indica que no puede acceder al documento. El panel de Copilot muestra respuestas como "No tengo información suficiente sobre este caso."

**Causa raíz:** Copilot en Word requiere que el documento esté guardado en **OneDrive o SharePoint Online** (no en almacenamiento local) para acceder a su contenido de forma contextual. Si el archivo está guardado localmente (en el disco duro o en una carpeta de red), Copilot no puede leerlo directamente. También puede ocurrir si la sesión de autenticación de Microsoft 365 expiró.

**Solución paso a paso:**

```
1. Verifique la ubicación del archivo:
   - En Word, revise la barra de título. Si muestra una ruta
     local (C:\Users\...) en lugar de OneDrive, el archivo
     no está en la nube.

2. Mover el archivo a OneDrive:
   - Haga clic en Archivo → Guardar como → OneDrive
   - Seleccione su carpeta de práctica en OneDrive
   - Guarde y espere a que aparezca el ícono de sincronización

3. Verificar la sesión de M365:
   - En la esquina superior derecha de Word, confirme que
     su nombre de usuario aparece correctamente
   - Si aparece "Iniciar sesión", haga clic y autentíquese
     con su cuenta corporativa

4. Alternativa si el problema persiste:
   - Copie el texto del expediente (Ctrl+A, Ctrl+C)
   - Abra el panel de Copilot en Word
   - Pegue el texto directamente en el cuadro de chat de Copilot
     precedido por el prompt
   - Esta modalidad funciona sin depender del acceso contextual
     al documento
```

---

### Problema 2: Copilot en Outlook no muestra el botón "Borrador con Copilot" o la opción no está disponible en la ventana de redacción

**Síntoma:** Al abrir un nuevo correo en Outlook, el botón "Borrador con Copilot" no aparece en la cinta de opciones, o aparece deshabilitado (en gris). El ícono de Copilot no es visible en ninguna parte de la interfaz de Outlook.

**Causa raíz:** Puede deberse a tres causas: (a) la funcionalidad de Copilot no está habilitada en Outlook a nivel de tenant por el administrador de TI, (b) se está usando la versión clásica de Outlook que no soporta todas las funciones de Copilot, o (c) el complemento de Copilot necesita actualizarse.

**Solución paso a paso:**

```
1. Verificar la versión de Outlook:
   - Haga clic en Archivo → Cuenta de Office → Información del producto
   - Confirme que la versión es 2401 o superior
   - Si no, actualice: Archivo → Cuenta de Office →
     Opciones de actualización → Actualizar ahora

2. Verificar si usa "Nuevo Outlook":
   - En la esquina superior derecha de Outlook, busque el
     interruptor "Probar el nuevo Outlook"
   - Active el nuevo Outlook (puede requerir reinicio)
   - Copilot tiene mejor soporte en el Nuevo Outlook

3. Si el problema persiste (limitación de tenant):
   - Use la alternativa en Microsoft Edge:
     a. Abra outlook.office.com en Edge
     b. Haga clic en "Nuevo mensaje"
     c. El botón de Copilot debería aparecer en la versión web
   - Si tampoco aparece en la web, contacte al administrador
     de TI para verificar que Copilot esté habilitado en Outlook
     a nivel de tenant

4. Solución alternativa completa:
   - Genere el borrador del correo usando Copilot en Word
     (panel lateral de Copilot con el prompt de redacción)
   - Copie el texto generado
   - Péguelo manualmente en un nuevo correo de Outlook
   - Esta alternativa produce el mismo resultado de aprendizaje
```

---

## Limpieza del Entorno

Al finalizar el laboratorio, realice los siguientes pasos para mantener el entorno ordenado:

### Archivos generados (conservar para evaluación)

```
Los siguientes archivos deben CONSERVARSE en OneDrive
hasta que el instructor confirme la evaluación del laboratorio:

□ Lab04_Resumen_Ejecutivo_[SusIniciales].docx
□ Lab04_Minuta_Reunion_[SusIniciales].docx
□ Capturas de pantalla de las tarjetas en Planner
□ Capturas de pantalla de los 3 borradores en Outlook
```

### Archivos temporales (pueden eliminarse)

```
□ Cualquier documento Word en blanco creado durante
  el proceso de preparación de datos para Copilot
□ Copias duplicadas de los archivos de práctica originales
□ Notas o documentos de borrador sin nombre
```

### Planner (conservar para referencia)

```
□ Conserve el plan "Cierre Fiscal Q[N] - Auditoría Interna"
  en Planner para referencia durante la sesión de evaluación
□ No elimine las tarjetas de tareas hasta la evaluación
```

### Borradores en Outlook

```
□ Los borradores pueden eliminarse después de la evaluación
□ CONFIRME que ningún correo fue enviado accidentalmente
  revisando la carpeta "Elementos enviados" de Outlook
□ Si encuentra algún correo enviado por error, notifique
  inmediatamente al instructor
```

### Cierre de sesiones

```
□ Cierre los paneles de Copilot en Word y Teams
□ Cierre los documentos de práctica en Word
□ Si está en un equipo compartido, cierre la sesión de
  Microsoft 365 en todas las aplicaciones:
  Inicio → Nombre de usuario → Cerrar sesión
```

---

## Resumen del Laboratorio

### Lo que se practicó en este laboratorio

En este laboratorio de 60 minutos se integraron cuatro aplicaciones de Microsoft 365 Copilot para abordar dos capacidades críticas en entornos de auditoría y cumplimiento fiscal:

**Bloque 1 — Síntesis documental:**
- Se generó un **resumen ejecutivo** de un expediente legal complejo de 15 páginas, reduciendo la información a una página orientada a la toma de decisiones, aplicando la estructura de seis secciones (antecedentes, posición de partes, argumentos, riesgos, estado procesal y recomendación).
- Se automatizó la generación de una **minuta de reunión** estructurada a partir de una transcripción, con tabla de tareas asignadas, responsables, fechas límite y puntos de seguimiento.
- Se aplicó el **ciclo de refinamiento iterativo** (prompt inicial → revisión crítica → ajuste → validación) para mejorar la calidad del output antes de su uso profesional.

**Bloque 2 — Gestión de hitos:**
- Se analizó un plan de trabajo de cierre fiscal para **identificar la ruta crítica**, tareas en riesgo y cuellos de botella, con recomendaciones de acción inmediata.
- Se crearon **tarjetas de tareas en Microsoft Planner** con prioridades, responsables y etiquetas de criticidad.
- Se redactaron **comunicaciones ejecutivas automatizadas** en Outlook: recordatorio de hito, alerta de escalamiento y convocatoria de reunión urgente.

### Conceptos clave reforzados

| Concepto | Aplicación en el laboratorio |
|---|---|
| Prompt con estructura rol + entrada + formato + tono | Pasos 1, 2, 3 y 4 |
| Verificación crítica de outputs de Copilot | Pasos 1.5 y 2.5 |
| Instrucción anti-alucinación [A CONFIRMAR] | Paso 2.2 |
| Refinamiento iterativo de secciones específicas | Pasos 1.4, 2.3 y 4.5 |
| Integración multi-aplicación M365 | Todo el laboratorio |
| Coherencia entre documentos del mismo proyecto | Validación final |

### Reflexión profesional

> 💼 El valor de Copilot no reside en eliminar el criterio profesional, sino en liberar tiempo para ejercerlo donde más importa. Un resumen ejecutivo generado en 30 segundos que requiere 10 minutos de revisión crítica es infinitamente más valioso que uno redactado desde cero en 3 horas sin revisión. La habilidad diferenciadora del profesional del siglo XXI no es la velocidad de escritura, sino la calidad del juicio con el que valida, ajusta y firma los documentos que produce —con o sin asistencia de IA.

### Recursos adicionales recomendados

| Recurso | Descripción | Enlace |
|---|---|---|
| Documentación oficial de Copilot en Word | Capacidades de resumen y redacción | [learn.microsoft.com/es-es/copilot](https://learn.microsoft.com/es-es/copilot/microsoft-365/microsoft-365-copilot-overview) |
| Guía de prompts efectivos para M365 | Microsoft Adoption Hub en español | [adoption.microsoft.com/es-es/copilot](https://adoption.microsoft.com/es-es/copilot/) |
| Copilot en Teams — Resúmenes de reuniones | Documentación de funcionalidades | [learn.microsoft.com — Teams Copilot](https://learn.microsoft.com/es-es/microsoftteams/copilot-teams-transcription) |
| Microsoft Planner — Guía de inicio | Gestión de tareas en M365 | [support.microsoft.com — Planner](https://support.microsoft.com/es-es/planner) |
| Verificación de outputs de IA en contextos legales | Stanford CodeX Center | [codex.stanford.edu](https://codex.stanford.edu) |

---

> 📋 **Próxima sesión:** El Laboratorio 05 aplicará las técnicas de síntesis y comunicación de este laboratorio en el contexto de detección de patrones de riesgo fiscal en conjuntos de datos extensos, integrando Copilot en Excel con Power Query para el análisis de grandes volúmenes de transacciones.

---
LAB_END---
