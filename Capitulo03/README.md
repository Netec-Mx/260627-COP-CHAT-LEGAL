# Automatización en la redacción de contratos, actas y respuestas técnicas a requerimientos de autoridades. Comparación de versiones de documentos y análisis de cláusulas de riesgo con IA. Sesión 3 90 min

## 1. Metadatos

| Atributo | Detalle |
|---|---|
| **Duración total** | 90 minutos (≈ 10 min introducción · 50 min práctica activa · 20 min análisis y discusión · 10 min cierre y limpieza) |
| **Complejidad** | Alta (Hard) |
| **Nivel Bloom** | Aplicar (Apply) |
| **Módulo** | 3 — Automatización Documental Legal y Fiscal con Copilot |
| **Sesión** | Sesión 3 |
| **Archivos requeridos** | `Lab03_Requerimiento_Autoridad.pdf` · `Lab03_Contrato_Servicios_v1.docx` · `Lab03_Contrato_Servicios_v2.docx` · `Lab03_Contrato_Arrendamiento.docx` |

> ⚠️ **Aviso de privacidad:** Todos los documentos de esta práctica son **ficticios**. No cargues información real de clientes, contribuyentes o expedientes legales en Copilot durante este laboratorio.

---

## 2. Descripción General

Este laboratorio aplica las capacidades de Microsoft 365 Copilot en Word para automatizar tres tareas de alto valor en áreas jurídicas y fiscales: (1) redacción de respuestas técnicas formales a requerimientos de autoridades tributarias, (2) comparación sistemática de versiones de contratos para identificar cambios de impacto, y (3) análisis de cláusulas de riesgo en contratos comerciales. El participante trabajará con documentos ficticios representativos de escenarios reales, aplicando técnicas de prompting jurídico-fiscal estructurado aprendidas en los Temas 3.1 y 3.2. Al concluir, habrá generado tres productos documentales completos que demuestran cómo Copilot transforma al profesional jurídico de redactor primario a revisor estratégico.

---

## 3. Objetivos de Aprendizaje

Al finalizar este laboratorio, el participante será capaz de:

- [ ] **Generar** borradores de respuestas técnicas formales a requerimientos de autoridades fiscales utilizando prompts estructurados en Copilot para Word, incluyendo fundamentos normativos y argumentación de fondo.
- [ ] **Redactar** actas corporativas y contratos comerciales mediante instrucciones en lenguaje natural en Copilot, reduciendo el tiempo de escritura inicial y aplicando el marco legal aplicable al contexto del participante.
- [ ] **Comparar** dos versiones de un contrato de servicios utilizando Copilot para generar un informe de cambios con clasificación de impacto (alto / medio / bajo) sobre obligaciones, plazos y condiciones económicas.
- [ ] **Identificar** cláusulas de riesgo en un contrato de arrendamiento comercial mediante análisis asistido por Copilot, distinguiendo penalidades excesivas, ambigüedades jurídicas y ausencias de cláusulas protectoras.
- [ ] **Aplicar** criterio profesional para validar, ajustar y complementar los resultados generados por Copilot antes de utilizarlos en un contexto de práctica legal o fiscal real.

---

## 4. Prerrequisitos

### 4.1 Conocimientos Previos

| Área | Nivel Requerido |
|---|---|
| Microsoft Word (estilos, control de cambios, comentarios) | Básico-Intermedio |
| Marco legal-fiscal local (legislación tributaria y derecho contractual básico) | Básico |
| Contenidos del Tema 3.1: Automatización en la Redacción de Contratos y Respuestas Técnicas | Completado |
| Contenidos del Tema 3.2: Comparación Documental y Análisis de Cláusulas de Riesgo con IA | Completado |
| Uso básico de Copilot en Word (activar panel, escribir prompts) | Básico |

### 4.2 Acceso y Licenciamiento

| Requisito | Estado requerido |
|---|---|
| Cuenta corporativa Microsoft 365 activa | ✅ Activa y con sesión iniciada |
| Licencia **Microsoft 365 Copilot** asignada por TI | ✅ Asignada (verificar con administrador) |
| Copilot habilitado en Microsoft Word (ícono visible en cinta de opciones) | ✅ Visible |
| Archivos de práctica cargados en OneDrive del participante | ✅ Carpeta `Laboratorios/Lab03/` en OneDrive |
| Conexión a internet estable (mínimo 10 Mbps) | ✅ Activa |

> 💡 **Verificación rápida de licencia:** Abre Word → Cinta de opciones → verifica que aparezca el ícono de Copilot (estrella de colores). Si no aparece, contacta al administrador de TI antes de continuar.

---

## 5. Entorno del Laboratorio

### 5.1 Hardware Recomendado

| Componente | Mínimo | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 8ª gen / AMD Ryzen 5 | Intel Core i7 / AMD Ryzen 7 |
| RAM | 8 GB | 16 GB |
| Almacenamiento libre | 10 GB | 20 GB |
| Resolución de pantalla | 1920×1080 | 2560×1440 o doble monitor |
| Conexión a internet | 10 Mbps | 25 Mbps o superior |

### 5.2 Software Requerido

| Aplicación | Versión mínima |
|---|---|
| Microsoft Word (Microsoft 365) | Versión 2401 o superior |
| Microsoft 365 Copilot | Versión de servicio actual (GPT-4 Turbo) |
| Microsoft OneDrive | Versión cloud actual (sincronizado) |
| Adobe Acrobat Reader DC | Versión actual (para visualizar el PDF del requerimiento) |
| Microsoft Edge | Versión 120 o superior |

