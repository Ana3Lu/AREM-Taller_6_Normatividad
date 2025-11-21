# 📄 Informe Técnico del Taller

## 🔖 Nombre del Taller
_Taller 6 - Checklist de Cumplimiento Normativo_

## 👥 Integrantes del equipo

- Juan David Cetina Gómez (juancego@unisabana.edu.co)
- Ana Lucía Quintero Vargas (anaquiva@unisabana.edu.co)
- Mariana Salas Gutiérrez (marianasalgu@unisabana.edu.co)

## 🧠 Descripción general del trabajo

Este informe tiene como objetivo verificar los aspectos legales, normativos y de cumplimiento que aplican al sistema del cliente, utilizando listas de control basadas en marcos como ISO 27001, GDPR, Hábeas Data y la Ley 1581 de Protección de Datos en Colombia. Como ejercicio introductorio se trabajó con un caso base: GobData (Portal de Trámites Ciudadanos) para comprender la metodología. Posteriormente, se aplicó al cliente real (Zajana SAS). El análisis busca aplicar el mismo checklist al sistema del cliente, indicar los elementos que cumplen, los que tienen brechas y los que no aplican, redactar recomendaciones e investigar normativas locales o sectoriales que impacten a Zajana SAS (SFC).

## 🔧 Proceso de desarrollo

Inicialmente, se realiza el trabajo en clase, donde se revisa una plantilla de checklist de cumplimiento aplicada al caso GobData, se evalúa el cumplimiento por secciones (consentimiento, seguridad, retención, roles, etc.), justificando con base en el tipo de datos que se procesan y las interacciones en la plataforma, y registrando brechas o hallazgos relevantes. Las herramientas utilizadas para realizar el taller fueron Excel (para las tablas) junto con AEVA para realizar correcciones y buscar plantillas.

Después, para el caso del cliente se define que se necesita de otra reunión con el contacto para tratar el tema de normatividad. El checklist que se aplica es el mismo de GobData, salvo por el último criterio adicional de auditoría, ya que fue un punto clave que resaltó el Gerente de TI de Zajana SAS Con la tabla lista y las recomendaciones diligenciadas, se hizo una tabla con las brechas y hallazgos relevantes encontrados. En resumen, Zajana SAS es una empresa que trabaja con una gran cantidad de datos y sus productos, SaaS, se centran en el análisis de información financiera, por lo que toman diferentes medidas para proteger la información y cumplir con las normas. En general, mantiene un alto cumplimiento normativo y el riesgo principal que se identifica son los cambios que pueda implicar en el tratamiento de datos personales la migración a Snowflake.

## 🧩 Análisis del modelo propuesto

- **¿Cómo se estructura el modelo entregado?** 

  El modelo entregado se estructura a partir de un checklist normativo y una matriz de brechas, diseñados para evaluar el cumplimiento de Zajana SAS frente a las principales leyes y estándares aplicables a la protección de datos personales y la seguridad de la información. El checklist permite identificar el nivel de cumplimiento por categoría, basándose en criterios de la Ley 1266 de 2008, la Ley 1581 de 2012, los Decretos reglamentarios 1377 y 1081, y los controles de la ISO 27001, mientras que la matriz de brechas complementa el análisis al señalar los aspectos que requieren seguimiento o ajustes menores para mantener la alineación con la regulación vigente.

- **¿Cómo representa las necesidades del cliente?**

  El modelo representa adecuadamente las necesidades del cliente (Zajana SAS), enfocadas en garantizar la seguridad, trazabilidad y cumplimiento normativo durante la migración hacia Snowflake. Al incorporar controles de cumplimiento, clasificación automática, y políticas de retención gestionadas por Purview, se asegura la protección de la información crediticia y financiera procesada, en línea con los estándares de la Superintendencia Financiera de Colombia (SFC) y las leyes 1266 y 1581 de 2012.

- **¿Qué supuestos se tomaron?**

  Se asumió que la infraestructura tecnológica actual (en particular los servicios de Azure) garantiza trazabilidad, seguridad, confiabilidad, disponibilidad, integridad y consistencia del servicio. No obstante, se contemplaron posibles riesgos y brechas, principalmente derivados de la migración a Snowflake.

## 📋 Tabla de Checklist

