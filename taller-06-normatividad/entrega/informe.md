# 📄 Informe Técnico del Taller

## 🔖 Nombre del Taller
_Taller 6 - Checklist de Cumplimiento Normativo_

## 👥 Integrantes del equipo
- Juan David Cetina Gómez (juancego@unisabana.edu.co)
- Ana Lucía Quintero Vargas (anaquiva@unisabana.edu.co)
- Mariana Salas Gutiérrez (marianasalgu@unisabana.edu.co)

## 🧠 Descripción general del trabajo
Describa brevemente el objetivo del taller y cómo se desarrolló la actividad.

## 🔧 Proceso de desarrollo
Explique cómo realizaron el trabajo: qué decisiones tomaron, qué herramientas utilizaron, qué aspectos modelaron primero y cómo lo fueron ajustando.

## 🧩 Análisis del modelo propuesto
Incluya un análisis sobre:
- **¿Cómo se estructura el modelo entregado?**
- **¿Cómo representa las necesidades del cliente?**
- **¿Qué supuestos se tomaron?**

## 📈 Diagrama final entregado
> (Inserte aquí una imagen o enlace al modelo-final.drawio / .asta / PDF)

## 📋 Tabla de Chacklist

| Nº | Categoría | Criterio de Cumplimiento | Nivel de Cumplimiento | Evidencia / Justificación | Recomendación |
|----|------------|---------------------------|------------------------|----------------------------|---------------------------|
| **1** | Finalidad del Tratamiento | Los datos se usan para trámites legítimos del Estado, tales como identidad, salud, impuestos y derechos civiles | **Alto** | Zajana S.A.S. utiliza datos personales únicamente con fines comerciales y analíticos legítimos, en cumplimiento de su política de tratamiento de datos y política de privacidad publicada en su página web. Los datos se procesan en servicios de Azure para generar *scores* e información que facilita la toma de decisiones en evaluación de riesgo y otorgamiento de crédito. Todo esto, protegido por medidas de ciberseguridad como **cifrado, Firewall, VNETs, NAT, DNS**, junto con herramientas como **Intune, Purview, Defender, Defender for Cloud, Sentinel, Log Analytics** y similares. | Mantener la alineación entre las finalidades declaradas y las actividades reales de tratamiento. Continuar publicando las actualizaciones de las políticas y avisos de privacidad conforme a cambios regulatorios. |
| **2** | Protección de Datos Sensibles | El sistema reconoce y maneja datos sensibles como historial crediticio o antecedentes de clientes | **Alto** | Zajana S.A.S. trabaja con algunos datos sensibles como la afiliación a la EPS y su tratamiento se específica en su política de tratamiento de datos personales, disponible en: [https://mareigua.co/politica-tratamiento-datos.html](https://mareigua.co/politica-tratamiento-datos.html). Sin embargo, su operación se centra en datos personales y datos semiprivados de carácter financiero/crediticio (Ley 1266/2008). | Continuar con el enfoque de manejo mínimo de datos sensibles y mantener las políticas de minimización, en especial para datos en tránsito. |
| **3** | Seguridad y Control Normativo | Se declara que se está sujeto a normativas como la Ley 1581 de 2012 e ISO 27001 | **Alto** | Zajana S.A.S. sigue los lineamientos de la Superintendencia Financiera de Colombia, específicamente la Ley de Habeas Data 1266 de 2008, el artículo 15 de la Constitución Política de Colombia, Ley 1581 de 2012, Decreto reglamentario 1377 de 2013 y Decreto 1081 de 2015. Además, se encuentra certificada en **ISO 27001**. | Continuar renovando la certificación ISO 27001 e integrando la gestión de privacidad bajo ISO 27701. Mantener actualizadas las referencias legales ante eventuales cambios normativos. |
| **4** | Trazabilidad Operativa | Se tiene registro de interacciones con entidades públicas | **Alto** | Zajana S.A.S. mantiene registro de las interacciones con entidades públicas y proveedores mediante plataformas integradas en Azure, como **Azure Monitor, Log Analytics y Sentinel (SIEM)**, que recopilan y correlacionan eventos de seguridad y operativos. Estas herramientas permiten conservar trazabilidad sobre conexiones, accesos, auditorías de datos y movimientos dentro de los servicios de nube. | Mantener la trazabilidad actual y continuar fortaleciendo la automatización de alertas con Azure Sentinel. Conservar los registros por los plazos legales establecidos. |
| **5** | Autenticación | Se implementan mecanismos de autenticación de usuarios | **Alto** | Zajana S.A.S. implementa mecanismos de autenticación para proteger el acceso a sus plataformas y datos en la nube. Utiliza **Microsoft Entra ID (Azure AD)** como directorio centralizado y **autenticación multifactor (MFA)**. Además, emplea **Azure Key Vault** para la protección de contraseñas, tokens y secretos, y la segmentación por roles (**RBAC**) en Azure, asegurando el principio de **mínimo privilegio** y **segregación de funciones**. | Continuar aplicando MFA y rotación de credenciales con políticas automáticas de Azure. Reforzar la educación de usuarios sobre autenticación segura y phishing. |
| **6** | Clasificación de Datos | Se realiza diferenciación entre datos personales y sensibles para su respectivo tratamiento | **Alto** | Zajana S.A.S. realiza la clasificación y tratamiento diferenciado de la información de acuerdo con su naturaleza: **datos personales, semiprivados y sensibles**, conforme a los principios establecidos en la Ley 1581 de 2012 y la Ley 1266 de 2008. La empresa no almacena datos sensibles, solo los utiliza en tránsito para generar los *scores*. Por ejemplo, no se guarda la información de la consulta, solo que se consultó a tal persona y el estado de la consulta (si fue exitosa o no). Se tiene **Microsoft Purview** para identificar y etiquetar datos personales, financieros o sensibles según reglas predefinidas. | Continuar con la política de no retención de datos sensibles y mantener actualizadas las etiquetas automáticas de Purview ante nuevos tipos de datos o normativas. |
| **7** | Consentimiento Informado | Realizar recolección libre, previa y específica del titular antes del tratamiento | **Alto** | Zajana S.A.S. tiene en sus términos y condiciones ([https://planeo.mareigua.co/terminosycondiciones.html](https://planeo.mareigua.co/terminosycondiciones.html)) que se solicita la autorización previa, expresa e informada de los titulares de la información. En general, la empresa obtiene la información para analizarla de fuentes de seguridad social y operadores de información, las cuales cuentan con sus propias políticas de tratamiento de datos y consentimientos informados. Respecto a su portal web, el usuario debe aceptar las **cookies** y la **política de privacidad**, donde se especifican los datos recolectados, su finalidad y el uso de cookies para mejorar la experiencia de navegación. | Mantener los mecanismos actuales de consentimiento informado y revisar periódicamente los textos legales de cookies y privacidad para reflejar cambios regulatorios o tecnológicos. |
| **8** | Derechos del Titular (ARCO) | Mecanismos implementados para acceder, rectificar, actualizar o suprimir datos según normativas | **Alto** | Zajana S.A.S. garantiza el ejercicio de los derechos **ARCO** (Acceso, Rectificación, Cancelación y Oposición) a través de los canales indicados en su política de tratamiento y privacidad, gestionados por el **Área de Servicios Compartidos**. Los titulares pueden solicitar actualización, rectificación o supresión de sus datos mediante correo electrónico o formulario web. Cada solicitud queda registrada y monitoreada con herramientas de auditoría en **Azure Monitor, Log Analytics y Microsoft Sentinel**, asegurando trazabilidad y cumplimiento de los plazos legales. | Continuar garantizando la trazabilidad de solicitudes ARCO y mantener los tiempos de respuesta dentro de los límites legales. |
| **9** | Retención y Supresión | Política de retención según finalidad y supresión o anonimización de datos | **Alto** | Zajana S.A.S. no almacena datos personales ni sensibles de forma permanente, únicamente conserva **metadatos de las consultas** realizadas (por ejemplo, si una verificación fue exitosa o no), cumpliendo con el principio de **finalidad y temporalidad** establecido en la Ley 1581 de 2012. Los datos procesados se mantienen en tránsito para generar análisis o puntajes crediticios y son eliminados una vez finaliza el proceso. Además, se cuenta con **Microsoft Purview** para aplicar políticas de retención, cifrado y acceso. | Mantener la política de no almacenamiento permanente y continuar aprovechando Purview para la aplicación automática de políticas de retención y cifrado. |
| **10** | Auditoría | Se realizan auditorías para verificar el cumplimiento de las políticas de protección de datos personales y la efectividad de los controles de seguridad de la información | **Alto** | Zajana S.A.S. cuenta con procesos formales de **auditoría interna y externa** para garantizar el cumplimiento de normativas y mantener la certificación **ISO 27001**. Las auditorías internas son realizadas por un equipo independiente, mientras que las auditorías externas anuales con **ICONTEC** validan la conformidad del Sistema de Gestión de Seguridad de la Información (SGSI). También se apoya en consultoría legal especializada y herramientas como **Defender for Cloud** y **Sentinel (SIEM)** para monitoreo continuo y generación de evidencias de cumplimiento. | Continuar realizando auditorías periódicas y manteniendo


## 🔍 Investigación complementaria
### Tema investigado:
(Ej: Buenas prácticas BPMN, comparación TOGAF vs C4, principios de seguridad STRIDE, etc.)

### Resumen:
Describa en 2–3 párrafos lo investigado, citando fuentes cuando sea necesario. Incluya cómo se relaciona con el taller.

## 📚 Referencias
- [1] Apellido, Nombre. *Título*. Año. URL o DOI.
- [2] Fuente oficial BPMN: https://www.omg.org/spec/BPMN/

---

_Este documento hace parte de la entrega del taller 6 del curso AREM (Arquitectura Empresarial) - Universidad de La Sabana._
