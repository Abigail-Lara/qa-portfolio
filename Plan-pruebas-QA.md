# Plan de Pruebas QA

Este documento define el **Plan de pruebas QA**, utilizado como instrumento de gobierno de calidad para controlar, evaluar y aprobar la liberación de funcionalidades críticas en sistemas bancarios y de seguros.

El plan establece el alcance, estrategia, responsabilidades, controles de riesgo y criterios de decisión, garantizando que la liberación a producción se realice con un nivel de riesgo conocido, mitigado y formalmente aceptado.

---

## 1. Contexto y alcance ejecutivo

**Sistema:** VisualTIME.
**Módulo crítico:** Consulta de pólizas.
**Dominio:** Bancario / Seguros.
**Tipo de liberación:** [Release mayor / Release menor / Hotfix]  
**Ambientes:** QA / UAT.
**Versión evaluada:** [Versión].
**Responsable QA:** [Nombre].

### Importancia del módulo
El módulo de consulta de pólizas soporta procesos de validación contractual y toma de decisiones (operativas).  
Un defecto en este módulo puede derivar en:
- Impacto financiero
- Decisiones de negocio incorrectas
- Incumplimiento normativo
- Afectación reputacional

Por lo tanto, el módulo se clasifica como **crítico**.

---

## 2. Objetivo del plan de pruebas

- Asegurar el cumplimiento funcional y operativo del módulo.
- Controlar el riesgo antes de la liberación.
- Garantizar trazabilidad completa entre requerimientos, pruebas y aceptación.
- Establecer criterios claros y defendibles.
- Proveer evidencia formal para auditoría y compliance.

---

## 3. Alcance funcional

### 3.1 En alcance
- Consulta de pólizas por identificador.
- Visualización de estatus, vigencia y datos del titular.
- Manejo controlado de errores (pólizas inexistentes).
- Reglas de negocio para pólizas canceladas.
- Validación de consistencia de datos (UI vs fuente oficial – Oracle).
- Control de accesos y permisos funcionales.
- Regresión funcional focalizada.
- User Acceptance Testing (UAT).

### 3.2 Fuera de alcance
- Pruebas de estrés y carga masiva.
- Cambios en sistemas externos no incluidos en el release.
- Validaciones regulatorias fuera del módulo.
- Cambios de infraestructura no relacionados.

---

## 4. Artefactos de trazabilidad

Este plan se apoya en los siguientes artefactos:

- **Casos de prueba funcionales**
- **Escenarios UAT**
- **Matriz de Trazabilidad (RTM)**
- **Matriz de Riesgos QA**
- **Bitácora de ejecución**
- **Reporte de defectos**
- **Acta de aceptación UAT**

La ausencia de alguno de estos artefactos bloquea la liberación.

---

## 5. Estrategia de pruebas

La estrategia se basa en criticidad y riesgo, no en volumen.

### 5.1 Tipos de prueba
- Pruebas funcionales End-to-End
- Pruebas negativas y de control
- Validación de reglas de negocio
- Validación de datos (SQL Oracle)
- Pruebas de regresión focalizada
- Smoke testing post-deploy
- User Acceptance Testing (UAT)

### 5.2 Niveles de prueba
- **QA Funcional:** Validación técnica y funcional.
- **UAT:** Validación operativa y aceptación de negocio.
- **Validación cruzada:** QA + negocio para datos críticos.

---

## 6. Gestión de riesgos

Los riesgos se identifican, evalúan y mitigan conforme a la matriz de riesgos, tomando en cuenta:

- Impacto al negocio
- Probabilidad de ocurrencia
- Capacidad de detección
- Riesgo post-pruebas

Ningún riesgo alto o crítico puede liberarse sin mitigación y aceptación formal.

---

## 7. Criterios de entrada

La ejecución de pruebas inicia únicamente si:

- Requerimientos y criterios de aceptación están aprobados.
- El ambiente está estable y validado.
- La versión está desplegada correctamente.
- Existen datos de prueba controlados.
- Se cuenta con accesos y roles definidos.
- Matriz de riesgos están vigentes.

---

## 8. Fases de plan de ejecución

### Fase 1 Smoke testing
Validar estabilidad básica post-deploy.

### Fase 2 Pruebas funcionales (críticas para negocio)
Cobertura de flujos principales, reglas de negocio y escenarios negativos.

### Fase 3 Validación de datos
Comparación UI vs fuente oficial (Oracle).

### Fase 4 Regresión
Validar impacto colateral del cambio.

### Fase 5 UAT
Ejecución por negocio con soporte QA y evidencia formal.

---

## 9. Gestión de defectos

### 9.1 Clasificación por severidad
- **Bloqueante:** Impide operación o pruebas.
- **Alta:** Afecta reglas críticas o datos.
- **Media:** Impacto funcional con workaround.
- **Baja:** Impacto menor.

### 9.2 Flujo de gestión
Registro > Triage > Corrección > Re-test > Regresión > Cierre.

Defectos bloqueantes o altos bloquearan la liberación.

---

## 10. Criterios de salida

QA se considera completo cuando:

- 100% de pruebas de prioridad alta ejecutadas.
- 0 defectos bloqueantes o altos abiertos.
- UAT crítico aprobado.
- Evidencia completa y trazable.
- Riesgo documentado.

---

## 11. Autoridad de decisión QA

QA tiene autoridad para:
- Recomendar **No-Go** si se compromete la calidad.
- Exigir mitigación o aceptación formal de riesgos.
- Bloquear liberación ante incumplimiento de criterios.

La decisión final de liberación requiere aceptación explícita del negocio.

---

## 12. Aprobaciones y aceptación de riesgo

| Rol | Nombre | Fecha | Aprobación |
|-----|--------|-------|------------|
| QA | [Nombre] | [Fecha] | ✔ |
| Usuario de Negocio | [Nombre] | [Fecha] | ✔ |
| Stakeholder | [Nombre] | [Fecha] | ✔ |

---
