# Uso de Copilot para la detección temprana de riesgos y patrones de fraude. Generación de fórmulas complejas en Excel para validación masiva de datos y automatización de reportes de hallazgos. Sesión 1 60 min

---

## 1. Metadatos

| Atributo | Detalle |
|---|---|
| **Duración total** | 60 minutos (50 min práctica activa + 10 min revisión y cierre) |
| **Complejidad** | Media |
| **Nivel Bloom** | Aplicar (*Apply*) |
| **Módulo** | Capítulo 1 — Auditoría Inteligente con Microsoft 365 Copilot |
| **Sesión** | Sesión 1 |
| **Modalidad** | Individual con guía paso a paso |

---

## 2. Descripción General

En este laboratorio aplicarás Microsoft 365 Copilot integrado en Excel para analizar un conjunto de datos transaccionales ficticio de 500+ registros que simula el libro de pagos a proveedores de una empresa mediana. Utilizarás técnicas de prompting analítico para identificar señales de alerta de fraude —transacciones duplicadas, pagos fraccionados (*smurfing*), proveedores con nombres similares y concentración inusual de operaciones— y solicitarás a Copilot la generación de fórmulas avanzadas para validación masiva. Al finalizar, Copilot te asistirá en estructurar un reporte ejecutivo de hallazgos directamente desde Excel, aplicando el flujo de trabajo **consulta → análisis → documentación** estudiado en la Lección 1.1.

> **⚠️ Aviso de privacidad:** Todos los archivos utilizados en este laboratorio son **ficticios**. No cargues datos reales de clientes, contribuyentes o expedientes durante la práctica.

---

## 3. Objetivos de Aprendizaje

Al completar este laboratorio serás capaz de:

- [ ] **Formular prompts analíticos efectivos** en Copilot dentro de Excel para identificar patrones anómalos en datos transaccionales (duplicados, outliers, proveedores similares).
- [ ] **Generar y aplicar fórmulas complejas** (XLOOKUP, SUMAR.SI.CONJUNTO, CONTAR.SI.CONJUNTO, PERCENTIL, DESVEST, FILTRAR) con asistencia de Copilot para validación masiva de datos financieros.
- [ ] **Interpretar y validar** los resultados que Copilot devuelve, aplicando criterio profesional para distinguir hallazgos accionables de falsos positivos.
- [ ] **Estructurar un reporte básico de hallazgos** de auditoría con tabla resumen y clasificación de riesgo utilizando Copilot como asistente de redacción dentro de Excel.

---

## 4. Prerrequisitos

### 4.1 Conocimientos Previos

| Área | Nivel Requerido |
|---|---|
| Microsoft Excel (tablas, filtros, fórmulas básicas: SUMA, SI, BUSCARV) | Básico-Intermedio |
| Conceptos de auditoría: señales de alerta (*red flags*), patrones de fraude | Básico (cubierto en Lección 1.1) |
| Navegación general en Microsoft 365 | Básico |

### 4.2 Acceso y Recursos

- [ ] Cuenta corporativa de Microsoft 365 con **licencia Copilot activa y verificada** (confirmar con el administrador de TI antes del laboratorio).
- [ ] Archivo **`Lab01_Transacciones_Auditoria.xlsx`** descargado y guardado en la carpeta **`Documentos > Laboratorios_Copilot`** de tu **OneDrive personal** (no en el escritorio local).
- [ ] Ícono de Copilot visible en la pestaña **Inicio** o **Vista** de la cinta de opciones de Excel.
- [ ] Conexión a internet estable (mínimo 10 Mbps).
- [ ] Microsoft Edge versión 120 o superior como navegador predeterminado.

> **💡 Nota del instructor:** Verificar que todos los participantes tengan el archivo en OneDrive y que Copilot esté habilitado en el tenant **al menos 48 horas antes** de la sesión.

---

## 5. Entorno de Laboratorio

### 5.1 Especificaciones de Hardware

| Componente | Mínimo Requerido | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 8ª gen / AMD Ryzen 5 | Intel Core i7 / AMD Ryzen 7 |
| Memoria RAM | 8 GB | 16 GB |
| Almacenamiento libre | 10 GB | 20 GB |
| Resolución de pantalla | 1920 × 1080 | 2560 × 1440 o doble monitor |
| Conexión a internet | 10 Mbps | 25 Mbps |

### 5.2 Especificaciones de Software

| Software | Versión Requerida |
|---|---|
| Microsoft 365 Apps for Enterprise | Canal mensual actualizado |
| Microsoft Excel | Versión 2401 o superior |
| Microsoft 365 Copilot | Servicio actual (GPT-4 Turbo) |
| Microsoft OneDrive | Versión cloud actual (sincronizado) |
| Microsoft Edge | Versión 120 o superior |
| Adobe Acrobat Reader DC | Versión actual (para referencia de normativa) |

### 5.3 Preparación del Entorno (antes de iniciar los pasos)

