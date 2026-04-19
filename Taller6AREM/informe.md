# 📄 Informe Técnico del Taller

## 🔖 Nombre del Taller
_Taller 6 - Normatividad

## 👥 Integrantes del equipo
- Julián Mauricio Zafra (julianzamo@unisabana.edu.co)
- Santiago Araque (santiagoaral@unisabana.edu.co)
- Juan José Forero (juanfope@unisabana.edu.co)

## 🧠 Descripción general del trabajo
En el presente trabajo se llevó a cabo un proceso de evaluación de cumplimiento normativo y gobierno de datos aplicable al ecosistema tecnológico de THEGEEKHUB. El objetivo principal de este taller fue analizar cómo los procesos actuales del negocio y la futura arquitectura de infraestructura interactúan con el marco legal vigente de protección de datos personales y gestión de la información. La actividad se desarrolló mediante una auditoría estructurada, contrastando el flujo de información de los compradores y las transacciones contra los requerimientos normativos estándar, culminando en la identificación de vulnerabilidades legales y operativas en el manejo de los datos.

## 🔧 Proceso de desarrollo
Nuestro proceso de desarrollo se realizó tomando como base el modelo de infraestructura y el análisis de ciberseguridad elaborados previamente. Para estructurar este diagnóstico se realizo lo siguiente:

- Herramientas y decisiones: Tomamos la decisión de emplear matrices de control ofimáticas, diseñando un "Checklist General" para auditar de forma sistemática el ciclo de vida del dato.
- Modelado inicial: El aspecto que modelamos primero fue la trazabilidad de la información: desde el punto de captura inicial en los canales externos (redes sociales y el antiguo registro en Excel) hasta su persistencia en la Base de Datos Relacional Central y el Historial NoSQL.
- Ajustes: A medida que avanzábamos en la evaluación del flujo, fuimos ajustando el enfoque técnico hacia uno legal. Al cruzar los hallazgos del checklist con la arquitectura propuesta, documentamos sistemáticamente las deficiencias encontradas en una matriz de "Brechas Identificadas", priorizando aquellas que impactan directamente el servicio de ventas y el tracking financiero.

## 🧩 Análisis del modelo propuesto
El modelo se estructura en dos artefactos interconectados. Por un lado, el "Checklist General" categoriza los dominios normativos evaluados, tales como mecanismos de recolección, políticas de privacidad, almacenamiento seguro y derechos de los titulares. Por otro lado, el archivo de "Brechas Identificadas" actúa como un registro de hallazgos que detalla las discrepancias entre la operación actual de THEGEEKHUB y el deber ser normativo, clasificando el riesgo y requiriendo acciones correctivas.

Este modelo traduce un requerimiento legal en una necesidad técnica y de negocio. Para un emprendimiento que busca escalar hacia un E-commerce formal y, eventualmente, a un local físico en Colombia, asegurar la legalidad de sus bases de datos es tan crítico como la robustez de su código. El modelo le entrega a THEGEEKHUB una hoja de ruta para blindarse ante posibles sanciones, garantizando que la información de sus compradores y el historial de transacciones se gestione con transparencia y rigor.

Durante el análisis, se partió del supuesto de que THEGEEKHUB asumirá legalmente el rol de "Responsable del Tratamiento" de los datos de sus clientes. Adicionalmente, se asumió que los métodos actuales para obtener la autorización del tratamiento de datos, como conversaciones informales por Instagram o WhatsApp, carecen de la estructura técnica y legal requerida para ser auditables, por lo que la nueva pasarela a través del API Gateway deberá incluir mecanismos explícitos "Privacy by Design" antes de procesar cualquier transacción en MercadoPago o Nequi.

## 📈 Diagrama final entregado
El checklist se puede observar en el archivo .xlsx ubicado en entrega/checklist-gobdata_THEGEEKHUB.xlsx

## 📋 Tabla de actores, entidades o componentes (si aplica)

| Nombre del elemento | Tipo | Descripción | Responsable |
|---------------------|------|-------------|-------------|
| Ej: Paciente        | Actor | Usuario que agenda una cita médica | Cliente |

## 🔍 Investigación complementaria

