# 🗒️ Registro de Trabajo en Clase - Taller 6

## 📆 Fecha de la sesión
_25/10/2025_

## 👥 Integrantes presentes
- Juan David Cetina Gómez
- Ana Lucía Quintero Vargas
- Mariana Salas Gutiérrez

## 🧠 Actividades realizadas en clase

Durante la sesión se trabajó en el análisis del caso base GobData, un portal estatal de atención digital del gobierno dedicado a trámites ciudadanos. El objetivo principal fue identificar normativas aplicables y definir un checklist preliminar para el manejo de información sensible en sectores regulados. Se revisaron normas sectoriales específicas de Salud, Educación y Gobierno Digital, complementarias a las leyes generales de protección de datos, así como referencias internacionales como la ISO/IEC 27001:2022 y normativas locales relevantes, incluyendo lineamientos de MinSalud, MinTIC, SuperSalud y SFC.

En resumen, el equipo avanzó en la construcción del checklist, organizando la información de manera estructurada y documentando criterios de cumplimiento, nivel y evidencia basada en la normativa identificada. Se sentaron así las bases para continuar el análisis fuera de clase, donde se completará el registro de brechas y hallazgos relevantes y se afinarán las recomendaciones por cada categoría.

- **¿Qué se discutió con el equipo?**
  
  Se debatió cuáles normas y categorías eran más relevantes para el caso base y cómo organizar el análisis para cubrir todos los aspectos críticos del manejo de datos. El equipo coincidió en que el enfoque debía estar en las nueve categorías definidas: finalidad del tratamiento, protección de datos sensibles, seguridad y control normativo, trazabilidad operativa, autenticación, clasificación de datos, consentimiento informado, derechos del titular (ARCO) y retención y supresión. También se acordó cómo registrar la evidencia de cumplimiento, justificar niveles y documentar recomendaciones, dejando el espacio para registrar brechas o hallazgos en fases posteriores. Se definió la división de roles para avanzar de manera simultánea y asegurar cobertura completa de todas las categorías.

- **¿Qué decisiones de modelado se tomaron?**
  
  Se decidió organizar el análisis de cada categoría del checklist para identificar el nivel de cumplimiento y justificarlo con base en el tipo de datos procesados y las interacciones en la plataforma. El checklist se estructuró de manera que sirviera tanto para evaluar cumplimiento como para documentar brechas y hallazgos relevantes, dejando evidencia de dónde GobData requeriría acciones correctivas o mejoras.

- **¿Qué herramientas se usaron (papel, pizarra, draw.io, Astah)?**

  La principal herramienta utilizada fue Excel, que permitió documentar el checklist, organizar criterios de cumplimiento, evidencia y recomendaciones, y dejar espacio para el registro de brechas y hallazgos que se completará fuera de clase. Esta herramienta facilitó que los miembros del equipo trabajaran en paralelo de forma estructurada, sin necesidad de diagramas o modelado visual en esta fase.

- **¿Qué parte del trabajo se alcanzó a desarrollar?**

  Durante la sesión se avanzó en la construcción del checklist y en la evaluación preliminar de cada categoría según los criterios definidos, documentando nivel de cumplimiento, evidencia y recomendaciones iniciales. Se estableció la metodología para continuar el análisis fuera de clase, donde se completará el registro de brechas y hallazgos relevantes y se finalizarán las recomendaciones para cada categoría.

## 🧩 Boceto inicial del análisis (Checklist)