Realiza las siguientes verificaciones en orden antes de comenzar la práctica:

**Paso de preparación A — Verificar sincronización de OneDrive:**
1. Abre el **Explorador de archivos** de Windows.
2. Navega a `OneDrive - [Tu Organización] > Documentos > Laboratorios_Copilot`.
3. Confirma que el archivo `Lab01_Transacciones_Auditoria.xlsx` muestra el ícono de nube verde ✅ (sincronizado).

> Si el ícono muestra una nube con flecha ↑, espera a que termine la sincronización antes de continuar.

**Paso de preparación B — Verificar Copilot en Excel:**
1. Abre `Lab01_Transacciones_Auditoria.xlsx` haciendo doble clic desde el Explorador de archivos (esto lo abre desde OneDrive sincronizado).
2. En la cinta de opciones, ve a la pestaña **Inicio**.
3. Confirma que el botón **Copilot** (ícono de estrella/chispa con el texto "Copilot") es visible en el extremo derecho de la cinta.
4. Haz clic en el botón **Copilot** para abrir el panel lateral.
5. Verifica que el panel muestre el campo de texto *"Pregúntame cualquier cosa sobre estos datos"* o similar.

> **⚠️ Si no ves el botón Copilot:** Consulta la sección de **Solución de Problemas** al final de esta guía antes de continuar.

**Paso de preparación C — Verificar estructura del archivo de práctica:**

El archivo `Lab01_Transacciones_Auditoria.xlsx` debe contener las siguientes hojas y columnas:

| Hoja | Columnas Principales |
|---|---|
| `Transacciones` | ID_Transaccion, Fecha, Proveedor, RFC_Proveedor, Concepto, Monto, Cuenta_Destino, Usuario_Registro, Tipo_Pago |
| `Catalogo_Proveedores` | RFC_Proveedor, Nombre_Oficial, Estado_Proveedor, Fecha_Alta |
| `Reporte_Hallazgos` | (hoja en blanco para usar en el Paso 4) |

> Si alguna hoja o columna no coincide, notifica al instructor antes de continuar.

---

## 6. Pasos del Laboratorio

### Bloque 1: Detección de Riesgos y Patrones de Fraude con Copilot (30 minutos)

---

### Paso 1: Exploración Inicial del Dataset con Copilot

**Objetivo:** Familiarizarte con el dataset y obtener un diagnóstico general de la calidad de los datos utilizando prompts exploratorios en Copilot.

**Instrucciones:**

1. Asegúrate de estar en la hoja **`Transacciones`** del archivo `Lab01_Transacciones_Auditoria.xlsx`.

2. Haz clic en cualquier celda dentro de la tabla de datos (por ejemplo, celda `B2`).

3. Abre el panel de **Copilot** haciendo clic en el botón de la cinta de opciones (pestaña **Inicio > Copilot**).

4. En el campo de texto del panel de Copilot, escribe el siguiente prompt y presiona **Enter** o haz clic en el botón de enviar:

   ```
   Describe brevemente la estructura de esta tabla. Indica cuántos registros contiene,
   el rango de fechas de las transacciones, el rango de montos (mínimo, máximo y promedio),
   y cuántos proveedores únicos aparecen. Señala si detectas algún problema evidente
   de calidad de datos como celdas vacías, formatos inconsistentes o valores atípicos.
   ```

5. Lee cuidadosamente la respuesta de Copilot. Identifica y **anota en papel o en un bloc de notas digital** los siguientes datos:
   - Número total de registros
   - Rango de fechas
   - Monto mínimo, máximo y promedio
   - Número de proveedores únicos
   - Problemas de calidad de datos mencionados por Copilot

6. Formula un **prompt de seguimiento** para profundizar en un punto específico que Copilot haya mencionado. Por ejemplo, si mencionó celdas vacías en RFC:

   ```
   ¿En cuántas filas la columna RFC_Proveedor está vacía o tiene un formato
   diferente a los 12 o 13 caracteres estándar de un RFC mexicano?
   Muestra los primeros 5 ejemplos con el número de fila correspondiente.
   ```

   > **Adaptación regional:** Si tu país usa NIT (Colombia), RUC (Ecuador/Perú) u otro identificador fiscal, ajusta el prompt reemplazando "RFC" y el formato de caracteres correspondiente.

**Resultado Esperado:**

Copilot debe devolver una descripción estructurada del dataset similar a:

```
La tabla contiene 523 registros de transacciones con fechas entre el 01/01/2024
y el 31/03/2024. Los montos van desde $500.00 hasta $485,000.00 con un promedio
de $28,340.00. Se identifican 87 proveedores únicos. Se detectaron 12 filas con
RFC_Proveedor vacío y 3 registros con formato de fecha inconsistente en las
filas 45, 201 y 389.
```

> **Nota:** Los valores exactos variarán según el archivo de práctica. Los resultados de Copilot son orientativos; pueden diferir entre sesiones por la naturaleza generativa del modelo.