### 5.3 Configuración Inicial del Entorno

Antes de comenzar los pasos del laboratorio, realiza las siguientes verificaciones:

**Paso A — Verificar archivos en OneDrive:**

1. Abre el explorador de archivos de Windows.
2. Navega a `OneDrive - [Tu organización] > Laboratorios > Lab03`.
3. Confirma que existen los cuatro archivos siguientes:

```
Lab03_Requerimiento_Autoridad.pdf
Lab03_Contrato_Servicios_v1.docx
Lab03_Contrato_Servicios_v2.docx
Lab03_Contrato_Arrendamiento.docx
```

> Si algún archivo falta, solicítalo al instructor antes de continuar. Los archivos deben estar en OneDrive (no solo en disco local) para que Copilot pueda referenciarlos.

**Paso B — Abrir el archivo PDF del requerimiento:**

1. Haz doble clic en `Lab03_Requerimiento_Autoridad.pdf`.
2. Léelo completo (2-3 minutos). Identifica: número de oficio, fecha, autoridad emisora, contribuyente requerido, RFC, observaciones planteadas y plazo de respuesta.
3. Mantén el PDF abierto en segundo plano durante el laboratorio.

**Paso C — Verificar Copilot en Word:**

1. Abre Microsoft Word con un documento en blanco.
2. Confirma que el ícono de Copilot aparece en la cinta de opciones (pestaña **Inicio** o **Copilot**).
3. Haz clic en el ícono para abrir el panel lateral de Copilot y verifica que responde.
4. Cierra el documento en blanco sin guardar.

---

## 6. Instrucciones Paso a Paso

> 📋 **Estructura del laboratorio:**
> - **Bloque 1 (Pasos 1–3):** Redacción automatizada — respuesta técnica a requerimiento y acta corporativa (≈ 25 minutos)
> - **Bloque 2 (Pasos 4–6):** Comparación de versiones y análisis de riesgo contractual (≈ 25 minutos)
> - **Bloque 3 (Paso 7):** Síntesis y refinamiento con criterio profesional (≈ 10 minutos)

---

### Paso 1: Generar el borrador de respuesta técnica al requerimiento fiscal

**Objetivo:** Utilizar Copilot en Word para generar un borrador estructurado y formalmente correcto de respuesta al requerimiento de la autoridad tributaria ficticia, incorporando fundamentos normativos y argumentación de fondo.

#### Instrucciones

1. Abre Microsoft Word. Crea un nuevo documento en blanco.

2. Guarda el documento inmediatamente con el nombre `Lab03_Respuesta_Requerimiento_[TusIniciales].docx` en la carpeta `OneDrive > Laboratorios > Lab03`.

   > Guardarlo en OneDrive desde el inicio asegura que Copilot tenga acceso al contexto del documento y que el versionado en la nube funcione correctamente.

3. Abre el panel de Copilot haciendo clic en el ícono de la cinta de opciones o presionando `Alt + I`.

4. En el panel de Copilot, escribe el siguiente prompt. **Adapta los datos entre corchetes** con la información real del PDF `Lab03_Requerimiento_Autoridad.pdf` que leíste en la configuración inicial:

```
Redacta una respuesta técnica formal al oficio de requerimiento número
[NÚMERO DE OFICIO DEL PDF] emitido por [AUTORIDAD EMISORA] el [FECHA DEL OFICIO],
dirigida al contribuyente [NOMBRE DE LA EMPRESA FICTICIA] con RFC [RFC FICTICIO].

La autoridad observa una diferencia entre los ingresos declarados en el ISR
del ejercicio [AÑO] por $[MONTO DECLARADO] MXN y los ingresos reportados en
los CFDI emitidos por $[MONTO CFDI] MXN. La diferencia de $[DIFERENCIA] MXN
corresponde a anticipos de clientes recibidos en el ejercicio anterior que
fueron acumulados en ese ejercicio conforme al principio de devengado.

Estructura la respuesta con: (1) encabezado formal con datos del contribuyente,
(2) antecedentes del requerimiento, (3) argumentación de fondo fundamentada en
el artículo 17 de la LISR y el artículo 18 del CFF, (4) listado de documentación
anexa propuesta, (5) cierre formal con espacio para firma del representante legal.
Tono formal e institucional. Extensión aproximada: 2 páginas.
```

5. Presiona **Enter** y espera a que Copilot genere el borrador (10–20 segundos aproximadamente).

6. Haz clic en **Insertar** (o el botón equivalente que aparece bajo el texto generado) para insertar el borrador en el documento.

7. Revisa el borrador generado. Identifica y **resalta en amarillo** (usando el resaltado de Word) cualquier dato que Copilot haya completado con información genérica que tú deberás personalizar con los datos reales del PDF ficticio.

8. Ahora solicita a Copilot que refine una sección específica. En el panel de Copilot, escribe:

```
Expande la sección de "Argumentación de Fondo" del documento actual.
Agrega un párrafo adicional que explique el tratamiento contable de los
anticipos de clientes conforme a las NIF (Normas de Información Financiera)
mexicanas y su impacto en la acumulación de ingresos para efectos del ISR.
Mantén el tono formal e institucional.
```

9. Inserta el texto generado en la sección correspondiente del documento.