| Nº | Categoría | Criterio de Cumplimiento | Nivel de Cumplimiento | Evidencia / Justificación | Recomendación |
|----|------------|---------------------------|------------------------|---------------------------|---------------------------|
| **1** | Finalidad del Tratamiento | Los datos se usan para trámites legítimos del Estado, tales como identidad, salud, impuestos y derechos civiles | **Alto** | Zajana SAS utiliza datos personales únicamente con fines comerciales y analíticos legítimos, en cumplimiento de su política de tratamiento de datos y política de privacidad publicada en su página web. Los datos se procesan en servicios de Azure para generar *scores* e información que facilita la toma de decisiones en evaluación de riesgo y otorgamiento de crédito. Todo esto, protegido por medidas de ciberseguridad como cifrado, Firewall, VNETs, NAT y DNS, junto con herramientas como Intune, Purview, Defender, Defender for Cloud, Sentinel, Log Analytics y similares. | Garantizar que durante la migración a Snowflake se mantengan las mismas condiciones de confidencialidad, cifrado y control de acceso declaradas en las políticas de tratamiento y privacidad. |
| **2** | Protección de Datos Sensibles | El sistema reconoce y maneja datos sensibles como historial crediticio o antecedentes de clientes | **Alto** | Zajana SAS trabaja con algunos datos sensibles como la afiliación a la EPS y su tratamiento se especifica en su política de tratamiento de datos personales, disponible en: [https://mareigua.co/politica-tratamiento-datos.html](https://mareigua.co/politica-tratamiento-datos.html). Sin embargo, su operación se centra en datos personales y datos semiprivados de carácter financiero/crediticio (Ley 1266/2008). | Asegurar que los mecanismos de cifrado y anonimización actuales se mantengan durante la migración de datos a Snowflake, especialmente en procesos de carga o replicación. |
| **3** | Seguridad y Control Normativo | Se declara que se está sujeto a normativas como la Ley 1581 de 2012 e ISO 27001 | **Alto** | Zajana SAS sigue los lineamientos de la Superintendencia Financiera de Colombia, específicamente la Ley de Hábeas Data 1266 de 2008, el artículo 15 de la Constitución Política de Colombia, Ley 1581 de 2012, Decreto reglamentario 1377 de 2013 y Decreto 1081 de 2015. Además, se encuentra certificada en ISO 27001. | Incluir la infraestructura y los procesos de Snowflake dentro del alcance de la certificación ISO 27001 y futuros controles de privacidad ISO 27701. |
| **4** | Trazabilidad Operativa | Se tiene registro de interacciones con entidades públicas | **Alto** | Zajana SAS mantiene registro de las interacciones con entidades públicas y proveedores mediante plataformas integradas en Azure, como Azure Monitor, Log Analytics y Sentinel (SIEM), que recopilan y correlacionan eventos de seguridad y operativos. Estas herramientas permiten conservar trazabilidad sobre conexiones, accesos, auditorías de datos y movimientos dentro de los servicios de nube. | Integrar la trazabilidad de Snowflake con Sentinel y Purview para mantener una cadena de custodia continua entre entornos Azure y Snowflake. |
| **5** | Clasificación de Datos | Se realiza diferenciación entre datos personales y sensibles para su respectivo tratamiento | **Alto** | Zajana SAS realiza la clasificación y tratamiento diferenciado de la información de acuerdo con su naturaleza: datos personales, semiprivados y sensibles, conforme a los principios establecidos en la Ley 1581 de 2012 y la Ley 1266 de 2008. La empresa no almacena datos sensibles, solo los utiliza en tránsito para generar los *scores*. Por ejemplo, no se guarda la información de la consulta, solo que se consultó a tal persona y el estado de la consulta (si fue exitosa o no). Se tiene Microsoft Purview para identificar y etiquetar datos personales, financieros o sensibles según reglas predefinidas. | Extender las etiquetas de clasificación y las políticas automatizadas de Purview hacia el entorno Snowflake, asegurando coherencia en el tratamiento de datos personales. |
| **6** | Retención y Supresión | Política de retención según finalidad y supresión o anonimización de datos | **Alto** | Zajana SAS no almacena datos personales ni sensibles de forma permanente, únicamente conserva metadatos de las consultas realizadas (por ejemplo, si una verificación fue exitosa o no), cumpliendo con el principio de finalidad y temporalidad establecido en la Ley 1581 de 2012. Los datos procesados se mantienen en tránsito para generar análisis o puntajes crediticios y son eliminados una vez finaliza el proceso. Además, se cuenta con Microsoft Purview para aplicar políticas de retención, cifrado y acceso. | Configurar en Snowflake políticas de retención automática mediante funcionalidades como *Time Travel* y *Fail-safe*, alineadas con las políticas de Purview. |
| **7** | Auditoría | Se realizan auditorías para verificar el cumplimiento de las políticas de protección de datos personales y la efectividad de los controles de seguridad de la información | **Alto** | Zajana SAS cuenta con procesos formales de auditoría interna y externa para garantizar el cumplimiento de normativas y mantener la certificación ISO 27001. Las auditorías internas son realizadas por un equipo independiente, mientras que las auditorías externas anuales con ICONTEC validan la conformidad del Sistema de Gestión de Seguridad de la Información (SGSI). También se apoya en consultoría legal especializada y herramientas como Defender for Cloud y Sentinel (SIEM) para monitoreo continuo y generación de evidencias de cumplimiento. | Continuar realizando auditorías periódicas y manteniendo la certificación ISO. |

## ⚠️ Brechas y hallazgos relevantes identificados

Durante el análisis se identificaron las siguientes brechas principales en el cumplimiento normativo:
| Nº | Categoría | Brecha / Hallazgo | Impacto Potencial | Recomendación general |
|----|------------|------------------|-------------------|-----------------------|
| **1** | Finalidad del Tratamiento | Se quiere migrar al nuevo entorno Snowflake, lo que puede generar ambigüedad frente al cumplimiento del principio de finalidad. | **Medio** | Actualizar la política de tratamiento de datos y los avisos de privacidad para incluir explícitamente el uso de Snowflake como entorno de análisis y asegurar que las finalidades se mantengan coherentes con las declaradas. |
| **6** | Clasificación de Datos | Las etiquetas automáticas de Microsoft Purview no se sincronizan aún con los esquemas y tablas de Snowflake. | **Medio** | Extender las políticas de clasificación y etiquetado de Purview a Snowflake mediante la integración de APIs y conectores de descubrimiento de datos. |
| **9** | Retención y Supresión | Las políticas de retención actuales no se han configurado nativamente en Snowflake, lo que podría afectar el cumplimiento del principio de temporalidad. | **Medio** | Implementar controles automáticos de retención y eliminación utilizando las funciones *Time Travel* y *Fail-safe* de Snowflake, alineadas con Purview. |

## 🖊️ Recomendaciones

A partir del análisis realizado, se concluye que Zajana SAS presenta un cumplimiento alto en materia de seguridad de la información y protección de datos personales. Sin embargo, la migración hacia Snowflake requiere ciertos ajustes para mantener la coherencia normativa y técnica del sistema. Se recomienda actualizar las políticas de tratamiento de datos y los avisos de privacidad, incorporando explícitamente el uso de Snowflake como nuevo entorno analítico, garantizando que las finalidades declaradas se mantengan sin alteración. Asimismo, se sugiere sincronizar las etiquetas automáticas de clasificación de Microsoft Purview con los esquemas y tablas de Snowflake, asegurando la consistencia en la gestión de datos personales y financieros. Finalmente, es importante configurar las políticas de retención y supresión de datos directamente en Snowflake, de modo que se mantenga el cumplimiento del principio de temporalidad y la alineación con las políticas de Purview. Con estas acciones, Zajana consolidará un entorno de datos unificado, seguro y totalmente conforme con las exigencias de la Superintendencia Financiera de Colombia y las leyes 1266 y 1581 de 2012.

## 🔍 Investigación complementaria
### Tema investigado: 
Leyes de seguridad de la información – Superintendencia Financiera de Colombia (SFC)

### Resumen:
Desde la Constitución Política de 1991 y la expedición de la Ley 1266 de 2008, se consolidó un marco legal que establece los derechos de los titulares, los deberes de las entidades vigiladas y la responsabilidad de la Superintendencia Financiera de Colombia (SFC) como ente regulador y garante del adecuado uso de la información. Este marco se complementa con la Ley 1581 de 2012 [1], que amplía la protección de los datos personales y fortalece los mecanismos de control sobre las operaciones financieras y crediticias.

Por su parte, en [2] se analiza el Hábeas Data como un derecho fundamental que otorga a los titulares la facultad de conocer, actualizar, rectificar o suprimir la información contenida en bases de datos públicas o privadas. Cifuentes señala que la creciente informatización del sistema financiero representa un desafío ético y jurídico, pues exige equilibrar la libertad individual y la eficiencia tecnológica con la protección de la intimidad y los derechos económicos del ciudadano. La jurisprudencia de la Corte Constitucional, a través de fallos como la SU-082 de 1995, consolidó este derecho como autónomo y de aplicación inmediata, sirviendo de base para las regulaciones emitidas por la SFC en materia de seguridad de la información, riesgo operativo y ciberseguridad financiera.

En el caso del taller de Zajana SAS, la aplicación de las normativas de la SFC demuestra la importancia de integrar el cumplimiento legal con la gestión tecnológica. Las directrices sobre riesgo de seguridad y ciberseguridad (SARCS), la Ley 1266 de 2008 y los estándares de la SFC permiten fortalecer las prácticas de protección de datos, trazabilidad, y control de acceso dentro del entorno financiero. De esta manera, el marco regulatorio colombiano no solo protege la información de los usuarios, sino que orienta la transformación digital segura de las organizaciones que operan o procesan información dentro del sistema financiero.

## 📚 Referencias
- [1] C. Pérez Álvarez, D. Acosta Giraldo y L. F. Arboleda Vargas, “Ley Estatutaria 1581 de 2012,” Trabajo de Grado, Instituto Universitario de Envigado, 2015.
- [2] E. Cifuentes Muñoz, “El Hábeas Data en Colombia,” Derecho PUCP, vol. 51, pp. 115–144, 1997.

---

_Este documento hace parte de la entrega del taller 6 del curso AREM (Arquitectura Empresarial) - Universidad de La Sabana._
