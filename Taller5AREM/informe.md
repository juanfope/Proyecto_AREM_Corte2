# 📄 Informe Técnico del Taller

## 🔖 Nombre del Taller
_Taller 5: Evaluación de Seguridad con STRIDE_

## 👥 Integrantes del equipo
- Julián Mauricio Zafra (julianzamo@unisabana.edu.co)
- Santiago Araque (santiagoaral@unisabana.edu.co)
- Juan José Forero (juanfope@unisabana.edu.co)

## 🧠 Descripción general del trabajo
En el presente trabajo se llevó acabo el analisis STRIDE para THEGEEKHUB tomando como referencia el desgloce de procesos y arquitectura propuesta para la migracion de sus procesos actuales a un entorno cloud con mejor escalabilidad, seguridad, control financiero y seguimiento de las acciones y ventas realizadas. El analisis STRIDE servira como una guia que exponga los riesgos mas fundamentales y criticos que puedan amenazar a la arquitectura de THEGEEKHUB, para permitir de esta forma abordar las diferentes medidas a emplear como estrategias de mitigación y las areas asociadas que llevaran a cabo esta tarea.

## 🔧 Proceso de desarrollo
Para esta etapa, tomamos la decisión de aplicar la metodología STRIDE para llevar a cabo una evaluación de seguridad estructurada sobre la arquitectura de THEGEEKHUB.

Hicimos uso de herramientas ofimáticas (hojas de cálculo) para estructurar una matriz de análisis y una leyenda que nos permitiera estandarizar la evaluación de las vulnerabilidades. El aspecto que modelamos primero fueron los límites de confianza y los puntos de entrada del sistema, específicamente el API Gateway / Controlador y la interacción con los canales externos (Instagram, Facebook, Mercado Libre). A medida que avanzamos, fuimos ajustando el nivel de profundidad del análisis al iterar sobre los servicios internos (Servicio de Ventas y Servicio de Tracking Financiero) y las bases de datos, evaluando sistemáticamente los riesgos de suplantación de identidad, manipulación de datos, repudio, divulgación de información, denegación de servicio y elevación de privilegios (STRIDE) en cada nodo de la arquitectura.

## 🧩 Análisis del modelo propuesto
El modelo se estructura a través de una matriz de evaluación de riesgos detallada en los anexos (Análisis STRIDE y Leyenda STRIDE). Esta herramienta desglosa cada componente de la infraestructura (desde la Cola de Eventos hasta el Historial NoSQL), categorizando las amenazas detectadas bajo las seis dimensiones de la metodología y emparejándolas con posibles vulnerabilidades técnicas y sus respectivas estrategias de mitigación.

Este análisis responde directamente al objetivo de THEGEEKHUB de expandirse hacia un sistema de E-commerce más profesional y seguro. Al identificar cómo un atacante podría alterar los registros de inventario o interceptar la información financiera de los compradores, el modelo provee una ruta de acción clara para blindar los datos. Esto garantiza la consistencia de la información y protege la confianza de los clientes, un factor vital para un negocio que busca formalizar sus ventas digitales.

Durante el modelado, partimos del supuesto de que el nuevo sistema operará en un entorno conectado a internet que expone APIs para la validación de ventas y pagos. Adicionalmente, se asumió que las integraciones con pasarelas externas (MercadoPago, Nequi) se manejan mediante tokens que son un objetivo de alto valor, y que el Dashboard de Socios (anteriormente manejado en Excel) requiere ahora de controles de acceso basados en roles (RBAC) muy estrictos para evitar que usuarios no autorizados escalen privilegios y alteren la Base de Datos Relacional Central.

## 📈 Diagrama final entregado
La evaluacion con STRIDE se puede observaren el archivo .xlsx

## 🔍 Investigación complementaria
### Tema investigado:
Buenas practicas de seguridad en la nube y prevencion de amenazas pertenecientes a STRIDE

### Resumen:
Debido al acelerado ritmo de crecimiento que tiene la tecnologia y sobretodo las conexiones en la nube nunca se esta excento de posibles amenazas, por lo que es una buena idea estar al tanto de los mayores riesgos actuales y lo que cada persona puede hacer para blindarse contra ello. Las personas son el elemento mas vulnerable de la seguridad informatica, aun mas que los sistemas por lo que una gran practica de la que se puede hacer usa para evitar por ejemplo el manejo de credenciales legitimas por parte de usuarios no autorizados es el uso de contraseñas fuertes en conjunto con MFA. El MFA ofrece una capa adicional de protección que puede prevenir la incurrencia en el algunas de las practicas descritas en STRIDE como el spoofing, garantizando que solo el dueño de las credenciales pueda hacer uso de ellas.

STRIDE no solo se limita a abarcar riesgos como el spoofing si no a establecer un conjunto general de practicas a corregir para abordar las amenazas y extiende principios como el de la triada CIA al incluir tambien el no repudio. Es de alta prioridad realizar un desgloce de los diferentes elementos de un  sistema para realizar el analisis STRIDE correspondiente, se deben tener en cuenta tanto elementos internos como externos pues el tipo de vulnerabilidades que pueden presentar son diferentes, asi como los procesos a asociados a cada uno. Adicionalmente STRIDE utiliza principios similares a los que se usan en el desarrollo de matrices de riesgo al realizar una categorizacion de nivel de riesgo e impacto que tienen el proposito de priorizar las mayores amenazas.

Finalmente, investigamos que STRIDE se enfoca tambien en los controles preventivos por encima de los reactivos, busca parchar las posibles vulnerabilidades bien sea reduciendo un riesgo particular o estableciendo un entorno controlado que de a individuos y organizaciones un entorno controlado en el cual puedan reaccionar de forma adecuada bajo protocolos preestablecidos.

## 📚 Referencias
[1] STRIDE Framework for Healthcare IT Threat Modeling. (2026, 19 marzo). Censinet, Inc. https://censinet-com.translate.goog/perspectives/stride-framework-healthcare-it-threat-modeling?_x_tr_sl=en&_x_tr_tl=es&_x_tr_hl=es&_x_tr_pto=tc
[2] Bitdefender. (2025, 7 marzo). Buenas Prácticas de Ciberseguridad para Particulares - Bitdefender. https://www.bitdefender.es/consumer/support/answer/105298/
Jegeib. (s. f.). Amenazas: Herramienta de modelado de amenazas de Microsoft: Azure. Microsoft Learn. https://learn.microsoft.com/es-es/azure/security/develop/threat-modeling-tool-threats

---

_Este documento hace parte de la entrega del taller X del curso AREM (Arquitectura Empresarial) - Universidad de La Sabana._