10. Aplica el estilo **"Título 1"** al encabezado principal y **"Título 2"** a cada sección (Antecedentes, Argumentación, Documentación Anexa, Cierre) utilizando los estilos de Word.

#### Resultado Esperado

Un documento Word de aproximadamente 2 páginas con la estructura completa de una respuesta técnica formal: encabezado institucional, antecedentes del requerimiento, argumentación de fondo con referencias al artículo 17 LISR y artículo 18 CFF, listado de anexos propuestos y cierre con espacio para firma. Los datos ficticios del PDF deben estar correctamente integrados en el texto.

#### Verificación

- [ ] El documento está guardado en `OneDrive > Laboratorios > Lab03` con el nombre correcto.
- [ ] El borrador contiene las 5 secciones estructurales solicitadas.
- [ ] Se identificaron y resaltaron en amarillo al menos 3 campos que requieren personalización.
- [ ] La sección de argumentación incluye referencia explícita al artículo 17 LISR.
- [ ] Se aplicaron estilos de Word (Título 1 y Título 2) a las secciones.

---

### Paso 2: Generar un acta corporativa de asamblea con Copilot

**Objetivo:** Practicar la generación automatizada de un acta corporativa formal a partir de puntos clave, aplicando el patrón de prompt estructurado con tipo de documento, partes, condiciones y marco legal.

#### Instrucciones

1. Crea un nuevo documento Word en blanco. Guárdalo como `Lab03_Acta_Asamblea_[TusIniciales].docx` en `OneDrive > Laboratorios > Lab03`.

2. Abre el panel de Copilot (`Alt + I`) y escribe el siguiente prompt:

```
Redacta el acta de asamblea general extraordinaria de accionistas de
"Distribuidora Comercial Omega S.A. de C.V." celebrada el 20 de junio de 2025
en la Ciudad de México. Asistentes: tres accionistas que representan el 100%
del capital social suscrito y pagado. Preside: el Presidente del Consejo.
Actúa como Secretario: el Director Jurídico.

Orden del día:
1. Aprobación del cambio de domicilio fiscal de la empresa de
   "Av. Insurgentes Sur 1234, Col. Del Valle, CDMX" a
   "Blvd. Manuel Ávila Camacho 567, Col. Lomas de Chapultepec, CDMX".
2. Ratificación de poderes del representante legal ante el SAT.
3. Asuntos generales.

Los tres puntos fueron aprobados por unanimidad. Incluye: encabezado formal,
lista de asistentes con porcentaje de participación, desarrollo de cada punto
del orden del día con los acuerdos tomados, cierre con firmas de Presidente
y Secretario. Formato legal mexicano. Tono formal y jurídico.
```

3. Inserta el texto generado en el documento.

4. Selecciona el texto completo del acta generada. En el panel de Copilot, escribe el siguiente prompt de refinamiento:

```
Revisa el acta insertada en este documento y agrega en el punto 1 del orden
del día una mención explícita al procedimiento de aviso de cambio de domicilio
ante el SAT conforme al artículo 27 del Código Fiscal de la Federación.
Mantén el resto del acta sin cambios.
```

5. Inserta el texto refinado y compara con la versión anterior para verificar la adición.

6. Activa el **Control de cambios** en Word (`Revisar > Control de cambios`) y realiza manualmente las siguientes ediciones para simular una revisión jurídica:
   - Cambia la fecha de la asamblea de "20 de junio" a "25 de junio de 2025".
   - Agrega en el punto 3 de Asuntos Generales: *"Se instruyó al Director Jurídico para iniciar el trámite de cambio de domicilio ante el RFC en un plazo no mayor a 5 días hábiles."*

7. Acepta todos los cambios (`Revisar > Aceptar > Aceptar todos los cambios`) y desactiva el Control de cambios.

#### Resultado Esperado

Un acta corporativa completa de 1–2 páginas con estructura legal formal mexicana, incluyendo la referencia al artículo 27 del CFF en el punto de cambio de domicilio fiscal, y con las ediciones manuales de revisión jurídica incorporadas.

#### Verificación

- [ ] El acta incluye encabezado formal, lista de asistentes y porcentajes de participación.
- [ ] El punto 1 contiene referencia explícita al artículo 27 del CFF.
- [ ] La fecha de asamblea refleja el cambio manual a "25 de junio de 2025".
- [ ] El punto 3 incluye la instrucción al Director Jurídico con plazo de 5 días hábiles.
- [ ] El documento está guardado en OneDrive sin cambios pendientes de aceptar.

---

### Paso 3: Generar un contrato de arrendamiento comercial desde cero

**Objetivo:** Aplicar el modelo de prompt de cuatro elementos (tipo de documento, partes, condiciones clave, jurisdicción) para generar un contrato completo que sirva como referencia de comparación en el Bloque 2.

#### Instrucciones

1. Crea un nuevo documento Word en blanco. Guárdalo como `Lab03_Contrato_Arrendamiento_Generado_[TusIniciales].docx` en `OneDrive > Laboratorios > Lab03`.

2. En el panel de Copilot, escribe el siguiente prompt estructurado:

```
Redacta un contrato de arrendamiento de local comercial con las siguientes
características:

TIPO DE DOCUMENTO: Contrato de arrendamiento de inmueble para uso comercial.

PARTES:
- Arrendador: "Inmobiliaria Cenit S.A. de C.V." (persona moral, propietaria
  del inmueble), representada por su Director General.
- Arrendatario: "Retail Express S.A. de C.V." (persona moral), representada
  por su Apoderado Legal.

CONDICIONES CLAVE:
- Inmueble: Local comercial de 250 m² ubicado en Plaza Comercial Norte,
  Local B-12, Ciudad de México.
- Renta mensual: $85,000 MXN más IVA.
- Depósito en garantía: equivalente a 2 meses de renta ($170,000 MXN).
- Vigencia: 3 años (36 meses) a partir del 1 de julio de 2025.
- Uso permitido: exclusivamente para venta al menudeo de artículos de ropa
  y accesorios.
- Incremento anual de renta: conforme al INPC publicado por el INEGI.

CLÁUSULAS REQUERIDAS: objeto del contrato, obligaciones del arrendador,
obligaciones del arrendatario, renta y forma de pago, depósito en garantía,
mantenimiento y reparaciones, subarrendamiento (prohibido), rescisión,
penalidades por incumplimiento, jurisdicción y ley aplicable.

JURISDICCIÓN: Código Civil del Distrito Federal (Ciudad de México) y
legislación local aplicable. Tono formal y jurídico.
```

3. Inserta el contrato generado en el documento.

4. Aplica estilos de Word: **Título 1** para el encabezado del contrato, **Título 2** para cada cláusula numerada.

5. Guarda el documento. Lo utilizarás como referencia en el Paso 5 (análisis de cláusulas de riesgo).

#### Resultado Esperado

Un contrato de arrendamiento comercial de 3–5 páginas con al menos 10 cláusulas, estructura jurídica formal, datos de las partes ficticias, condiciones económicas especificadas y referencia a la legislación aplicable del Distrito Federal / Ciudad de México.

#### Verificación

- [ ] El contrato contiene al menos 10 cláusulas numeradas.
- [ ] Se incluye cláusula de rescisión con causales explícitas.
- [ ] Se incluye cláusula de penalidades por incumplimiento.
- [ ] El incremento anual de renta referencia el INPC del INEGI.
- [ ] Los estilos Título 1 y Título 2 están aplicados correctamente.

---

### Paso 4: Comparar versiones del contrato de servicios con Copilot

**Objetivo:** Utilizar Copilot para comparar sistemáticamente las versiones 1.0 y 2.0 del contrato de servicios ficticio y generar un informe de cambios con clasificación de impacto, enfocado en modificaciones que afecten obligaciones, plazos y condiciones económicas.

#### Instrucciones

1. Abre el archivo `Lab03_Contrato_Servicios_v1.docx` desde `OneDrive > Laboratorios > Lab03`.

2. Tómate 3 minutos para leer el contrato v1.0 completo. Identifica mentalmente: partes, objeto, monto de honorarios, vigencia, cláusulas de confidencialidad y rescisión.

3. Abre el archivo `Lab03_Contrato_Servicios_v2.docx` en una segunda ventana de Word.

4. Utiliza la función nativa de comparación de Word:
   - En el documento v2.0, ve a `Revisar > Comparar > Comparar...`
   - En **Documento original**, selecciona `Lab03_Contrato_Servicios_v1.docx`.
   - En **Documento revisado**, confirma que está seleccionado `Lab03_Contrato_Servicios_v2.docx`.
   - Haz clic en **Aceptar**.
   - Word generará un tercer documento con todos los cambios marcados. Guárdalo como `Lab03_Comparacion_Contratos_[TusIniciales].docx` en `OneDrive > Laboratorios > Lab03`.

5. Con el documento de comparación abierto, activa el panel de Copilot y escribe el siguiente prompt:

```
Analiza el documento actual que contiene la comparación entre dos versiones
de un contrato de prestación de servicios. Identifica y clasifica todos los
cambios detectados según su nivel de impacto:

🔴 ALTO: Cambios que modifican montos económicos, plazos de vigencia,
   causales de rescisión, responsabilidades o penalidades.
🟡 MEDIO: Cambios que modifican procedimientos, notificaciones, definiciones
   o condiciones secundarias.
🟢 BAJO: Cambios de redacción, estilo o correcciones menores sin impacto
   sustancial.

Para cada cambio identificado, indica: (1) número de cláusula afectada,
(2) descripción del cambio, (3) nivel de impacto con justificación,
(4) recomendación para la parte que negocia el contrato.

Presenta el resultado en formato de tabla.
```

6. Inserta la tabla generada por Copilot al final del documento de comparación.

7. Ahora solicita un resumen ejecutivo. En el panel de Copilot, escribe:

```
Con base en el análisis de cambios del documento actual, redacta un
resumen ejecutivo de máximo 200 palabras dirigido al Director Jurídico
de la empresa cliente. El resumen debe destacar: (1) cuántos cambios de
impacto alto se identificaron, (2) cuál es el cambio más crítico y por qué,
(3) recomendación de acción antes de firmar la versión 2.0 del contrato.
Tono profesional y directo.
```

8. Inserta el resumen ejecutivo al inicio del documento de comparación (antes de la tabla de cambios).

9. Guarda el documento.

#### Resultado Esperado

Un documento de comparación que contiene: (a) el control de cambios nativo de Word mostrando todas las modificaciones entre v1.0 y v2.0, (b) una tabla generada por Copilot clasificando cada cambio con semáforo de impacto (🔴/🟡/🟢) y recomendaciones, y (c) un resumen ejecutivo de máximo 200 palabras para el Director Jurídico.

#### Verificación