**Verificación:**
- [ ] Copilot respondió con datos cuantitativos sobre el dataset (número de registros, rangos).
- [ ] Identificaste al menos un problema de calidad de datos en la respuesta.
- [ ] Anotaste los datos clave para usarlos como referencia en los pasos siguientes.

---

### Paso 2: Identificación de Transacciones Duplicadas y Pagos Fraccionados

**Objetivo:** Utilizar prompts analíticos específicos para detectar transacciones duplicadas y el patrón de *smurfing* (fraccionamiento de pagos para evadir controles).

**Instrucciones:**

1. Con el panel de Copilot abierto y la hoja `Transacciones` activa, escribe el siguiente prompt:

   ```
   Analiza las columnas Proveedor, Monto y Fecha en esta tabla.
   Identifica los casos donde:
   1. El mismo proveedor recibe pagos con el mismo monto en fechas diferentes
      (posibles duplicados).
   2. El mismo proveedor recibe múltiples pagos en el mismo día o en días
      consecutivos cuya suma supera $50,000 pero ningún pago individual
      supera $10,000 (posible fraccionamiento o smurfing).
   Para cada caso, indica el nombre del proveedor, las filas involucradas
   y el monto total acumulado.
   ```

2. Revisa la respuesta. Copilot identificará proveedores y filas específicas.

3. Para **validar manualmente** uno de los casos señalados por Copilot:
   - En la cinta de opciones, ve a **Datos > Filtrar**.
   - Haz clic en la flecha del encabezado **Proveedor**.
   - Selecciona únicamente el proveedor mencionado por Copilot como sospechoso.
   - Revisa visualmente las filas filtradas y confirma si el patrón señalado es real.

4. Ahora formula un prompt más específico para el patrón de proveedores con **nombres similares** (posibles empresas fantasma con variaciones tipográficas):

   ```
   Examina la columna Proveedor y agrupa los nombres que sean muy similares
   entre sí (por ejemplo, "Servicios ABC S.A." y "Servicios ABC SA" o
   "SERVICIOS ABC S.A."). Lista los grupos de nombres similares encontrados
   y el número de transacciones asociadas a cada grupo.
   ```

5. Anota los grupos de proveedores similares que Copilot identifique. Estos serán usados en el Paso 3 para generar fórmulas de validación.

**Resultado Esperado:**

Copilot debe devolver una lista estructurada como:

```
Posibles duplicados detectados:
• Proveedor "Consultores Delta S.C." — Pago de $15,000 en filas 34, 67 y 112
  (misma fecha: 15/02/2024). Riesgo: ALTO.

Posible fraccionamiento (smurfing):
• Proveedor "Tech Supplies MX" — 6 pagos entre $8,000 y $9,500 los días
  03/03/2024 y 04/03/2024. Suma total: $52,300. Riesgo: MEDIO-ALTO.

Nombres similares (posibles empresas fantasma):
• Grupo 1: "INMOBILIARIA TORRES S.A." (8 transacciones) /
           "Inmobiliaria Torres SA" (3 transacciones) /
           "INMBILIARIA TORRES S.A." (1 transacción — posible error tipográfico)
```

**Verificación:**
- [ ] Copilot identificó al menos un caso de pago duplicado o fraccionado con referencia a filas específicas.
- [ ] Copilot identificó al menos un grupo de proveedores con nombres similares.
- [ ] Validaste manualmente al menos uno de los hallazgos usando el filtro de Excel.

---

### Paso 3: Análisis de Concentración y Detección de Outliers

**Objetivo:** Identificar concentración inusual de operaciones por proveedor, fecha o usuario de registro, y detectar montos estadísticamente atípicos.

**Instrucciones:**

1. En el panel de Copilot, escribe el siguiente prompt para analizar la **concentración por proveedor**:

   ```
   Calcula qué porcentaje del gasto total representa cada proveedor.
   Identifica los proveedores que concentran más del 20% del gasto total
   y aquellos que tienen más de 15 transacciones en el período.
   Presenta los resultados en una tabla ordenada de mayor a menor concentración.
   ```

2. Una vez que Copilot devuelva la respuesta, solicita que **inserte una tabla dinámica o una visualización** con el resumen:

   ```
   Crea una tabla dinámica en una nueva hoja que muestre el total de pagos
   por proveedor, ordenado de mayor a menor, con el porcentaje del total.
   ```

   > Copilot puede generar la tabla dinámica directamente o guiarte para crearla. Si la genera, revisa que los datos sean correctos.

3. Ahora solicita el análisis de **concentración por fecha** para detectar picos inusuales:

   ```
   Analiza la columna Fecha e identifica los días con mayor número de
   transacciones y mayor volumen de pagos. ¿Existe algún día con actividad
   inusualmente alta comparada con el promedio diario? Indica la fecha,
   el número de transacciones y el monto total de ese día.
   ```

