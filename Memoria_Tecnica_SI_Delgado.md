Memoria Técnica SI

Portada

Proyecto: Infraestructura híbrida Docker – Guacamole
Alumno: David Delgado Alonso
Ciclo: Administración de Sistemas Informáticos en Red (ASIR)
Módulo: UD07. Elaboración de documentación técnica y uso de aplicaciones de propósito general
Fecha: 15 de mayo de 2026



Índice

Análisis de Necesidades
1.1. Contexto y Problemática Actual
1.2. Solución Propuesta: Infraestructura Híbrida Docker-Guacamole
1.3. Justificación Técnica y Beneficios (TCO)


1. Análisis de Necesidades

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

Referencias

Drake, J. M. (2008). Análisis de requisitos y especificación de una aplicación.
García Notario, D. (2015). Análisis de requisitos en el desarrollo del software
