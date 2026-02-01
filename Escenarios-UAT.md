# Escenarios UAT

Este documento contiene ejemplos de **escenarios de User Acceptance Testing (UAT)** diseñados para validar que los sistemas cumplan con los requerimientos de negocio, reglas operativas y criterios de aceptación, previo a su liberación a producción.

Los escenarios están redactados en lenguaje de negocio, con apoyo de QA para validaciones técnicas, y se enfocan en mitigación de riesgos, toma de decisiones y estabilidad operativa en entornos bancarios y de seguros.

---

## Información general

**Sistema:** VisualTIME  
**Módulo:** Consulta de Pólizas.  
**Tipo de sistema:** Bancario / Seguros.  
**Ambiente UAT:** Preproductivo.  
**Objetivo de UAT:** Validar que el sistema sea funcionalmente aceptable para su uso operativo.

---

## Roles involucrados

- **Usuario de Negocio:** Ejecuta los escenarios y valida el cumplimiento funcional.
- **QA:** Da soporte técnico, valida consistencia de datos y documenta evidencias.
- **Stakeholder:** Autoriza la aceptación final del sistema.

---

## UAT-001 Consulta exitosa de póliza activa (flujo crítico de negocio)

**Tipo:** Positivo / Flujo principal.
**Prioridad:** Alta.
**Riesgo cubierto:** Toma de decisiones con información incorrecta.

### Objetivo de negocio
Confirmar que el usuario pueda consultar una póliza activa y obtener información completa, confiable y actualizada, necesaria para la operación diaria.

### Datos de prueba
- Número de póliza activa: [definir]
- Cliente asociado: [definir]

### Pasos (Usuario de negocio)
1. Ingresar a VisualTIME con credenciales válidas.
2. Acceder al módulo Consulta.
3. Capturar el número de póliza activa.
4. Ejecutar la consulta.

### Resultado esperado (negocio)
- El estatus se muestra como Activo.
- Se visualiza correctamente la vigencia y datos del titular.
- No existen campos vacíos, valores por defecto o información inconsistente.

### Evidencia requerida
- Captura de pantalla del resultado.
- Registro del número de póliza consultado.

---

## UAT-002 Consulta de póliza inexistente (control funcional del error)

**Tipo:** Negativo / Manejo de error.
**Prioridad:** Media.
**Riesgo cubierto:** Confusión del usuario y uso de información inválida.

### Objetivo de negocio
Garantizar que el sistema gestione adecuadamente la consulta de una póliza inexistente, evitando interpretaciones erróneas.

### Datos de prueba
- Número de póliza inexistente: [definir]

### Pasos (Usuario de negocio)
1. Acceder al módulo Consulta.
2. Capturar un número de póliza inexistente.
3. Ejecutar la consulta.

### Resultado esperado (negocio)
- El sistema muestra un mensaje claro e informativo indicando que la póliza no existe.
- No se despliega información residual.
- El sistema permanece estable y operativo.

### Evidencia requerida
- Captura del mensaje mostrado.
- Registro del número de póliza utilizado.

---

## UAT-003 Consulta de póliza cancelada y aplicación de reglas de negocio

**Tipo:** Regla de negocio.
**Prioridad:** Alta.
**Riesgo cubierto:** Uso indebido de pólizas canceladas.

### Objetivo de negocio
Confirmar que una póliza cancelada sea identificada correctamente y que el sistema aplique las restricciones correspondientes.

### Datos de prueba
- Número de póliza cancelada: [definir].

### Pasos (Usuario de negocio)
1. Acceder al módulo *Consulta.
2. Capturar el número de póliza cancelada.
3. Ejecutar la consulta.

### Resultado esperado (negocio)
- El estatus se muestra como Cancelado.
- No se habilitan acciones operativas asociadas a pólizas activas.
- La información se presenta de forma clara y consistente.

### Evidencia requerida
- Captura del resultado de la consulta.
- Registro del estatus visualizado.

---

## UAT-004 Validación de consistencia de datos

**Tipo:** Validación de datos.
**Prioridad:** Alta.
**Riesgo cubierto:** Decisiones basadas en información incorrecta.

### Objetivo de negocio
Asegurar que la información utilizada por el usuario coincida con la fuente oficial de datos.

### Datos de prueba
- Número de póliza activa: [definir].

### Pasos 
1. Usuario consulta la póliza en VisualTIME.
2. QA valida los datos críticos contra la fuente oficial en Oracle.
3. Se comparan campos: estatus, vigencia y datos del titular.

### Resultado esperado (negocio)
- Coincidencia total entre UI y fuente oficial.
- No existen discrepancias en campos críticos.

### Evidencia requerida
- Captura del resultado en UI.
- Evidencia de validación técnica (consulta SQL o equivalente).

---

## UAT-005 Validación de permisos de acceso al módulo Consulta

**Tipo:** Seguridad funcional.
**Prioridad:** Media.
**Riesgo cubierto:** Exposición de información a usuarios no autorizados.

### Objetivo de negocio
Confirmar que únicamente usuarios con permisos autorizados puedan consultar pólizas.

### Datos de prueba
- Usuario sin permisos de consulta: [definir].

### Pasos (Usuario de negocio)
1. Ingresar al sistema con usuario de rol limitado.
2. Intentar acceder al módulo consulta.

### Resultado esperado (negocio)
- El sistema restringe el acceso o muestra un mensaje de permisos insuficientes.
- No se expone información de pólizas.

### Evidencia requerida
- Captura del mensaje o restricción aplicada.
- Registro del usuario utilizado.

---

## Criterios de salida UAT

UAT se considera aprobado cuando:
- Todos los escenarios de prioridad alta han sido ejecutados y aprobados.
- No existen defectos abiertos de severidad alta o bloqueante.
- La evidencia requerida está completa y trazable.
- Los usuarios de negocio y stakeholders confirman la aceptación funcional del sistema.

---