- [ ] El documento de comparación fue generado correctamente con la función `Revisar > Comparar` de Word.
- [ ] La tabla de Copilot contiene al menos 3 cambios clasificados en diferentes niveles de impacto.
- [ ] Cada fila de la tabla incluye: cláusula, descripción del cambio, nivel de impacto con justificación y recomendación.
- [ ] El resumen ejecutivo no supera 200 palabras y menciona el cambio más crítico.
- [ ] El documento está guardado en OneDrive.

---

### Paso 5: Analizar cláusulas de riesgo en el contrato de arrendamiento

**Objetivo:** Aplicar Copilot para realizar un análisis sistemático de riesgo jurídico y fiscal sobre el contrato de arrendamiento ficticio provisto, identificando cláusulas problemáticas, ambigüedades y ausencias de protecciones clave.

#### Instrucciones

1. Abre el archivo `Lab03_Contrato_Arrendamiento.docx` desde `OneDrive > Laboratorios > Lab03`.

   > Este es el contrato **provisto por el instructor**, diferente al que generaste en el Paso 3. Contiene intencionalmente cláusulas problemáticas para el ejercicio de análisis.

2. Lee el contrato completo (5 minutos). Mientras lees, anota mentalmente cualquier cláusula que te parezca inusual, ambigua o potencialmente desfavorable.

3. Activa el panel de Copilot y escribe el siguiente prompt de análisis de riesgo:

```
Analiza el contrato de arrendamiento en este documento desde la perspectiva
de la parte arrendataria (inquilino). Identifica:

1. PENALIDADES EXCESIVAS: Cláusulas que impongan penalidades
   desproporcionadas o sin límite claro.
2. AUSENCIA DE CLÁUSULAS PROTECTORAS: Cláusulas que deberían estar presentes
   para proteger al arrendatario y no se encuentran en el contrato
   (por ejemplo: cláusula de rescisión anticipada sin penalidad por causa
   justificada, cláusula de mantenimiento mayor a cargo del arrendador,
   cláusula de renovación preferente).
3. AMBIGÜEDADES JURÍDICAS: Redacción vaga o imprecisa que pueda interpretarse
   de forma desfavorable para el arrendatario.
4. EXPOSICIÓN FISCAL: Cláusulas que puedan generar contingencias fiscales
   para el arrendatario (IVA, ISR, retenciones, CFDI).
5. DESEQUILIBRIO CONTRACTUAL: Obligaciones o derechos que favorezcan
   desproporcionadamente al arrendador.

Para cada hallazgo: indica el número de cláusula, cita el texto problemático,
explica el riesgo y propón una redacción alternativa o cláusula correctiva.
Presenta en formato estructurado con encabezados por categoría.
```

4. Inserta el análisis generado en un nuevo documento Word. Guárdalo como `Lab03_Analisis_Riesgo_Arrendamiento_[TusIniciales].docx` en `OneDrive > Laboratorios > Lab03`.

5. Ahora profundiza en el análisis fiscal. En el panel de Copilot, escribe:

```
Del análisis anterior, enfócate específicamente en la exposición fiscal
del arrendatario. Explica:
(a) Cuáles son las obligaciones de retención de ISR aplicables al
    arrendamiento de locales comerciales entre personas morales en México.
(b) Si el contrato actual incluye o debería incluir cláusulas sobre la
    emisión de CFDI por parte del arrendador.
(c) Qué riesgos genera para el arrendatario la ausencia de estas cláusulas
    fiscales en el contrato.
Fundamenta en la LISR y la LIVA vigentes.
```

6. Inserta esta sección como un apartado adicional titulado **"Análisis de Exposición Fiscal"** en el documento de análisis de riesgo.

7. Utilizando los **Comentarios de Word** (`Insertar > Comentario` o `Ctrl + Alt + M`), agrega al menos 3 comentarios en el documento de análisis señalando los hallazgos que consideras más críticos desde tu propio criterio profesional. Cada comentario debe incluir tu razonamiento personal sobre por qué ese riesgo es prioritario.

   > Este paso es crucial: Copilot genera el análisis técnico, pero tu criterio profesional determina qué es verdaderamente prioritario en el contexto específico del cliente o caso.

8. Guarda el documento con los comentarios.

#### Resultado Esperado

Un documento de análisis de riesgo de 3–5 páginas que contiene: (a) análisis estructurado por categorías (penalidades, ausencias, ambigüedades, exposición fiscal, desequilibrio), (b) sección específica de análisis de exposición fiscal con fundamentos normativos (LISR y LIVA), y (c) al menos 3 comentarios del participante que reflejan criterio profesional propio sobre los riesgos prioritarios identificados.

#### Verificación

- [ ] El análisis cubre las 5 categorías de riesgo solicitadas.
- [ ] Cada hallazgo incluye: número de cláusula, texto problemático, explicación del riesgo y redacción alternativa propuesta.
- [ ] La sección de exposición fiscal menciona obligaciones de retención ISR entre personas morales.
- [ ] La sección fiscal referencia la LISR y la LIVA.
- [ ] El documento contiene al menos 3 comentarios del participante con criterio profesional propio.
- [ ] El documento está guardado en OneDrive.

---

### Paso 6: Comparar el contrato provisto con el contrato generado por Copilot

**Objetivo:** Utilizar Copilot para comparar el contrato de arrendamiento provisto (con cláusulas problemáticas) contra el contrato que el participante generó en el Paso 3, identificando las diferencias en calidad de protecciones y estructura.

#### Instrucciones