4. Finalmente, solicita la identificación de **outliers estadísticos** en los montos:

   ```
   Usando criterios estadísticos (por ejemplo, montos que superen el
   percentil 95 o que estén a más de 2 desviaciones estándar del promedio),
   identifica las transacciones con montos atípicamente altos. Lista las
   10 transacciones de mayor riesgo con su fila, proveedor, monto y fecha.
   ```

5. **Aplica formato condicional** manual para resaltar visualmente las filas identificadas:
   - Selecciona la columna **Monto** (por ejemplo, `F2:F524`).
   - Ve a **Inicio > Formato condicional > Escalas de color**.
   - Elige la escala **Rojo-Amarillo-Verde** (los montos más altos quedarán en rojo).

**Resultado Esperado:**

- Una tabla dinámica en una nueva hoja con el ranking de proveedores por gasto.
- Lista de los 3-5 días con mayor concentración de transacciones.
- Lista de las 10 transacciones con montos más atípicos, con referencia a filas específicas.
- La columna Monto con formato condicional aplicado.

**Verificación:**
- [ ] La tabla dinámica fue creada y muestra al menos los 10 proveedores con mayor gasto.
- [ ] Copilot identificó al menos un día con actividad inusualmente alta.
- [ ] Se generó una lista de transacciones outliers con referencia a filas específicas.
- [ ] El formato condicional de escala de colores está aplicado en la columna Monto.

---

### Bloque 2: Generación de Fórmulas Complejas y Reporte de Hallazgos (20 minutos)

---

### Paso 4: Generación de Fórmulas Avanzadas con Copilot

**Objetivo:** Solicitar a Copilot la generación de fórmulas complejas para validación masiva de datos y clasificación de riesgo, y aplicarlas correctamente en la hoja de cálculo.

**Instrucciones:**

1. Navega a la hoja **`Transacciones`** y haz clic en una celda vacía al final de la tabla, en una nueva columna (por ejemplo, columna `J`, encabezado: `Validacion_RFC`).

2. En el panel de Copilot, solicita la primera fórmula de **validación de RFC**:

   ```
   Genera una fórmula para la columna J llamada "Validacion_RFC" que verifique
   si el valor en la columna C (RFC_Proveedor) tiene exactamente 12 caracteres
   (persona moral) o 13 caracteres (persona física). Si cumple, muestra "VÁLIDO";
   si está vacío, muestra "FALTANTE"; si tiene otra longitud, muestra "FORMATO INCORRECTO".
   ```

3. Copilot generará una fórmula. **Cópiala** del panel y pégala en la celda `J2`. La fórmula debe ser similar a:

   ```excel
   =SI(C2="","FALTANTE",SI(O(LARGO(C2)=12,LARGO(C2)=13),"VÁLIDO","FORMATO INCORRECTO"))
   ```

4. Extiende la fórmula hacia abajo hasta el último registro (doble clic en el controlador de relleno de la celda `J2`).

5. Ahora solicita una fórmula para **identificar proveedores no registrados en el catálogo**. Agrega una nueva columna `K` con encabezado `En_Catalogo`:

   ```
   Genera una fórmula para la columna K llamada "En_Catalogo" que busque el
   RFC de la columna C (RFC_Proveedor) en la hoja "Catalogo_Proveedores",
   columna A (RFC_Proveedor). Si el RFC existe en el catálogo, muestra
   "REGISTRADO"; si no existe, muestra "NO REGISTRADO - REVISAR".
   Usa XLOOKUP con manejo de error.
   ```

6. Copilot generará una fórmula similar a:

   ```excel
   =SI.ERROR(SI(XLOOKUP(C2,Catalogo_Proveedores!$A:$A,Catalogo_Proveedores!$A:$A,"")<>"","REGISTRADO","NO REGISTRADO - REVISAR"),"NO REGISTRADO - REVISAR")
   ```

   Pega la fórmula en `K2` y extiéndela hacia abajo.

7. Solicita una fórmula para **calcular el total acumulado por proveedor** y compararlo con un umbral. Agrega columna `L` con encabezado `Total_Proveedor`:

   ```
   Genera una fórmula SUMAR.SI para la columna L llamada "Total_Proveedor"
   que sume todos los montos de la columna F donde el proveedor en columna B
   sea igual al proveedor de la fila actual. El resultado debe ser el total
   acumulado de pagos a ese proveedor en toda la tabla.
   ```

8. Agrega columna `M` con encabezado `Nivel_Riesgo_Proveedor` y solicita:

   ```
   Genera una fórmula para la columna M llamada "Nivel_Riesgo_Proveedor"
   que clasifique el riesgo del proveedor con base en el total calculado
   en la columna L:
   - Si el total supera $200,000: "RIESGO ALTO"
   - Si el total está entre $50,000 y $200,000: "RIESGO MEDIO"
   - Si el total es menor a $50,000: "RIESGO BAJO"
   Además, si la columna K muestra "NO REGISTRADO - REVISAR",
   el nivel siempre debe ser "RIESGO ALTO" independientemente del monto.
   ```

   La fórmula resultante debe ser similar a:

   ```excel
   =SI(K2="NO REGISTRADO - REVISAR","RIESGO ALTO",SI(L2>200000,"RIESGO ALTO",SI(L2>=50000,"RIESGO MEDIO","RIESGO BAJO")))
   ```

