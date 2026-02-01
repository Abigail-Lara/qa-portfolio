# Matriz de Riesgos QA 

Este documento define la **Matriz de Riesgos QA**, utilizada como herramienta de calidad para identificar, evaluar, mitigar y aceptar riesgos funcionales y operativos en sistemas bancarios y de seguros, previo a su liberación a producción.

La matriz permite tomar decisiones mas informadas, priorizar esfuerzos de prueba y establecer un nivel de residual aceptable, alineado con las expectativas del negocio.

---

## 1. Información del sistema

**Sistema:** VisualTIME  
**Módulo:** Consulta de Pólizas  
**Dominio:** Bancario / Seguros  
**Ambiente:** Preproductivo (UAT)  
**Responsable QA:** [Nombre]  
**Fecha de evaluación:** [Fecha]  
**Versión evaluada:** [Versión]

---

## 2. Propósito de la Matriz de Riesgos QA

Esta matriz tiene como objetivos:

- Identificar riesgos que puedan impactar la operación, la toma de decisiones o cumplimiento normativo.
- Evaluar el impacto y probabilidad de manifestarse cada riesgo.
- Definir estrategias de mitigación a través de pruebas funcionales y UAT.
- Determinar el riesgo posterior a las pruebas.
- Dar visibilidad ejecutiva del estado de calidad previo a la liberación.

---

## 3. Criterios de evaluación de riesgo

### 3.1 Impacto al negocio
- **Alto:** Impacto financiero, legal, regulatorio y reputacional.
- **Medio:** Impacto operativo, reprocesos o afectación al servicio.
- **Bajo:** Impacto menor sin afectación crítica.

### 3.2 Probabilidad de ocurrencia
- **Alta:** El riesgo puede manifestarse con frecuencia.
- **Media:** El riesgo puede presentarse en escenarios muy específicos.
- **Baja:** El riesgo es de caracter poco probable.

### 3.3 Nivel de riesgo
El nivel de riesgo se determina combinando impacto y probabilidad:
- **Crítico**
- **Alto**
- **Medio**
- **Bajo**

---

## 4. Matriz de Riesgos QA

| ID Riesgo | Descripción del riesgo | Impacto | Probabilidad | Nivel inicial | Estrategia de mitigación QA | Evidencia (TC / UAT) | Riesgo residual | Responsable |
|----------|------------------------|---------|--------------|---------------|-----------------------------|----------------------|------------------|-------------|
| RIESGO-001 | Visualización de información incorrecta de pólizas activas que derive en decisiones erróneas. | Alto | Media | Alto | Pruebas funcionales End-to-End, validación de reglas de negocio y consistencia UI vs BD. | TC-FUNC-001, TC-FUNC-003, UAT-001, UAT-004 | Bajo | QA |
| RIESGO-002 | Consulta de pólizas inexistentes mostrando datos residuales o inconsistentes. | Medio | Media | Medio | Pruebas negativas y validación de control de errores. | TC-FUNC-002, UAT-002 | Bajo | QA |
| RIESGO-003 | Uso indebido de pólizas canceladas por ausencia de restricciones operativas. | Alto | Baja | Alto | Validación de reglas de negocio y restricciones funcionales. | TC-FUNC-004, UAT-003 | Bajo | QA / Negocio |
| RIESGO-004 | Desalineación entre información mostrada en UI y fuente oficial de datos. | Alto | Media | Alto | Validación de datos con SQL (Oracle) y revisión de puntos críticos. | TC-FUNC-003, UAT-004 | Bajo | QA |
| RIESGO-005 | Acceso no autorizado a información de pólizas por configuración incorrecta de permisos. | Medio | Baja | Medio | Pruebas funcionales de control de accesos y roles. | TC-FUNC-005, UAT-005 | Bajo | QA |
| RIESGO-006 | Mensajes de error poco claros que generen interpretaciones incorrectas del estado de una póliza. | Medio | Media | Medio | Validación de mensajes funcionales en escenarios negativos. | TC-FUNC-002, UAT-002 | Bajo | QA |

---

## 5. Análisis de riesgos críticos

- Riesgos con nivel Alto fueron priorizados en pruebas funcionales y UAT.
- Todos los riesgos críticos cuentan con evidencia de mitigación.
- No se identificaron riesgos críticos sin cobertura de pruebas.

---

## 6. Riesgo residual y aceptación

Tras la ejecución de pruebas funcionales y escenarios UAT:

- El riesgo para los riesgos identificados se considera bajo.
- QA valida la correcta mitigación técnica y funcional.
- La aceptación del riesgo residual corresponde al negocio y stakeholders.

---

## 7. Uso de la Matriz de riesgos en el proceso de liberación

Esta matriz es utilizada como insumo para:

- Priorizar pruebas y escenarios UAT.
- Respaldar decisiones.
- Comunicar el estado de calidad a negocio y management.
- Atender auditorías, revisiones regulatorias y controles internos.
- Documentar la aceptación formal de riesgos.

---

## 8. Conclusión QA

Desde la perspectiva de QA, los riesgos funcionales y operativos del módulo han sido identificados, evaluados y mitigados mediante pruebas funcionales y UAT.  
No se detectan riesgos críticos sin control, por lo que el nivel de riesgo residual es aceptable para liberación, sujeto a la aceptación formal del negocio.

---

## 9. Aprobaciones y aceptación de riesgo

| Rol | Nombre | Fecha | Aprobación |
|----|--------|-------|------------|
| QA | [Nombre] | [Fecha] | ✔ |
| Usuario de Negocio | [Nombre] | [Fecha] | ✔ |
| Stakeholder | [Nombre] | [Fecha] | ✔ |

---