1. Abre ambos documentos en ventanas separadas de Word:
   - `Lab03_Contrato_Arrendamiento.docx` (provisto por instructor — con problemas)
   - `Lab03_Contrato_Arrendamiento_Generado_[TusIniciales].docx` (generado en Paso 3)

2. Activa el panel de Copilot en el documento generado por ti y escribe:

```
Tengo dos contratos de arrendamiento comercial. El documento actual es
el contrato que generé con Copilot. El otro contrato (Lab03_Contrato_Arrendamiento.docx)
es la versión con cláusulas problemáticas analizada anteriormente.

Compara ambos contratos y genera una tabla que muestre:
- Cláusulas presentes en mi contrato generado pero ausentes en el contrato
  problemático (protecciones que faltan en el contrato problemático).
- Cláusulas presentes en el contrato problemático pero ausentes o mejor
  redactadas en mi contrato generado.
- Evaluación general: ¿cuál contrato ofrece mejor protección al arrendatario
  y por qué?

Sé específico y cita las cláusulas por nombre o número.
```

   > **Nota:** Copilot puede no tener acceso directo al otro archivo si no está abierto en la misma sesión. Si el prompt no funciona con referencia al otro archivo, copia y pega el texto del contrato problemático en un documento temporal y ajusta el prompt para que analice "el siguiente texto de contrato" seguido del contenido pegado.

3. Inserta la tabla comparativa en el documento de análisis de riesgo (`Lab03_Analisis_Riesgo_Arrendamiento_[TusIniciales].docx`) como sección final titulada **"Comparativa: Contrato Problemático vs. Contrato Modelo"**.

4. Guarda el documento.

#### Resultado Esperado

Una tabla comparativa final que evidencia las diferencias en calidad de protecciones entre ambos contratos, con evaluación argumentada de cuál ofrece mejor protección al arrendatario.

#### Verificación

- [ ] La tabla comparativa identifica al menos 4 diferencias entre ambos contratos.
- [ ] La evaluación general incluye argumentación específica (no solo "el contrato A es mejor").
- [ ] La tabla fue insertada en el documento de análisis de riesgo existente.

---

### Paso 7: Síntesis final — Generación del informe ejecutivo consolidado

**Objetivo:** Integrar los productos generados en los pasos anteriores en un informe ejecutivo consolidado que demuestre el flujo completo de trabajo asistido por Copilot para un área jurídica o fiscal.

#### Instrucciones

1. Crea un nuevo documento Word. Guárdalo como `Lab03_Informe_Ejecutivo_[TusIniciales].docx` en `OneDrive > Laboratorios > Lab03`.

2. En el panel de Copilot, escribe el siguiente prompt para generar la estructura del informe:

```
Redacta la estructura de un informe ejecutivo de 1 página para el
Director General de "Distribuidora Comercial Omega S.A. de C.V." que
resume los hallazgos de la revisión jurídica y fiscal realizada. El informe
debe incluir:

1. RESUMEN EJECUTIVO: Situación actual de la empresa en materia de
   cumplimiento documental (requerimiento fiscal pendiente de respuesta,
   contratos en revisión).
2. HALLAZGOS PRINCIPALES:
   - Requerimiento del SAT: diferencia de $700,000 MXN en ingresos ISR 2023
     — acción recomendada: respuesta formal en plazo.
   - Contrato de servicios v2.0: [X] cambios identificados, [Y] de impacto alto
     — acción recomendada: renegociar cláusula [número].
   - Contrato de arrendamiento: [Z] riesgos identificados, exposición fiscal
     por ausencia de cláusulas CFDI — acción recomendada: solicitar addendum.
3. ACCIONES INMEDIATAS: Lista priorizada de los 3 pasos más urgentes.
4. PRÓXIMOS PASOS: Cronograma sugerido de las siguientes 2 semanas.

Completa los datos entre corchetes con estimaciones razonables basadas en
los análisis típicos de este tipo de documentos. Tono ejecutivo, directo
y orientado a decisiones.
```

3. Inserta el informe generado. Personaliza los datos entre corchetes con los hallazgos reales que obtuviste en tus análisis de los pasos anteriores.

4. Aplica formato profesional:
   - **Título principal:** Estilo "Título 1"
   - **Secciones:** Estilo "Título 2"
   - Inserta una tabla de "Acciones Inmediatas" con columnas: Acción | Responsable | Plazo | Prioridad.
   - Agrega número de página en el pie de página.

5. Guarda el documento final.

#### Resultado Esperado

Un informe ejecutivo de 1 página, con formato profesional, que integra los hallazgos de los tres escenarios trabajados durante el laboratorio (requerimiento fiscal, comparación de contratos, análisis de riesgo), con acciones concretas y cronograma sugerido.

#### Verificación

- [ ] El informe tiene máximo 1 página (ajusta el tamaño de fuente o márgenes si es necesario).
- [ ] Los datos entre corchetes fueron personalizados con hallazgos reales del laboratorio.
- [ ] La tabla de acciones inmediatas contiene al menos 3 filas con responsable, plazo y prioridad.
- [ ] El documento tiene número de página en el pie.
- [ ] El tono es ejecutivo y orientado a decisiones (no técnico-jurídico).

---

## 7. Validación y Pruebas

Al finalizar todos los pasos, verifica que los siguientes entregables estén completos y guardados en `OneDrive > Laboratorios > Lab03`:

| # | Archivo | Contenido esperado | Estado |
|---|---|---|---|
| 1 | `Lab03_Respuesta_Requerimiento_[TusIniciales].docx` | Respuesta técnica formal al SAT con 5 secciones estructurales y fundamentos LISR/CFF | ☐ |
| 2 | `Lab03_Acta_Asamblea_[TusIniciales].docx` | Acta corporativa con referencia al Art. 27 CFF y ediciones de revisión jurídica | ☐ |
| 3 | `Lab03_Contrato_Arrendamiento_Generado_[TusIniciales].docx` | Contrato de arrendamiento generado con Copilot, 10+ cláusulas, estilos aplicados | ☐ |
| 4 | `Lab03_Comparacion_Contratos_[TusIniciales].docx` | Comparación v1.0 vs v2.0 con tabla de semáforo de impacto y resumen ejecutivo | ☐ |
| 5 | `Lab03_Analisis_Riesgo_Arrendamiento_[TusIniciales].docx` | Análisis de riesgo con 5 categorías, exposición fiscal, comentarios profesionales y tabla comparativa | ☐ |
| 6 | `Lab03_Informe_Ejecutivo_[TusIniciales].docx` | Informe ejecutivo consolidado de 1 página con tabla de acciones y cronograma | ☐ |

### Prueba de Calidad de Prompts

Reflexiona sobre las siguientes preguntas de autoevaluación (no hay respuestas únicas correctas):

1. **¿El borrador de respuesta al SAT generado por Copilot podría presentarse directamente a la autoridad sin revisión adicional?** — ¿Por qué sí o por qué no? ¿Qué elementos requieren validación profesional obligatoria?

2. **¿Los artículos normativos citados por Copilot (Art. 17 LISR, Art. 27 CFF, etc.) corresponden efectivamente a lo que se afirma?** — Verifica al menos uno de ellos en el texto oficial de la ley. Este ejercicio ilustra la importancia de la validación del criterio profesional sobre las respuestas de la IA.

3. **¿El análisis de cláusulas de riesgo generado por Copilot capturó todos los problemas que identificaste en tu lectura inicial del contrato?** — ¿Hay riesgos que la IA omitió y que tu criterio profesional detectó?

---

## 8. Resolución de Problemas

### Problema 1: El ícono de Copilot no aparece en la cinta de opciones de Word

**Síntoma:** Al abrir Microsoft Word, no se visualiza el ícono de Copilot en la cinta de opciones ni en la pestaña "Inicio". El atajo `Alt + I` tampoco abre el panel.

**Causa probable:** La licencia de Microsoft 365 Copilot no está correctamente asignada al usuario en el tenant de la organización, o la función de Copilot en Word está deshabilitada a nivel de políticas del tenant por el administrador de TI. También puede deberse a una versión de Word desactualizada (anterior a la versión 2401).

**Solución:**

