## Explorar Azure Monitor

Azure Monitor ofrece una solución completa para recopilar, analizar y actuar en la telemetría desde los entornos local y en la nube. Esta información le ayudará a conocer el rendimiento de las aplicaciones y a identificar de manera proactiva los problemas que les afectan y los recursos de los que dependen.

El siguiente diagrama proporciona una visión general de Azure Monitor. En el centro del diagrama están los almacenes de datos de las métricas y los registros, que son los dos tipos fundamentales de datos que se utilizan en Azure Monitor. En la parte izquierda están los orígenes de datos de supervisión que rellenan estos almacenes de datos. En la derecha puede ver las diferentes funciones que realiza Azure Monitor con los datos recopilados. Esto incluye acciones como el análisis, la alerta y la transmisión a sistemas externos.

### ¿Qué datos recopila Azure Monitor?

Azure Monitor puede recopilar datos de diversos orígenes. como la aplicación y cualquier sistema operativo o servicio en los que se base, o incluso la propia plataforma. Azure Monitor recopila datos de cada uno de los siguientes niveles:

- Datos de supervisión de aplicaciones: datos sobre el rendimiento y la funcionalidad del código que ha escrito, independientemente de la plataforma.

- Datos de supervisión del sistema operativo invitado: datos sobre el sistema operativo en el que se ejecuta la aplicación. La aplicación se puede ejecutar en Azure, en otra nube o en el entorno local.

- Datos de supervisión de recursos de Azure: datos acerca del funcionamiento de un recurso de Azure.

- Datos de supervisión de la suscripción de Azure: datos sobre el funcionamiento y la administración de una suscripción de Azure, así como sobre el estado y el funcionamiento del propio Azure.

- Datos de supervisión del inquilino de Azure: datos sobre el funcionamiento de los servicios de Azure en el nivel del inquilino, como Azure Active Directory.

### Supervisión de la plataforma de datos

Todos los datos que recopila Azure Monitor pueden clasificarse como uno de los dos tipos fundamentales: métricas y registros. Las métricas son valores numéricos que describen algunos aspectos de un sistema en un momento dado en el tiempo. Las métricas son ligeras y capaces de admitir escenarios de tiempo casi real. Los registros contienen distintos tipos de datos organizados en registros con diferentes conjuntos de propiedades para cada tipo. Los datos de telemetría, como los eventos y los seguimientos, se almacenan como registros junto con los datos de rendimiento para poder analizarlos de forma combinada.

Para muchos recursos de Azure, verá los datos de las métricas que recopila Azure Monitor directamente en la página de información general de Azure Portal. Los datos de registro recopilados por Azure Monitor se pueden analizar con consultas para recuperar, consolidar y analizar rápidamente los datos recopilados. Puede crear y probar consultas con Log Analytics en Azure Portal.

### Insights y visualizaciones seleccionadas

Los datos de supervisión solo resultan útiles si aportan una mayor visibilidad sobre el funcionamiento del entorno informático. Algunos proveedores de recursos de Azure tienen una "visualización seleccionada" que proporciona una experiencia de supervisión personalizada para ese servicio o conjunto de servicios concretos. Por lo general, requieren una configuración mínima. Las visualizaciones más grandes y seleccionadas se conocen como "conclusiones" y se marcan con ese nombre en la documentación y en Azure Portal. Ejemplos:

- Application Insights: este servicio supervisa la disponibilidad, el rendimiento y el uso de las aplicaciones web, tanto si están hospedadas en la nube como en un entorno local. Esta solución utiliza la eficaz plataforma de análisis de datos de Azure Monitor para proporcionar información exhaustiva sobre las operaciones de la aplicación y permite diagnosticar errores sin esperar a que un usuario los notifique.

- Container Insights: este servicio supervisa el rendimiento de las cargas de trabajo de contenedor que se implementan en clústeres de Kubernetes administrados y que están hospedados en Azure Kubernetes Service (AKS) y Azure Container Instances. Proporciona información sobre el rendimiento recopilando métricas de los controladores, los nodos y los contenedores disponibles en Kubernetes mediante Metrics API. También se recopilan registros del contenedor.