9. **Aplica formato condicional** a la columna `M` para el semáforo de riesgo:
   - Selecciona el rango `M2:M524`.
   - Ve a **Inicio > Formato condicional > Resaltar reglas de celdas > Texto que contiene**.
   - Crea tres reglas:
     - Texto "RIESGO ALTO" → Relleno rojo claro, texto rojo oscuro.
     - Texto "RIESGO MEDIO" → Relleno amarillo, texto amarillo oscuro.
     - Texto "RIESGO BAJO" → Relleno verde claro, texto verde oscuro.

**Resultado Esperado:**

La hoja `Transacciones` debe tener cuatro columnas nuevas funcionales:

| Columna | Encabezado | Ejemplo de valor |
|---|---|---|
| J | Validacion_RFC | `VÁLIDO` / `FALTANTE` / `FORMATO INCORRECTO` |
| K | En_Catalogo | `REGISTRADO` / `NO REGISTRADO - REVISAR` |
| L | Total_Proveedor | `$52,300.00` |
| M | Nivel_Riesgo_Proveedor | `RIESGO ALTO` (en rojo) |

**Verificación:**
- [ ] La columna `J` muestra al menos tres valores distintos (VÁLIDO, FALTANTE, FORMATO INCORRECTO).
- [ ] La columna `K` identifica al menos un proveedor "NO REGISTRADO - REVISAR".
- [ ] La columna `L` muestra valores consistentes (el total del mismo proveedor es igual en todas sus filas).
- [ ] La columna `M` tiene el semáforo de colores aplicado correctamente.
- [ ] Todas las fórmulas se extienden hasta el último registro de la tabla.

---

### Paso 5: Generación del Reporte de Hallazgos con Copilot

**Objetivo:** Utilizar Copilot para estructurar y redactar un reporte ejecutivo de hallazgos de auditoría con tabla resumen y recomendaciones, directamente desde Excel.

**Instrucciones:**

1. Navega a la hoja **`Reporte_Hallazgos`** (hoja en blanco).

2. En la celda `A1`, escribe el título: **`REPORTE DE HALLAZGOS DE AUDITORÍA — ANÁLISIS DE PAGOS A PROVEEDORES`**

3. En la celda `A2`, escribe: **`Período analizado: Q1 2024 | Elaborado con: Microsoft 365 Copilot | Fecha: [fecha actual]`**

4. Abre el panel de **Copilot** y escribe el siguiente prompt para generar la tabla resumen de hallazgos:

   ```
   Basándote en el análisis realizado en la hoja "Transacciones" de este archivo,
   genera una tabla de resumen de hallazgos de auditoría con las siguientes columnas:
   - N° Hallazgo
   - Categoría de Riesgo (Duplicados, Fraccionamiento, Proveedor No Registrado,
     RFC Inválido, Concentración Inusual)
   - Descripción del Hallazgo (máximo 2 líneas)
   - Número de Transacciones Afectadas
   - Monto Total en Riesgo
   - Nivel de Riesgo (Alto/Medio/Bajo)
   - Recomendación de Acción

   Incluye al menos 5 hallazgos basados en los patrones detectados.
   Inserta la tabla en la hoja activa comenzando en la celda A4.
   ```

5. Copilot generará la tabla. Revísala críticamente:
   - ¿Los números de transacciones afectadas son consistentes con lo que viste en los pasos anteriores?
   - ¿Las recomendaciones son específicas y accionables?
   - Corrige cualquier dato que no coincida con tu análisis.

6. Solicita a Copilot que redacte el **párrafo de conclusión ejecutiva**:

   ```
   Redacta un párrafo de conclusión ejecutiva (máximo 150 palabras) para el
   reporte de auditoría que resuma los hallazgos principales, el nivel de
   riesgo general del período analizado y las tres acciones prioritarias
   que se recomiendan a la dirección. Usa un tono formal y técnico apropiado
   para un informe de auditoría interna.
   ```

7. Copia el texto generado por Copilot y pégalo en la celda `A` debajo de la tabla de hallazgos (deja dos filas en blanco entre la tabla y el párrafo).

8. Aplica **formato básico** al reporte:
   - Título en `A1`: Negrita, tamaño 14, color azul oscuro.
   - Encabezados de la tabla: Negrita, fondo azul claro, texto blanco.
   - Columna "Nivel de Riesgo": Aplicar formato condicional de colores (rojo/amarillo/verde) igual que en el Paso 4.