1. Verifica la versión de Word: `Archivo > Cuenta > Acerca de Word`. Confirma que la versión es 2401 o superior. Si no, actualiza: `Archivo > Cuenta > Opciones de actualización > Actualizar ahora`.
2. Verifica tu licencia: abre [https://portal.microsoft.com](https://portal.microsoft.com) en Edge, inicia sesión con tu cuenta corporativa, ve a `Mi cuenta > Suscripciones` y confirma que aparece "Microsoft 365 Copilot" como licencia asignada.
3. Si la licencia está asignada pero el ícono no aparece, cierra Word completamente, espera 2 minutos y vuelve a abrirlo (el aprovisionamiento de licencias puede tardar hasta 24 horas en propagarse).
4. Si el problema persiste, contacta al administrador de TI para verificar que Copilot esté habilitado en las políticas del tenant para la aplicación Word específicamente (`Microsoft 365 Admin Center > Settings > Copilot`).
5. Como alternativa temporal durante el laboratorio, puedes usar **Copilot en Microsoft 365 Chat** ([https://m365.cloud.microsoft/chat](https://m365.cloud.microsoft/chat)) para generar los textos y luego copiarlos manualmente a Word.

---

### Problema 2: Copilot genera texto con artículos normativos incorrectos o inexistentes

**Síntoma:** Al revisar el borrador generado por Copilot para la respuesta al requerimiento o el análisis de riesgo, se detecta que los artículos citados (por ejemplo, "Artículo 17 de la LISR" o "Artículo 27 del CFF") no corresponden exactamente al contenido descrito, o Copilot cita artículos que no existen en la versión vigente de la ley.

**Causa probable:** Los modelos de lenguaje generativo como Copilot pueden producir "alucinaciones" (hallucinations) — referencias normativas plausibles pero incorrectas — especialmente cuando la legislación ha sido reformada recientemente o cuando el modelo no tiene acceso en tiempo real al texto oficial actualizado de la ley. Este es un riesgo conocido y documentado en el uso de IA para tareas jurídicas.

**Solución:**

1. **Nunca uses referencias normativas de Copilot sin verificación independiente.** Esta es una regla de oro en el uso de IA para trabajo jurídico-fiscal.
2. Verifica cada artículo citado directamente en la fuente oficial:
   - **México:** [https://www.diputados.gob.mx/LeyesBiblio/](https://www.diputados.gob.mx/LeyesBiblio/) (LISR, CFF, LIVA)
   - **Ecuador:** [https://www.sri.gob.ec/normativa](https://www.sri.gob.ec/normativa)
   - **Perú:** [https://www.sunat.gob.pe/legislacion/](https://www.sunat.gob.pe/legislacion/)
   - **Colombia:** [https://www.dian.gov.co/normatividad/](https://www.dian.gov.co/normatividad/)
3. Si encuentras un artículo incorrecto, usa Copilot para corregirlo con un prompt específico: `"El artículo que citas no corresponde al contenido descrito. El fundamento correcto para [tema] es el artículo [número correcto] de [ley]. Reescribe el párrafo de argumentación usando el artículo correcto."` Esto demuestra cómo el profesional mantiene el control del criterio jurídico.
4. Documenta los errores encontrados como parte del ejercicio de reflexión crítica del laboratorio — esta experiencia refuerza el concepto de que Copilot es un asistente que requiere supervisión profesional, no una fuente de autoridad jurídica autónoma.

---

## 9. Limpieza del Entorno

Al finalizar el laboratorio, realiza las siguientes acciones de limpieza:

1. **Cierra todos los documentos de Word** guardando los cambios finales en cada uno.

2. **Verifica la sincronización con OneDrive:**
   - Confirma que el ícono de OneDrive en la barra de tareas muestra una nube con palomita verde (sincronización completa).
   - Si hay archivos pendientes de sincronizar, espera a que completen antes de cerrar sesión.

3. **Organiza la carpeta de OneDrive:**
   - Todos los archivos de entregables deben estar en `OneDrive > Laboratorios > Lab03`.
   - Elimina cualquier documento temporal o en blanco que hayas creado durante la práctica.

4. **Cierra el panel de Copilot** en Word si permanece abierto.

5. **No compartas ni envíes por correo** los archivos generados fuera del entorno de aprendizaje. Recuerda que contienen datos ficticios diseñados exclusivamente para este laboratorio.

6. **Cierra sesión de Microsoft 365** si estás en una computadora compartida o de laboratorio público: `Inicio de Windows > tu nombre de usuario > Cerrar sesión`.

---

## 10. Resumen

### Lo que aprendiste en este laboratorio

En este laboratorio de 90 minutos aplicaste Microsoft 365 Copilot en Word para transformar tres flujos de trabajo críticos en áreas jurídicas y fiscales:

| Tarea realizada | Técnica aplicada | Valor generado |
|---|---|---|
| Respuesta técnica al SAT | Prompting estructurado con contexto normativo | Borrador formal listo para revisión en < 2 minutos |
| Acta corporativa de asamblea | Prompt con 4 elementos (tipo, partes, condiciones, jurisdicción) | Documento legal completo con fundamento CFF |
| Contrato de arrendamiento desde cero | Prompt detallado con cláusulas requeridas | Contrato de 10+ cláusulas con estructura jurídica formal |
| Comparación de versiones contractuales | Función Comparar de Word + análisis Copilot | Tabla de semáforo de impacto y resumen ejecutivo |
| Análisis de cláusulas de riesgo | Prompt de análisis multi-categoría | Identificación de riesgos con redacciones alternativas |
| Informe ejecutivo consolidado | Prompt de síntesis ejecutiva | Documento de 1 página orientado a decisiones |

### Principios Clave Reforzados

- **Copilot como acelerador, no como sustituto:** El profesional jurídico aporta el contexto, los hechos y el criterio; Copilot transforma esos insumos en texto estructurado de alta calidad en segundos.
- **La calidad del prompt determina la calidad del output:** Prompts con tipo de documento, partes, condiciones y marco legal producen resultados significativamente superiores a instrucciones genéricas.
- **La validación normativa es no negociable:** Toda referencia legal generada por Copilot debe verificarse en la fuente oficial antes de usarse en un contexto real.
- **El criterio profesional agrega valor irreemplazable:** Los comentarios que añadiste en el Paso 5 y las ediciones manuales del Paso 2 representan el juicio profesional que ninguna IA puede replicar completamente.

### Recursos Adicionales

| Recurso | URL |
|---|---|
| Documentación oficial Copilot en Word | [https://support.microsoft.com/es-es/topic/bienvenido-a-copilot-en-word-2135e85f](https://support.microsoft.com/es-es/topic/bienvenido-a-copilot-en-word-2135e85f) |
| Código Fiscal de la Federación (México) | [https://www.diputados.gob.mx/LeyesBiblio/pdf/CFF.pdf](https://www.diputados.gob.mx/LeyesBiblio/pdf/CFF.pdf) |
| Ley del ISR (México) | [https://www.diputados.gob.mx/LeyesBiblio/pdf/LISR.pdf](https://www.diputados.gob.mx/LeyesBiblio/pdf/LISR.pdf) |
| Galería de prompts de Microsoft Copilot | [https://adoption.microsoft.com/es-es/copilot-scenario-library/](https://adoption.microsoft.com/es-es/copilot-scenario-library/) |
| Centro de adopción Microsoft 365 Copilot | [https://adoption.microsoft.com/es-es/copilot/](https://adoption.microsoft.com/es-es/copilot/) |

> 🎯 **Preparación para el siguiente laboratorio:** En el Lab 04, aplicarás Copilot en Excel para análisis de datos fiscales y detección de patrones de riesgo en grandes volúmenes de transacciones. Asegúrate de tener los archivos del Lab 04 cargados en OneDrive antes de la próxima sesión.

---

*Guía de laboratorio generada para uso exclusivo en el programa de formación. Todos los casos, empresas, RFC y datos utilizados son ficticios y no representan a personas físicas o morales reales.*