- VM Insights: este servicio supervisa las máquinas virtuales (VM) de Azure a escala. Analiza el rendimiento y el estado de las máquinas virtuales Windows y Linux, e identifica los distintos procesos y dependencias interconectadas en procesos externos.

## Exploración de Application Insights

Application Insights es una característica de Azure Monitor que es un servicio de Application Performance Management (APM) extensible para desarrolladores y profesionales de DevOps. Úselo para supervisar las aplicaciones en directo. Detectará automáticamente anomalías en el rendimiento e incluye eficaces herramientas de análisis que le ayudan a diagnosticar problemas y a saber lo que hacen realmente los usuarios con la aplicación. Está diseñado para ayudarle a mejorar continuamente el rendimiento y la facilidad de uso.

### Funcionamiento de Application Insights

Instale un paquete de instrumentación pequeño (SDK) en la aplicación o habilite Application Insights mediante el agente de Application Insights cuando se admita. La instrumentación supervisa la aplicación y dirige los datos de telemetría a un recurso de Azure Application Insights mediante un GUID único al que se hace referencia como una clave de instrumentación.

No solo puede instrumentar la aplicación de servicio web, sino también todos los componentes en segundo plano y JavaScript en las propias páginas web. La aplicación y sus componentes se pueden ejecutar en cualquier lugar; no tienen que estar hospedados en Azure.

Además, puede obtener la telemetría de los entornos del host, como pueden ser contadores de rendimiento, diagnósticos de Azure o registros de Docker. También puede configurar pruebas web que envíen periódicamente solicitudes sintéticas al servicio web.

Todos estos flujos de telemetría están integrados en Azure Monitor. En Azure Portal, puede aplicar versátiles herramientas de análisis y búsqueda a los datos sin procesar. El impacto sobre el rendimiento de la aplicación es pequeño. Las llamadas de seguimiento no suponen ningún tipo de bloqueo y se agrupan por lotes y se envían en un subproceso aparte.

### Qué supervisa Application Insights

Application Insights está dirigido al equipo de desarrollo y sirve ayudarle a conocer el rendimiento de una aplicación y cómo se utiliza. Supervisa:

- Tasas de solicitud, tiempos de respuesta y tasas de error. Averigüe qué páginas que son las más conocidas, en qué momento del día y dónde están los usuarios. Vea qué páginas presentan mejor rendimiento. Si los tiempos de respuesta y las tasas de error aumentan cuando hay más solicitudes, quizás tiene un problema de recursos.
- Tasas de dependencia, tiempos de respuesta y tasa de error. Averigüe si los servicios externos le ralentizan.
- Excepciones: Analice las estadísticas agregadas o seleccione instancias concretas y profundice en el seguimiento de la pila y las solicitudes relacionadas. Se notifican tanto las excepciones de servidor como las de explorador.
- Vistas de página y rendimiento de carga Notificados por los exploradores de los usuarios.
- Llamadas AJAX desde páginas web. Tasas, tiempos de respuesta y tasas de error.
N- úmero de usuarios y sesiones.
- Contadores de rendimiento de las máquinas de servidor de Windows o Linux, como CPU, memoria y uso de la red.
- Diagnóstico de host de Docker o Azure.
- Registros de seguimiento de diagnóstico de la aplicación - De esta forma puede correlacionar eventos de seguimiento con las solicitudes.
- Métricas y eventos personalizados que usted mismo escribe en el código de cliente o servidor para realizar un seguimiento de eventos empresariales, como artículos vendidos o partidas ganadas.

## Uso de Application Insights

Application Insights es uno de los muchos servicios hospedados en Microsoft Azure y los datos de telemetría se envían ahí para analizarlos y mostrarlos. Es gratuito registrarse y, si elige el plan de precios básico de Application Insights, no tendrá ningún cargo hasta que la aplicación haya crecido hasta tener un uso sustancial.

Hay varias maneras de empezar a supervisar y analizar el rendimiento de las aplicaciones:

- En tiempo de ejecución: instrumente la aplicación web en el servidor. Ideal para las aplicaciones ya implementadas. Evita toda actualización del código.
- En tiempo de desarrollo: agregue Application Insights al código. Le permite personalizar la recopilación de telemetría personalizada y enviar telemetría adicional.
- Instrumente sus páginas web para la vista de la página, AJAX y otros datos de telemetría del lado cliente.
- Analice el uso de aplicaciones móviles mediante la integración con Visual Studio App Center.
- Pruebas de disponibilidad : haga ping a su sitio web de manera regular desde nuestros servidores.

## Detección de métricas basadas en registros

Las métricas basadas en registros de Application Insights le permiten analizar el estado de las aplicaciones supervisadas, crear paneles eficaces y configurar alertas. Existen dos tipos de métricas:

- Las métricas basadas en registros subyacentes se traducen en consultas de Kusto de eventos almacenados.
- Las métricas estándar se almacenan como series temporales previamente agregadas.

Puesto que las métricas estándar se agregan previamente durante la recopilación, tienen un mejor rendimiento en el momento de la consulta. Esto las convierte en una opción mejor para los paneles y las alertas en tiempo real. Las métricas basadas en registros tienen más dimensiones, lo que las convierte en la mejor opción para el análisis de datos y los diagnósticos ad hoc. Use el selector del espacio de nombres para cambiar entre las métricas basadas en registros y las métricas estándar en el explorador de métricas.

### Métricas basadas en registros

Los desarrolladores pueden usar el SDK para emitir estos eventos manualmente (escribiendo código que invoca explícitamente el SDK) o pueden usar la recopilación automática de eventos de la instrumentación automática. En cualquier caso, el servidor back-end de Application Insights almacena todos los eventos recopilados como registros y las hojas de Application Insights en Azure Portal actúan como herramienta de análisis y diagnóstico para visualizar los datos basados en eventos de los registros.

El uso de registros para conservar un conjunto completo de eventos puede aportar gran valor al análisis y el diagnóstico. Por ejemplo, puede obtener el número exacto de solicitudes enviadas a una dirección URL determinada con el número de usuarios distintos que realizaron estas llamadas. O puede obtener seguimientos de diagnóstico detallados, incluidas las excepciones y llamadas de dependencia para cualquier sesión de usuario. Con este tipo de información puede mejorar considerablemente la visibilidad sobre el estado y el uso de la aplicación, lo que permite reducir el tiempo necesario diagnosticar los problemas de una aplicación.

Al mismo tiempo, recopilar un conjunto completo de eventos puede resultar poco práctico (o incluso imposible) en el caso de aplicaciones que generan un gran volumen de telemetría. En aquellos casos en los que el volumen de eventos es demasiado alto, Application Insights implementa varias técnicas de reducción del volumen de datos de telemetría, tales como muestreo y filtrado, que reducen el número de eventos recopilados y almacenados. Lamentablemente, reducir el número de eventos almacenados reduce también la precisión de las métricas que, en segundo plano, deben realizar agregaciones en tiempo de consulta de los eventos almacenados en los registros.

## Métricas agregadas previamente (métricas estándar)

Las métricas agregadas previamente no se almacenan como eventos individuales con muchas propiedades. En su lugar, se almacenan como series temporales previamente agregadas y solo con las dimensiones clave. Esto hace que las nuevas métricas sean superiores en tiempo de consulta: la recuperación de datos es mucho más rápida y requiere menos capacidad de proceso. Esto permite nuevos escenarios como las alertas casi en tiempo real sobre las dimensiones de las métricas y paneles con más capacidad de respuesta y muchos más.

Los SDK más recientes (SDK de Application Insights 2.7 o versiones posteriores para .NET) agregan previamente las métricas durante la recopilación. Esto se aplica a las métricas estándar enviadas de forma predeterminada, por lo que la precisión no se ve afectada por el muestreo o el filtrado. También se aplica a las métricas personalizadas enviadas mediante GetMetric, lo que genera una ingesta de datos y un costo menores.