9. **Guarda el archivo** presionando `Ctrl + S`. Confirma que se guarda en OneDrive (debe aparecer "Guardado en OneDrive" en la barra de título).

**Resultado Esperado:**

La hoja `Reporte_Hallazgos` debe contener:
- Un encabezado con título y período del análisis.
- Una tabla con mínimo 5 hallazgos clasificados por nivel de riesgo con formato de semáforo.
- Un párrafo de conclusión ejecutiva de tono formal.
- El archivo guardado y sincronizado en OneDrive.

**Ejemplo representativo de tabla de hallazgos generada por Copilot:**

| N° | Categoría | Descripción | Transacciones Afectadas | Monto en Riesgo | Nivel | Recomendación |
|---|---|---|---|---|---|---|
| 1 | Duplicados | Pago idéntico a "Consultores Delta S.C." en 3 fechas distintas | 3 | $45,000 | ALTO | Retener pagos y solicitar soporte documental |
| 2 | Fraccionamiento | "Tech Supplies MX" recibió 6 pagos en 2 días con suma $52,300 | 6 | $52,300 | ALTO | Escalar a comité de ética para investigación |
| 3 | Proveedor No Registrado | 14 transacciones con RFC no encontrado en catálogo oficial | 14 | $187,500 | ALTO | Suspender pagos y validar alta en sistema |
| 4 | RFC Inválido | 12 registros con RFC vacío o con formato incorrecto | 12 | $34,200 | MEDIO | Solicitar corrección a área de cuentas por pagar |
| 5 | Concentración Inusual | Un proveedor concentra el 31% del gasto total del período | 47 | $412,000 | MEDIO | Revisar proceso de selección y contratos vigentes |

**Verificación:**
- [ ] La tabla de hallazgos contiene mínimo 5 filas con todas las columnas completas.
- [ ] El párrafo de conclusión ejecutiva tiene tono formal y menciona acciones prioritarias.
- [ ] El formato de semáforo está aplicado en la columna "Nivel de Riesgo".
- [ ] El archivo fue guardado exitosamente en OneDrive (sin errores de sincronización).

---

## 7. Validación y Pruebas

Al finalizar todos los pasos, realiza la siguiente lista de verificación integral del laboratorio:

### Lista de Verificación Final

| # | Criterio de Validación | Estado |
|---|---|---|
| 1 | Copilot respondió al prompt de exploración inicial con datos cuantitativos del dataset | ☐ Completo |
| 2 | Se identificaron al menos 2 patrones de riesgo distintos (duplicados, fraccionamiento, nombres similares) | ☐ Completo |
| 3 | Se validó manualmente al menos 1 hallazgo de Copilot usando filtros de Excel | ☐ Completo |
| 4 | La columna `Validacion_RFC` (J) funciona correctamente con los tres posibles resultados | ☐ Completo |
| 5 | La columna `En_Catalogo` (K) usa XLOOKUP y devuelve resultados correctos | ☐ Completo |
| 6 | La columna `Nivel_Riesgo_Proveedor` (M) tiene semáforo de colores aplicado | ☐ Completo |
| 7 | La hoja `Reporte_Hallazgos` contiene tabla con mínimo 5 hallazgos | ☐ Completo |
| 8 | El reporte incluye conclusión ejecutiva redactada con Copilot | ☐ Completo |
| 9 | El archivo está guardado y sincronizado en OneDrive | ☐ Completo |
| 10 | Se aplicó criterio profesional para validar/ajustar al menos una respuesta de Copilot | ☐ Completo |

### Prueba de Calidad del Reporte

Para verificar que el reporte generado tiene la calidad mínima requerida, responde las siguientes preguntas de reflexión crítica:

1. **¿Copilot identificó algún falso positivo?** (es decir, ¿marcó como sospechosa alguna transacción que, al revisar manualmente, resultó ser completamente normal?) Documenta un ejemplo.

2. **¿Las recomendaciones generadas por Copilot son específicas para el contexto de tu organización o son genéricas?** Identifica al menos una que requeriría adaptación antes de incluirse en un reporte real.

3. **¿El monto total en riesgo calculado en la tabla de hallazgos es consistente** con los montos que viste en los pasos de análisis? ¿Hay duplicación o subestimación?

> Estas reflexiones son el núcleo del **juicio profesional** que el auditor debe aplicar siempre que use Copilot como herramienta de apoyo. Comparte tus respuestas en la discusión grupal al cierre de la sesión.

---

## 8. Solución de Problemas

### Problema 1: El botón de Copilot no aparece en la cinta de opciones de Excel

**Síntoma:** Al abrir `Lab01_Transacciones_Auditoria.xlsx`, la pestaña **Inicio** de la cinta de opciones no muestra el botón de Copilot (ícono de estrella/chispa). La pestaña "Copilot" tampoco aparece en otras pestañas de la cinta.

