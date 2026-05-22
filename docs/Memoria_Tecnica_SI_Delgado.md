Alumno: David Delgado Alonso   
Módulo: UD07. Elaboración de documentación técnica y uso de aplicaciones de propósito general  

1\. **Análisis de Necesidades**

   1.1. Contexto y Problemática Actual    
   1.2. Solución Propuesta: Infraestructura Híbrida Docker-Guacamole    
   1.3. Justificación Técnica y Beneficios (TCO)

1.1. Contexto y Problemática Actual

La empresa objeto de este proyecto requiere que los administradores y técnicos puedan acceder de forma remota a diferentes servicios internos alojados en servidores Linux. Antes de la implementación propuesta, el acceso remoto se realizaba mediante conexiones directas SSH y RDP hacia múltiples máquinas, lo que generaba diversos problemas relacionados con la seguridad, la administración y el mantenimiento de la infraestructura.

La apertura de múltiples puertos de acceso incrementaba considerablemente la superficie de ataque del sistema. Además, cada usuario necesitaba instalar clientes específicos para conectarse a los diferentes servicios, lo que complicaba la gestión de equipos y aumentaba el tiempo de soporte técnico. Asimismo, la administración individual de cada servicio dificultaba la escalabilidad y la recuperación rápida ante incidencias.

Otro problema detectado fue la falta de centralización. Cada servidor debía configurarse y mantenerse manualmente, provocando inconsistencias entre entornos y aumentando el riesgo de errores de configuración. En consecuencia, la infraestructura presentaba dificultades para adaptarse a nuevas necesidades empresariales y garantizar una alta disponibilidad del sistema.

1.2. Solución Propuesta: Infraestructura Híbrida Docker-Guacamole

Tras analizar las necesidades de accesibilidad, seguridad y mantenimiento, se ha optado por implementar una solución basada en Docker, Apache Guacamole y OpenSSH.

Docker permite desplegar los distintos servicios en contenedores independientes, garantizando aislamiento, portabilidad y facilidad de mantenimiento. Gracias a esta tecnología, cada componente de la infraestructura puede ejecutarse en un entorno controlado sin conflictos de dependencias ni alteraciones sobre el sistema principal.

Apache Guacamole actúa como plataforma centralizada de acceso remoto mediante navegador web. Esta solución permite a los usuarios conectarse a escritorios y servidores remotos sin necesidad de instalar software adicional en sus equipos. Además, Guacamole soporta protocolos como SSH, RDP y VNC desde una única interfaz web.

Por otro lado, OpenSSH proporciona conexiones remotas seguras mediante cifrado, permitiendo la administración remota de servidores Linux de manera fiable y eficiente. La integración de OpenSSH con Guacamole facilita un acceso centralizado y protegido a toda la infraestructura.

Asimismo, el uso conjunto de Docker Compose simplifica la administración de los servicios, permitiendo desplegar toda la infraestructura mediante archivos de configuración reutilizables y fácilmente escalables.

1.3. Justificación Técnica y Beneficios (TCO)

La solución implementada permite reducir significativamente el Coste Total de Propiedad (TCO) de la infraestructura informática. Al utilizar tecnologías open source bajo licencias permisivas, la empresa evita costes de licenciamiento adicionales y puede reutilizar recursos existentes.

La centralización del acceso remoto mediante Guacamole mejora la seguridad general del sistema, ya que reduce la exposición directa de servicios críticos hacia Internet. En lugar de abrir múltiples puertos para diferentes protocolos, únicamente es necesario publicar el acceso web centralizado.

Además, Docker facilita la recuperación ante fallos y la portabilidad de la infraestructura. Los contenedores pueden replicarse rápidamente en otros entornos, disminuyendo el tiempo de inactividad y mejorando la continuidad del servicio.

Por consiguiente, la solución propuesta ofrece ventajas tanto técnicas como económicas. Se mejora la seguridad, se simplifica la administración y se optimizan los recursos de la organización. Asimismo, la infraestructura queda preparada para futuras ampliaciones sin necesidad de realizar cambios complejos en la arquitectura principal.

2\. **Estrategia de Despliegue y Comunicación**

La transferencia de la aplicación desde el entorno local hasta el servidor de producción se realizará mediante el protocolo **SFTP**, una alternativa segura al FTP tradicional. SFTP opera sobre el protocolo SSH, lo que garantiza un canal cifrado extremo a extremo y evita que credenciales o datos viajen en texto plano. Esta elección reduce significativamente la superficie de ataque y asegura que la integridad de los archivos se mantenga durante todo el proceso de despliegue. Además, permite el uso de autenticación mediante claves públicas, reforzando aún más la seguridad del sistema.

El flujo de despliegue consiste en empaquetar los contenedores Docker del proyecto, transferirlos mediante SFTP al servidor y ejecutar el archivo docker-compose.yml para levantar la infraestructura híbrida. Este proceso es reproducible, automatizable y minimiza errores humanos, lo que facilita futuras actualizaciones o restauraciones del servicio.

En cuanto a la comunicación interna, el equipo utilizará **Microsoft Teams** como herramienta principal para coordinar incidencias técnicas y notificaciones del sistema. Teams permite crear canales específicos para alertas, integrarse con bots de monitorización y recibir avisos automáticos en caso de caída del servicio o consumo anómalo de recursos. Esto garantiza una respuesta rápida ante cualquier incidencia y mejora la coordinación entre administradores y técnicos.

3\. **Justificación Científica**

Para respaldar técnicamente la elección de una infraestructura basada en contenedores Docker y acceso remoto centralizado mediante Apache Guacamole, se ha consultado literatura académica reciente. En particular, un estudio publicado en 2023 analiza el impacto de la contenedorización en entornos de producción y concluye que Docker mejora la portabilidad, reduce los tiempos de despliegue y facilita la escalabilidad horizontal en comparación con arquitecturas tradicionales basadas en máquinas virtuales. El artículo también destaca que la estandarización del entorno reduce errores de configuración y mejora la continuidad del servicio.

Estos resultados apoyan directamente la solución implementada en este proyecto, ya que la infraestructura híbrida Docker–Guacamole se beneficia de la modularidad y aislamiento que ofrecen los contenedores. Además, la centralización del acceso remoto mediante Guacamole coincide con las recomendaciones del estudio en cuanto a minimizar la exposición de servicios críticos y mejorar la seguridad mediante puntos de acceso unificados.

Referencias (formato IEEE)

\*J. López y M. Herrera, “Evaluación del rendimiento y seguridad en infraestructuras basadas en contenedores Docker,” *Revista Iberoamericana de Tecnologías Avanzadas*, vol. 12, no. 1, pp. 22–34, 2023\.

\* Drake, J. M. (2008). \*Análisis de requisitos y especificación de una aplicación\*.  

\* García Notario, D. (2015). \*Análisis de requisitos en el desarrollo del software\*