En el caso de los SDK que no implementan la agregación previa (es decir, las versiones anteriores del SDK de Application Insights o la instrumentación del explorador) el servidor back-end de Application Insights sigue agregando los eventos recibidos por la el punto de conexión de recopilación de eventos de Application Insights para rellenar las nuevas métricas. Esto significa que aunque no se beneficie del menor volumen de datos que se transmite a través del cable, podrá seguir usando las métricas agregadas previamente para experimentar un mejor rendimiento y aprovechar la compatibilidad con las alertas dimensionales casi en tiempo real con los SDK que no agregan previamente las métricas durante la recopilación.

Merece la pena mencionar que el punto de conexión de la colección agrega previamente los eventos antes de muestreo de ingesta, lo que significa que el muestreo de ingesta no afectará nunca a la precisión de las métricas agregadas previamente, independientemente de la versión SDK que use con su aplicación.

## Instrumentación de una aplicación para supervisión

Anteriormente en este módulo resaltamos que una aplicación se puede supervisar en Application Insights con o sin agregar código. En esta unidad, este tema se trata con más detalle.

### Instrumentación automática

La instrumentación automática permite habilitar la supervisión de las aplicaciones con Application Insights sin modificar el código.

Application Insights se integra con varios proveedores de recursos y funciona en distintos entornos. En resumen, solo debe habilitar y, en algunos casos, configurar el agente, que recopilará la telemetría automáticamente. En unos instantes, podrá ver las métricas, las solicitudes y las dependencias en el recurso de Application Insights, lo que le permitirá detectar el origen de los posibles problemas antes de que se produzcan y analizar la causa raíz con la vista de transacciones integral.

### Instrumentación para realizar un seguimiento distribuido

El seguimiento distribuido es el equivalente de las pilas de llamadas para arquitecturas de microservicios y en la nube modernas, junto con un generador de perfiles de rendimiento simple. En Azure Monitor, se proporcionan dos experiencias para consumir datos de seguimiento distribuido. La primera es la vista de diagnósticos de transacción, que es como una pila de llamadas con una dimensión de tiempo adicional. La vista de diagnósticos de transacción proporciona visibilidad sobre una sola transacción o solicitud y resulta útil para encontrar la causa raíz de problemas de confiabilidad y cuellos de botella de rendimiento por cada solicitud.

Azure Monitor ofrece también una vista de mapa de aplicación que agrega muchas transacciones para mostrar una vista topológica de cómo interactúan los sistemas y cuáles son las tasas promedio de rendimiento y de errores.

Habilitar el seguimiento distribuido de los servicios de una aplicación es tan simple como agregar el SDK o la biblioteca adecuada a cada servicio, en función del lenguaje en el que se implementó el servicio.

#### Habilitación mediante los SDK de Application Insights

Los SDK de Application Insights para .NET, .NET Core, Java, Node.js y JavaScript admiten el seguimiento distribuido de forma nativa.

Con el SDK de Application Insights adecuado instalado y configurado, la información de seguimiento se recopila automáticamente para los marcos de trabajo, bibliotecas y tecnologías más populares mediante los auto-recopiladores de dependencias del SDK. La lista completa de las tecnologías compatibles está disponible en la documentación de la recopilación automática de dependencias.

Asimismo, puede realizar un seguimiento manual de cualquier tecnología con una llamada a TrackDependency en TelemetryClient.

#### Habilitación mediante OpenCensus

Además de los SDK de Application Insights, Application Insights también admite el seguimiento distribuido mediante OpenCensus. OpenCensus es una distribución de bibliotecas de código abierto e independiente del proveedor que proporciona recopilación de métricas y seguimiento distribuido para los servicios. También permite a la comunidad de código abierto habilitar el seguimiento distribuido con tecnologías conocidas como Redis, Memcached o MongoDB.

## Selección de una prueba de disponibilidad

Después de haber implementado la aplicación o el sitio web, puede configurar pruebas periódicas para supervisar la disponibilidad y capacidad de respuesta. Application Insights envía solicitudes web a la aplicación a intervalos regulares desde puntos de todo el mundo. Puede enviar una alerta si la aplicación no responde o si responde de manera demasiada lenta.

Puede configurar pruebas de disponibilidad para cualquier punto de conexión HTTP o HTTPS que sea accesible desde la red pública de Internet. No hace falta realizar cambios en el sitio web que está probando. De hecho, ni siquiera es necesario que sea un sitio de su propiedad. Puede probar la disponibilidad de una API de REST de la que depende su servicio.

