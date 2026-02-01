# Matriz de Trazabilidad de Requerimientos 

Este documento presenta una **Matriz de trazabilidad de requerimientos** utilizada para asegurar la cobertura funcional, la alineación con el negocio y el control de riesgos previo a la liberación de sistemas críticos en entornos bancarios y de seguros.

---

## Información del sistema

**Sistema:** VisualTIME  
**Módulo:** Consulta de Pólizas  
**Dominio:** Bancario / Seguros  
**Ambiente:** Preproductivo UAT
**Responsable QA:** [Nombre]  
**Fecha:** [Fecha]

---

## Objetivo

- Garantizar cobertura completa de requerimientos funcionales.
- Asegurar alineación entre negocio, QA y resultados de prueba.
- Identificar riesgos no cubiertos previo a liberación.
- Proveer evidencia trazable para auditoría y control de calidad.

---

## Convenciones

- **REQ:** Requerimiento funcional de negocio  
- **TC:** Caso de prueba funcional  
- **UAT:** Escenario de aceptación de usuario  
- **Estado QA:** Pass / Fail / Blocked / Not Executed  
- **Estado UAT:** Accepted / Rejected / Pending  

---

## Matriz de trazabilidad (Requerimiento -> Pruebas -> UAT)

| ID Req | Requerimiento de negocio | Impacto de negocio | Riesgo | Casos de prueba asociados | Escenarios UAT asociados | Estado QA | Estado UAT |
|------|--------------------------|--------------------|--------|---------------------------|--------------------------|-----------|------------|
| REQ-001 | El sistema debe permitir consultar pólizas activas y mostrar información completa y confiable. | Alto – Toma de decisiones operativas | Alto | TC-FUNC-001, TC-FUNC-003 | UAT-001, UAT-004 | Pass | Accepted |
| REQ-002 | El sistema debe manejar correctamente la consulta de pólizas inexistentes. | Medio – Confusión del usuario | Medio | TC-FUNC-002 | UAT-002 | Pass | Accepted |
| REQ-003 | El sistema debe identificar pólizas canceladas y restringir acciones no válidas. | Alto – Uso indebido del sistema | Alto | TC-FUNC-004 | UAT-003 | Pass | Accepted |
| REQ-004 | La información mostrada en pantalla debe coincidir con la fuente oficial de datos. | Alto – Información incorrecta | Alto | TC-FUNC-003 | UAT-004 | Pass | Accepted |
| REQ-005 | El acceso al módulo Consulta debe estar restringido por permisos de usuario. | Medio – Exposición de información | Medio | TC-FUNC-005 | UAT-005 | Pass | Accepted |

---

## Análisis de cobertura

- **Cobertura de requerimientos:** 100%
- **Cobertura de pruebas funcionales:** 100%
- **Cobertura UAT:** 100%
- **Requerimientos de riesgo Alto cubiertos:** 100%
- **Requerimientos sin UAT asociado:** 0

---

## Evaluación de riesgos QA

| Riesgo identificado | Mitigación aplicada | Evidencia |
|--------------------|---------------------|-----------|
| Información incorrecta al usuario | Validación UI vs base de datos | TC-FUNC-003 / UAT-004 |
| Uso de pólizas canceladas | Reglas de negocio validadas | TC-FUNC-004 / UAT-003 |
| Exposición de información sensible | Validación de permisos | TC-FUNC-005 / UAT-005 |

---

## Conclusión QA

Con base en la ejecución de pruebas funcionales y escenarios UAT, todos los requerimientos definidos para el módulo han sido cubiertos y aceptados, sin defectos abiertos de severidad alta o bloqueante.  
Desde la perspectiva de QA, el módulo cumple con los criterios de calidad necesarios para su liberación a producción.

---

## Aprobaciones

| Rol | Nombre | Fecha | Aprobación |
|----|--------|-------|------------|
| QA | [Nombre] | [Fecha] | ✔ |
| Usuario de Negocio | [Nombre] | [Fecha] | ✔ |
| Stakeholder | [Nombre] | [Fecha] | ✔ |

---
