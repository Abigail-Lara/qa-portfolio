# Ejemplos de Casos de Prueba Funcionales

Este documento presenta ejemplos reales de diseño de pruebas funcionales aplicadas a sistemas bancarios y de seguros. El enfoque está orientado a la validación de procesos críticos del negocio, consistencia de la información y mitigación de riesgos en entornos productivos.

---

## Contexto del módulo
Módulo de consulta de pólizas, utilizado por usuarios de negocio para validar información contractual de clientes.  
Un error en este módulo puede generar decisiones incorrectas, impacto financiero o afectación legal.

---

## Caso 1 Consulta de póliza activa

**ID:** TC-FUNC-001 
**Tipo:** Funcional. 
**Prioridad:** Alta. 
**Riesgo cubierto:** Información incorrecta entre UI y base de datos.

### Objetivo de negocio
Asegurar que el usuario visualice información confiable y completa de una póliza activa para la toma de decisiones.

### Criterios de aceptación
- La póliza debe mostrarse únicamente si su estatus es activo.
- La información debe coincidir con la fuente oficial de datos.
- No deben mostrarse campos vacíos ni valores por defecto.

### Precondiciones
- Usuario con permisos de consulta.
- Póliza activa registrada correctamente en el sistema.

### Validaciones a ejecutar
1. Ingresar al módulo consulta desde la aplicación VisualTIME.
2. Capturar el número de póliza a consultar.
3. Validar que el estatus de la póliza sea activo.
4. Validar la vigencia de la póliza.
5. Validar que los datos del titular correspondan al registro de la póliza.
6. Comparar la información mostrada en UI contra base de datos (Oracle).

### Resultado esperado
- La información mostrada es consistente, completa y exacta.
- No existen discrepancias entre UI y base de datos.

---

## Caso 2 Consulta de póliza inexistente

**ID:** TC-FUNC-002
**Tipo:** Funcional / Negativa 
**Prioridad:** Media.
**Riesgo cubierto:** Confusión del usuario / visualización de datos residuales.

### Objetivo de negocio
Evitar que el sistema muestre información incorrecta cuando la póliza no existe.

### Criterios de aceptación
- El sistema debe controlar el error de forma adecuada.
- El mensaje debe ser claro, informativo y no técnico.
- No debe mostrarse información parcial ni residual.

### Validaciones a ejecutar
1. Ingresar al módulo **Consulta** desde la aplicación VisualTIME.
2. Capturar un número de póliza inexistente.
3. Validar la información contra base de datos (Oracle).

### Resultado esperado
- El sistema muestra un mensaje informativo indicando que la póliza no existe.
- La aplicación se mantiene estable y operativa.

---

## Caso 3 Validación de consistencia de datos

**ID:** TC-FUNC-003
**Tipo:** Funcional / Validación de datos.
**Prioridad:** Alta.
**Riesgo cubierto:** Decisiones basadas en información incorrecta.

### Objetivo de negocio
Garantizar que la información presentada al usuario sea la misma que la registrada en la base de datos.

### Validaciones a ejecutar
1. Ingresar al módulo consulta desde la aplicación VisualTIME.
2. Capturar el número de póliza a consultar.
3. Ejecutar consulta SQL en Oracle.
4. Comparar campos críticos: estatus, vigencia y datos del titular.

### Resultado esperado
- Coincidencia total entre la información mostrada en UI y los registros de base de datos.
- No existen desfasamientos ni inconsistencias de información.

---

## Caso 4 Consulta de póliza cancelada

**ID:** TC-FUNC-004  
**Tipo:** Funcional / Regla de negocio.
**Prioridad:** Alta.
**Riesgo cubierto:** Uso indebido de pólizas canceladas.

### Objetivo de negocio
Asegurar que una póliza con estatus cancelado se muestre correctamente y no permita acciones no válidas.

### Criterios de aceptación
- El estatus de la póliza debe mostrarse como cancelado.
- No deben habilitarse acciones correspondientes a pólizas activas.

### Validaciones a ejecutar
1. Ingresar al módulo consulta desde la aplicación VisualTIME.
2. Capturar un número de póliza con estatus cancelado.
3. Validar que el estatus se muestre como cancelado.
4. Verificar que no se habiliten acciones asociadas a pólizas activas.

### Resultado esperado
- Información clara y consistente del estatus de la póliza.
- Restricciones de negocio aplicadas correctamente.

---

## Decisiones de QA
- Se priorizan flujos que impactan directamente la toma de decisiones del negocio.
- Se valida consistencia de datos en puntos críticos del sistema.
- No se documentan casos redundantes de bajo valor.
- La cobertura de pruebas se enfoca en riesgo, no en volumen de casos.

---