Puede crear hasta 100 pruebas de disponibilidad por recurso de Application Insights, y existen tres tipos de pruebas de disponibilidad:

- Prueba de ping de URL (clásica): puede crear esta prueba sencilla a través del portal para validar si un punto de conexión responde y medir el rendimiento asociado a esa respuesta. También puede establecer criterios de éxito personalizados junto con características más avanzadas, como analizar solicitudes dependientes y permitir reintentos.
- Prueba estándar (versión preliminar): esta prueba de solicitud única es similar a la prueba de ping de URL. Incluye la validez del certificado SSL, la comprobación proactiva de la duración, el verbo de solicitud HTTP (por ejemplo, GET, HEAD o POST), los encabezados personalizados y los datos personalizados asociados a la solicitud HTTP.
- Prueba TrackAvailability personalizada: si decide crear una aplicación personalizada para ejecutar pruebas de disponibilidad, puede usar el método TrackAvailability() para enviar los resultados a Application Insights. La prueba TrackAvailability personalizada es la solución admitida a largo plazo para escenarios de prueba de autenticación o de varias solicitudes.

## Solución de problemas de rendimiento de aplicaciones mediante el Mapa de aplicación

El mapa de aplicación le ayuda a detectar los cuellos de botella en el rendimiento o las zonas activas con error en todos los componentes de la aplicación distribuida. Cada nodo del mapa representa un componente de aplicación o sus dependencias, e incluye el KPI de mantenimiento y el estado de alerta. Puede hacer clic a través de cualquier componente para ver un diagnóstico más detallado, como los eventos de Application Insights. Si su aplicación usa los servicios de Azure, también puede hacer clic por los diagnósticos de Azure, como las recomendaciones SQL Database Advisor.

Los componentes son partes que se pueden implementar independientemente de su aplicación de microservicios o distribuida. Los equipos de operaciones y los desarrolladores pueden ver el código o acceder a la telemetría que generan estos componentes de la aplicación.

- Los componentes son diferentes de las dependencias externas "observadas", como SQL, Event Hubs y otras, a las que su equipo u organización no pueden acceder (código o telemetría).

- Los componentes se ejecutan en cualquier número de instancias de rol, servidor o contenedor.

- Los componentes pueden ser claves de instrumentación de Application Insights independientes (incluso aunque las suscripciones sean diferentes) o diferentes roles que informan a una única clave de instrumentación de Application Insights. La experiencia de mapa de versión preliminar muestra los componentes con independencia de cómo están configurados.

Puede ver la topología de aplicación completa a lo largo de varios niveles de componentes de aplicación relacionados. Los componentes podrían ser diferentes recursos de Application Insights o distintos roles de un único recurso. Para encontrar componentes, el mapa de aplicación sigue las llamadas de dependencia HTTP entre los servidores con el SDK de Application Insights instalado.

Esta experiencia comienza con la detección progresiva de los componentes. La primera vez que carga el mapa de aplicación, se desencadena un conjunto de consultas para detectar los componentes relacionados con este componente. Un botón en la esquina superior izquierda se actualiza con el número de componentes de la aplicación a medida que se detectan.

Al hacer clic en "Update map components" (Actualizar componentes del mapa), el mapa se actualiza con todos los componentes detectados hasta ese momento. Según la complejidad de la aplicación, esta operación puede tardar un minuto en cargarse.

Si todos los componentes son roles dentro de un único recurso de Application Insights, este paso de detección no es necesario. La carga inicial para este tipo de aplicación tendrá todos sus componentes.

Uno de los objetivos principales de la experiencia es poder visualizar topologías complejas con cientos de componentes. Haga clic en cada componente para ver información detallada relacionada e ir a la experiencia de evaluación de prioridades de rendimiento y errores de ese componente.

El mapa de aplicación usa la propiedad nombre de rol en la nube para identificar los componentes en el mapa. Puede establecer o invalidar manualmente el nombre del rol en la nube y cambiar lo que se muestra en el Mapa de aplicación.