**Causa probable:** Una o más de las siguientes condiciones:
- La licencia **Microsoft 365 Copilot** no está asignada a la cuenta del usuario en el portal de administración de M365.
- El administrador de TI no ha habilitado Copilot para la aplicación Excel a nivel de tenant.
- El archivo **no está guardado en OneDrive o SharePoint** (Copilot en Excel requiere que el archivo esté en la nube, no en almacenamiento local).
- La versión de Excel instalada es anterior a la 2401 (Copilot no está disponible en versiones antiguas).

**Solución paso a paso:**

1. **Verificar que el archivo esté en OneDrive:**
   - Revisa la barra de título de Excel. Debe mostrar el ícono de OneDrive y el texto *"Guardado en OneDrive"*.
   - Si el archivo está en el escritorio o en una carpeta local, ciérralo, muévelo a `OneDrive > Documentos > Laboratorios_Copilot` y ábrelo desde ahí.

2. **Verificar la versión de Excel:**
   - Ve a **Archivo > Cuenta > Acerca de Excel**.
   - Confirma que la versión sea **2401 o superior**. Si no, solicita al área de TI que actualice Office.

3. **Verificar la licencia de Copilot:**
   - Abre un navegador y ve a [https://portal.office.com](https://portal.office.com).
   - Inicia sesión con tu cuenta corporativa.
   - Ve a **Configuración > Mis aplicaciones**. Si Copilot no aparece como aplicación disponible, la licencia no está asignada. Contacta a tu administrador de TI.

4. **Forzar actualización de la cinta:**
   - Cierra Excel completamente.
   - Espera 2 minutos.
   - Vuelve a abrir el archivo desde OneDrive (no desde archivos recientes locales).

> Si ninguno de los pasos anteriores resuelve el problema, notifica al instructor. **No continúes el laboratorio** hasta resolver el acceso a Copilot, ya que todos los pasos siguientes dependen de esta funcionalidad.

---

### Problema 2: Copilot genera fórmulas con errores (#¿NOMBRE?, #¡REF!, #¡VALOR!) al pegarlas en Excel

**Síntoma:** Al copiar una fórmula generada por Copilot y pegarla en una celda de Excel, la celda muestra un error como `#¿NOMBRE?`, `#¡REF!` o `#¡VALOR!` en lugar del resultado esperado.

**Causa probable:** Las causas más frecuentes son:
- **Separador de argumentos incorrecto:** Copilot puede generar fórmulas usando coma (`,`) como separador, pero la configuración regional de Excel en español usa punto y coma (`;`).
- **Nombre de hoja o columna incorrecto:** Copilot puede referenciar una hoja o columna con un nombre ligeramente diferente al real (por ejemplo, `Catalogo_Proveedores` vs `Catalogo Proveedores`).
- **Función no disponible en la versión instalada:** Funciones como `XLOOKUP` o `FILTRAR` requieren Excel 365 (versión 2019 o superior). En versiones anteriores no están disponibles.

**Solución paso a paso:**

1. **Corregir el separador de argumentos:**
   - Selecciona la celda con error y presiona `F2` para editar la fórmula.
   - Reemplaza todas las comas (`,`) que separan argumentos por punto y coma (`;`).
   - Ejemplo: `=SI(C2="","FALTANTE",...)` debe convertirse en `=SI(C2="";"FALTANTE";...)`.
   - Presiona `Enter` y verifica si el error desaparece.

2. **Verificar nombres de hojas y columnas:**
   - Revisa el nombre exacto de la hoja en la pestaña inferior (distingue mayúsculas, espacios y guiones bajos).
   - En la fórmula, asegúrate de que el nombre de la hoja referenciada coincida exactamente. Si tiene espacios, debe ir entre apóstrofes: `'Catalogo Proveedores'!$A:$A`.

3. **Solicitar a Copilot una versión alternativa:**
   - Si la función no está disponible, pide a Copilot que genere una fórmula equivalente con funciones más antiguas:
   ```
   La función XLOOKUP no está disponible en mi versión de Excel.
   Genera la misma fórmula usando BUSCARV o INDICE/COINCIDIR como alternativa.
   ```

4. **Usar el Asistente para funciones de Excel:**
   - Haz clic en el botón `fx` junto a la barra de fórmulas.
   - Selecciona la función con error para ver qué argumento está causando el problema.

> **Buena práctica:** Siempre prueba la fórmula generada por Copilot en una celda de prueba vacía antes de aplicarla a toda la columna. Esto evita propagar errores a cientos de filas.

---

## 9. Limpieza del Entorno

Al finalizar el laboratorio, realiza los siguientes pasos para dejar el entorno ordenado y listo para las siguientes sesiones:

1. **Guardar el archivo final:**
   - Presiona `Ctrl + S` para guardar todos los cambios.
   - Confirma que la barra de título muestra *"Guardado en OneDrive"* sin indicadores de error.

2. **Renombrar el archivo con tu identificador:**
   - Cierra el archivo en Excel.
   - En el Explorador de archivos, navega a `OneDrive > Documentos > Laboratorios_Copilot`.
   - Renombra el archivo de `Lab01_Transacciones_Auditoria.xlsx` a `Lab01_Transacciones_Auditoria_[TusIniciales]_Completado.xlsx`.
   - Ejemplo: `Lab01_Transacciones_Auditoria_JMR_Completado.xlsx`.

3. **Conservar el archivo original sin modificar:**
   - El instructor habrá provisto también una copia de solo lectura del archivo original. Verifica que no hayas sobrescrito ese archivo. Si lo hiciste accidentalmente, descárgalo nuevamente desde el enlace provisto por el instructor.

4. **Cerrar el panel de Copilot:**
   - Abre el archivo renombrado.
   - Haz clic en la **X** del panel de Copilot para cerrarlo.
   - Cierra Excel.

5. **Verificar sincronización final con OneDrive:**
   - En la bandeja del sistema (esquina inferior derecha), haz clic en el ícono de OneDrive (nube azul).
   - Confirma que el estado muestra *"Actualizado"* o *"Todo sincronizado"* sin errores pendientes.

> **No elimines** el archivo completado. El instructor puede solicitar revisarlo como evidencia de la práctica realizada.

---

## 10. Resumen

### Conceptos Clave Practicados

En este laboratorio de 60 minutos aplicaste los conceptos fundamentales de la Lección 1.1 en un escenario realista de auditoría:

| Concepto | Aplicación en el Laboratorio |
|---|---|
| **Copilot como asistente cognitivo** | Formulaste prompts en lenguaje natural para obtener análisis que habrían tomado horas de forma manual |
| **Análisis de patrones en datos estructurados** | Detectaste duplicados, fraccionamiento (*smurfing*) y proveedores con nombres similares en 500+ registros |
| **Generación de hipótesis de riesgo** | Usaste prompts exploratorios para que Copilot sugiriera áreas de riesgo que luego validaste manualmente |
| **Fórmulas avanzadas asistidas por IA** | Generaste y aplicaste XLOOKUP, SI anidado, SUMAR.SI y fórmulas de validación de RFC/NIT |
| **Semáforo de riesgo** | Clasificaste transacciones y proveedores en niveles Alto/Medio/Bajo con formato condicional |
| **Reporte de hallazgos** | Estructuraste un reporte ejecutivo con tabla de hallazgos y conclusión redactada por Copilot |
| **Juicio profesional** | Validaste manualmente los hallazgos de Copilot e identificaste posibles falsos positivos |

### Reflexión Final

El flujo de trabajo **consulta → análisis → documentación** que practicaste hoy es la base de todas las prácticas avanzadas del curso. Recuerda siempre:

> *"Copilot amplifica tu capacidad analítica, pero no reemplaza tu criterio profesional. Un hallazgo de auditoría solo tiene valor cuando ha sido validado por un profesional competente."*
> — Principio central de la Lección 1.1

### Recursos Adicionales

| Recurso | Enlace |
|---|---|
| Documentación oficial de Copilot para Microsoft 365 | [learn.microsoft.com/es-es/copilot/microsoft-365](https://learn.microsoft.com/es-es/copilot/microsoft-365/microsoft-365-copilot-overview) |
| Guía de prompts para Copilot en Excel | [learn.microsoft.com — Copilot en Excel](https://learn.microsoft.com/es-es/copilot/microsoft-365/use-cases/excel) |
| Funciones de Excel — XLOOKUP | [support.microsoft.com — XLOOKUP](https://support.microsoft.com/es-es/office/función-xlookup-b7fd680e-6d10-43e6-84f9-88eae8bf5929) |
| Informe Global sobre Fraude Ocupacional 2024 — ACFE | [acfe.com/report-to-the-nations](https://www.acfe.com/fraud-resources/report-to-the-nations) |
| ISA 240: Responsabilidades del auditor en relación con el fraude — IFAC | [ifac.org — ISA 240](https://www.ifac.org/system/files/downloads/a012-2010-iaasb-handbook-isa-240.pdf) |

### Próxima Sesión

En la **Sesión 2 (Lab 01-00-02)** profundizarás en la **Lección 1.2: Fórmulas Complejas y Automatización de Reportes de Hallazgos en Excel**, donde construirás un flujo de análisis más robusto que incluye fórmulas matriciales, funciones dinámicas (`FILTRAR`, `ÚNICO`, `ORDENAR`) y la automatización completa del ciclo de reporte desde Excel hacia Word usando Copilot. Asegúrate de tener el archivo `Lab02_Reporte_Automatizado.xlsx` en tu OneDrive antes de la próxima sesión.

---

*Guía de Laboratorio — Lab 01-00-01 | Microsoft 365 Copilot para Auditoría, Impuestos y Legal | Versión 1.0*
*Todos los datos y escenarios son ficticios. Uso exclusivo para fines de capacitación.*