### Tema investigado:
Gobernanza de datos personales: Habeas Data (Ley 1581 de 2012),
ISO/IEC 27001:2022 y lineamientos MinTIC para privacidad y seguridad
de la información en plataformas digitales colombianas.

### Resumen:

**Habeas Data y Ley 1581 de 2012**
En Colombia, el derecho al Habeas Data está consagrado en el artículo 15
de la Constitución Política y reglamentado por la Ley 1581 de 2012, la cual
establece que todo tratamiento de datos personales requiere una autorización
previa, expresa e informada del titular [1]. Su Decreto reglamentario 1377
de 2013 complementa esta norma definiendo los mecanismos para obtener dicha
autorización y el contenido mínimo de la Política de Tratamiento de
Información (PTI), que debe ser pública y especificar la finalidad del uso
de los datos y los derechos del titular [2]. El incumplimiento puede acarrear
sanciones de la Superintendencia de Industria y Comercio (SIC) de hasta
2.000 SMMLV.

**ISO/IEC 27001:2022 — Seguridad de la Información**
La norma ISO/IEC 27001 es el estándar internacional de referencia para la
gestión de la seguridad de la información y define un Sistema de Gestión de
Seguridad de la Información (SGSI) basado en el ciclo PHVA
(Planear-Hacer-Verificar-Actuar) [3]. Para plataformas digitales, dos
controles son especialmente críticos: el control A.5.15 sobre gestión de
acceso lógico mediante autenticación y roles, y el control A.8.8 sobre
gestión de vulnerabilidades técnicas, que incluye la realización de escaneos
periódicos automatizados [3]. Ambos controles corresponden directamente a las
categorías evaluadas en el checklist del presente taller.

**Lineamientos MinTIC — Privacidad desde el Diseño e Inventario de Activos**
El Ministerio de Tecnologías de la Información y las Comunicaciones (MinTIC)
ha publicado la Guía de Gestión de Activos de Información, alineada con ISO
27001, que establece la necesidad de documentar todos los activos críticos
—servidores, APIs, bases de datos— como primer paso para protegerlos [4].
Complementariamente, MinTIC promueve el principio de *Privacy by Design*,
originalmente formulado por Cavoukian [5], el cual plantea que la privacidad
debe ser una característica intrínseca del sistema desde su concepción y no
un añadido posterior, implicando minimización de datos, anonimización donde
sea posible y documentación formal de los criterios de protección aplicados
durante el desarrollo [4][5].

Estos tres marcos normativos y técnicos son complementarios: la Ley 1581
establece el *qué* (derechos y obligaciones legales), ISO 27001 el *cómo*
(controles técnicos y organizacionales), y los lineamientos MinTIC el
contexto local de aplicación para empresas que operan en Colombia.

## 📚 Referencias

- [1] Congreso de Colombia. *Ley 1581 de 2012 — Por la cual se dictan
  disposiciones generales para la protección de datos personales*. 2012.
  Disponible en: https://www.funcionpublica.gov.co/eva/gestornormativo/norma.php?i=49981

- [2] Presidencia de la República de Colombia. *Decreto 1377 de 2013 —
  Por el cual se reglamenta parcialmente la Ley 1581 de 2012*. 2013.
  Disponible en: https://www.sic.gov.co/decreto-1377-de-2013

- [3] International Organization for Standardization. *ISO/IEC 27001:2022 —
  Information security, cybersecurity and privacy protection —
  Information security management systems — Requirements*. ISO, 2022.
  Disponible en: https://www.iso.org/standard/27001

- [4] MinTIC Colombia. *Guía de Gestión de Activos de Información —
  Seguridad y Privacidad de la Información, versión 1.1*. Ministerio de
  Tecnologías de la Información y las Comunicaciones, 2016.
  Disponible en: https://www.mintic.gov.co/gestionti/615/articles-5482_G4_Gestion_Activos.pdf

- [5] Cavoukian, A. *Privacy by Design — The 7 Foundational Principles*.
  Information and Privacy Commissioner of Ontario, 2009.
  Disponible en: https://www.ipc.on.ca/wp-content/uploads/resources/7foundationalprinciples.pdf

_Este documento hace parte de la entrega del taller X del curso AREM (Arquitectura Empresarial) - Universidad de La Sabana._