| Nº | Categoría | Criterio de Cumplimiento | Nivel de Cumplimiento | Evidencia / Justificación | Recomendación |
|---|-----------|-------------------------|----------------------|--------------------------|---------------|
| 1 | Finalidad del Tratamiento | Los datos se usan para trámites legítimos del Estado, tales como identidad, salud, impuestos y derechos civiles | Alto | GobData únicamente permite trámites asociados a obligaciones legales del ciudadano, en este caso identidad, salud e impuestos. Lo que define una finalidad concreta y de interés público | Publicar una relación de finalidades por entidad responsable para mayor transparencia |
| 2 | Protección de Datos Sensibles | El sistema reconoce y maneja datos sensibles como historias médicas o antecedentes de clientes | Alto | La plataforma integra servicios críticos como historia clínica y certificados judiciales, según las finalidades mencionadas. Lo que obliga a adoptar controles especiales de seguridad y confidencialidad conforme Ley 1581 | Implementar esquemas Zero Trust y monitoreo de accesos privilegiados |
| 3 | Seguridad y Control Normativo | Se declara que se está sujeto a normativas como la Ley 1581 de 2012 e ISO 27001 | Alto | El sistema maneja infraestructura estatal y procesos de autenticación centralizados, alineados a SGSI gubernamental y políticas MinTIC | Evidenciar auditorías internas y plan de mejora continua de seguridad |
| 4 | Trazabilidad Operativa | Se tiene registro de interacciones con entidades públicas | Parcial | Al ser una plataforma transaccional interinstitucional, requiere registrar cada acceso y modificación. Sin embargo, la trazabilidad no siempre es accesible para el ciudadano | Habilitar historial visible al titular de todos los accesos a su información, garantizando trazabilidad |
| 5 | Autenticación | Se implementan mecanismos de autenticación de usuarios | Parcial | Se utiliza validación documental, pero se requiere fortalecer autenticación según criticidad del trámite, dado que se manejan datos sensibles | Integrar autenticación multifactor y control de roles con privilegios mínimos |
| 6 | Clasificación de Datos | Se realiza diferenciación entre datos personales y sensibles para su respectivo tratamiento | Parcial | Se gestionan distintos niveles de criticidad, pero no se evidencia etiquetado interno ni segmentación estricta por nivel de sensibilidad, teniendo todos los datos centralizados | Implementar clasificación por capas, según la categoría de los trámites en línea y los datos tratados |
| 7 | Consentimiento Informado | Realizar recolección libre, previa y específica del titular antes del tratamiento | Bajo | Muchos datos son tratados bajo obligatoriedad legal sin consentimiento diferenciado por servicio, generando riesgo en usos adicionales o interoperabilidad, no teniendo consentimiento informado para el tratamiento de datos por parte de terceros | Incorporar consentimiento granular por entidad y tipo de dato, garantizando la recolección de datos teniendo autorización previa para el manejo de datos |
| 8 | Derechos del Titular (ARCO) | Mecanismos implementados para acceder, rectificar, actualizar o suprimir datos según normativas | Bajo | El ciudadano depende de cada entidad dueña del dato para modificaciones, pero GobData no provee una ruta unificada para ejercer derechos de los titulares de la información | Integrar portal ARCO centralizado con trazabilidad completa, garantizando información verídica y autorizada ajustada a las normativas |
| 9 | Retención y Supresión | Política de retención según finalidad y supresión o anonimización de datos | Bajo | La larga persistencia de datos y documentos dentro del portal sin depuración pone en riesgo su veracidad y exposición a brechas, sin tener una vida útil y supresión de información al finalizarla | Automatizar la eliminación o anonimización al cumplirse la finalidad legal, según se establezca en la normativa |

## ⚠️ Brechas y hallazgos relevantes identificados

Durante el análisis se identificaron las siguientes brechas principales en el cumplimiento normativo:

| Nº | Categoría | Brecha / Hallazgo | Impacto Potencial | Recomendación general |
|----|------------|------------------|-------------------|-----------------------|
| 1 | **Trazabilidad Operativa** | La trazabilidad no es accesible al ciudadano y carece de transparencia en los accesos a su información. | Riesgo de pérdida de confianza y vulneración del derecho de acceso a la información personal. | Implementar un módulo de historial de accesos visible para el titular, garantizando trazabilidad y transparencia. |
| 2 | **Autenticación** | Uso de autenticación básica sin mecanismos robustos de verificación de identidad. | Riesgo de suplantación o acceso indebido a datos sensibles. | Incorporar autenticación multifactor y control de privilegios mínimos. |
| 3 | **Clasificación de Datos** | Ausencia de etiquetado y segmentación de la información según nivel de sensibilidad. | Riesgo de tratamiento homogéneo de datos sensibles sin controles diferenciados. | Implementar un esquema de clasificación por capas que identifique datos personales, sensibles y públicos. |
| 4 | **Consentimiento Informado** | No existe consentimiento granular por servicio o entidad, ni registro de aceptación verificable. | Riesgo de tratamiento no autorizado y uso extendido de datos. | Diseñar un sistema de consentimiento previo, específico y verificable para cada finalidad o entidad. |
| 5 | **Derechos del Titular (ARCO)** | Falta un canal unificado para ejercer los derechos de acceso, rectificación, actualización o supresión. | Riesgo de incumplimiento de la Ley 1581 y pérdida de trazabilidad en la atención a titulares. | Crear un portal centralizado para la gestión de derechos ARCO con trazabilidad completa. |
| 6 | **Retención y Supresión** | No existen criterios claros de conservación ni depuración periódica de datos. | Riesgo de almacenamiento excesivo, exposición a brechas y vulneración del principio de finalidad. | Definir políticas de retención por tipo de trámite e implementar eliminación o anonimización automática. |

## 🔁 Tareas definidas para complementar el taller

Anote las responsabilidades acordadas entre los miembros del equipo para completar la entrega final:

| Tarea asignada | Responsable | Fecha estimada |
|----------------|-------------|----------------|
| Modelado final en Excel | Juan David Cetina Gómez y Mariana Salas Gutiérrez  | 30/10 |
| Redacción del informe     | Ana Lucía Quintero Vargas y Mariana Salas Gutiérrez | 28/10 |
| Investigación y referencias | Mariana Salas Gutiérrez | 30/10 |

---

_Este documento resume el trabajo colaborativo realizado durante la sesión del taller 6 en el curso AREM - Universidad de La Sabana._
