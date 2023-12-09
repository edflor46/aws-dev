# Certificacion AWS - Developer Associate

# Repaso Simuladores

### Parameters

Parameters le permiten introducir valores personalizados en su plantilla de CloudFormation cada vez que crea o actualiza un stack. La sección opcional Condiciones contiene declaraciones que definen las circunstancias en las que se crean o configuran las entidades. Por ejemplo, puede crear una condición y luego asociarla con un recurso o salida para que AWS CloudFormation solo cree el recurso o salida si la condición es verdadera.

Puede utilizar condiciones cuando desee reutilizar una plantilla que pueda crear recursos en diferentes contextos, como un entorno de test frente a un entorno de producción. En su plantilla, puede añadir un parámetro de entrada EnvironmentType, que acepta prod o test como entradas. Para el entorno de producción, puede incluir instancias de Amazon EC2 con determinadas capacidades; sin embargo, para el entorno de test, desea utilizar capacidades reducidas para ahorrar dinero.

Las condiciones no se pueden utilizar en la sección Parámetros. Después de definir todas sus condiciones, puede asociarlas con recursos y propiedades de recursos solo en las secciones Recursos y Salidas de una plantilla.

### SQS

El tamaño mínimo del mensaje es de 1 byte (1 carácter). El máximo es de 262.144 bytes (256 KB).

### Amazon Kinesis Data Streams

Amazon Kinesis Data Streams (KDS) es un servicio de streaming de datos en tiempo real masivamente escalable y duradero. KDS puede capturar de forma continua gigabytes de datos por segundo de cientos de miles de fuentes, como stream de clics de sitios web, stream de eventos de bases de datos, transacciones financieras, feeds de redes sociales, logs de IT y eventos de seguimiento de ubicación. Los datos recopilados están disponibles en milisegundos para permitir casos de uso de análisis en tiempo real como dashboards en tiempo real, detección de anomalías en tiempo real, precios dinámicos, etc.

Kinesis Data Streams permite el procesamiento en tiempo real de big data en streaming. Proporciona ordenación de registros, así como la capacidad de leer y/o reproducir registros en el mismo orden a múltiples aplicaciones de Amazon Kinesis. La biblioteca de clientes de Amazon Kinesis (KCL) entrega todos los registros de una clave de partición determinada al mismo procesador de registros, lo que facilita la creación de varias aplicaciones que lean el mismo stream de datos de Amazon Kinesis (por ejemplo, para realizar recuentos, agregaciones y filtrados).

Kinesis Data Streams es altamente personalizable y el más adecuado para los desarrolladores que crean aplicaciones personalizadas o streaming de datos para necesidades especializadas. Las secuencias de datos también ofrecen mayor flexibilidad que Firehose a la hora de integrar aplicaciones de flujo descendente.

### Utilizar credenciales Git generadas desde IAM

Los repositorios de CodeCommit están basados en Git y soportan las funcionalidades básicas de Git como las credenciales Git. AWS recomienda utilizar un usuario IAM al trabajar con CodeCommit. Puede acceder a CodeCommit con otros tipos de identidad, pero los demás tipos de identidad están sujetos a limitaciones.

### SSE-S3 - Server-Side Encryption

Al utilizar Server-Side Encryption with Amazon S3-Managed Keys (SSE-S3), cada objeto se cifra con una clave única que emplea un cifrado multifactor potente. Como salvaguarda adicional, cifra la propia clave con una clave maestra que rota periódicamente. El cifrado del lado del servidor de Amazon S3 utiliza uno de los cifrados por bloques más potentes disponibles, el Estándar de cifrado avanzado de 256 bits (AES-256), para cifrar sus datos.

### SSE-C

Dispone de las siguientes opciones para proteger los datos en reposo en Amazon S3:

- Cifrado del lado del servidor - Solicite a Amazon S3 que cifre su objeto antes de guardarlo en discos en sus centros de datos y, a continuación, descifrarlo cuando descargue los objetos.

- Cifrado del lado del cliente - Cifra los datos del lado del cliente y carga los datos cifrados en Amazon S3. En este caso, usted administra el proceso de cifrado, las claves de cifrado y las herramientas relacionadas.

- Para el caso de uso dado, la empresa desea administrar las claves de cifrado a través de su aplicación personalizada y dejar que S3 administre el cifrado, por lo que debe utilizar el cifrado del lado del servidor con claves proporcionadas por el cliente (SSE-C).

- El uso del cifrado del lado del servidor con claves de cifrado proporcionadas por el cliente (SSE-C) le permite establecer sus claves de cifrado. Con la clave de cifrado que proporcione como parte de su petición, Amazon S3 administra tanto el cifrado, cuando escribe en los discos, como el descifrado, cuando obtiene acceso a sus objetos.

### Habilitar el autoescalado de almacenamiento para RDS MySQL

Si su carga de trabajo es impredecible, puede habilitar el autoescalado de almacenamiento para una instancia de base de datos de Amazon RDS. Con el autoescalado de almacenamiento habilitado, cuando Amazon RDS detecta que se está quedando sin espacio libre en la base de datos, escala automáticamente el almacenamiento. Amazon RDS inicia una modificación de almacenamiento para una instancia de base de datos con autoescalado habilitado cuando se aplican estos factores:

- E-l espacio libre disponible es inferior al 10 por ciento del almacenamiento asignado.
- La condición de almacenamiento bajo dura al menos cinco minutos.
- Han transcurrido al menos seis horas desde la última modificación del almacenamiento.

### El parámetro de nombre de cluster no ha sido actualizado en el fichero

Inicialmente, lanza la plantilla con el valor de entrada 'MainCluster', que despliega cinco instancias en dos zonas de disponibilidad. La segunda vez, lanza la plantilla con un valor de entrada 'SecondCluster'. Sin embargo, las instancias creadas en la segunda ejecución también se lanzaron en "MainCluster" incluso después de especificar un nombre de Cluster diferente.

El parámetro de nombre de cluster no ha sido actualizado en el fichero /etc/ecs/ecs.config durante el bootstrap - En el fichero ecs.config hay que configurar el parámetro ECS_CLUSTER='your_cluster_name' para registrar la instancia de contenedor con un Cluster llamado 'your_cluster_name'.

### Firmantes que pueden crear URL firmadas para sus distribuciones de Amazon CloudFront

1. Cada firmante que utiliza para crear URL firmadas o cookies firmadas de CloudFront debe tener un par de claves pública y privada. El firmante utiliza su clave privada para firmar la URL o las cookies, y CloudFront utiliza la clave pública para verificar la firma.

1. Cuando utiliza el usuario root para administrar pares de claves de CloudFront, solo puede tener hasta dos pares de claves de CloudFront activos por cuenta de AWS.

### Orden correcto de los pasos a seguir para crear una aplicación utilizando AWS CDK

El flujo de trabajo de desarrollo estándar de AWS CDK es similar al flujo de trabajo que ya conoces como desarrollador. Hay algunos pasos adicionales:

1. Cree la aplicación a partir de una plantilla proporcionada por AWS CDK - Cada aplicación de AWS CDK debe estar en su propio directorio, con sus propias dependencias de módulos locales. Crea un nuevo directorio para tu aplicación. Ahora inicializa la app usando el comando cdk init, especificando la plantilla deseada ("app") y el lenguaje de programación. El comando cdk init crea una serie de archivos y carpetas dentro del directorio de inicio creado para ayudarte a organizar el código fuente de tu app AWS CDK.

1. Añade código a la app para crear recursos dentro de stacks - Añade código personalizado según sea necesario para tu aplicación.

1. En la mayoría de los entornos de programación, después de realizar cambios en el código, debe compilarlo. Esto no es estrictamente necesario con el CDK de AWS - el kit de herramientas lo hace por ti para que no te olvides. Pero aún puedes compilar manualmente cuando quieras para detectar errores de sintaxis y de tipo.

1. Sintetizar uno o más stacks en la aplicación para crear una plantilla de AWS CloudFormation - Sintetizar uno o más stacks en la aplicación para crear una plantilla de AWS CloudFormation. El paso de síntesis detecta errores lógicos en la definición de sus recursos de AWS. Si tu app contiene más de un stack, necesitarías especificar qué stack(s) sintetizar.

1. Es opcional (aunque una buena práctica) sintetizar antes de implementar. El CDK de AWS sintetiza su stack antes de cada despliegue. Si tu código tiene implicaciones de seguridad, verás un resumen de las mismas y deberás confirmarlas antes de proceder al despliegue. El comando cdk deploy se utiliza para implementar el stack utilizando plantillas de CloudFormation. Este comando muestra información sobre el progreso del despliegue de tu stack. Cuando termina, vuelve a aparecer el símbolo del sistema.

**En resumen:**

1. Cree la aplicación a partir de una plantilla proporcionada por AWS CDK
1. Añada código a la aplicación para crear recursos dentro de stacks
1. Cree la aplicación (opcional)
1. Sintetice uno o más stacks en la aplicación
1. Implemente stack(s) en su cuenta de AWS

### Clase de almacenamiento de Amazon Elastic File System (EFS) Standard-IA

La clase de almacenamiento Standard-IA reduce los costos de almacenamiento de los archivos a los que no se obtiene acceso todos los días. Lo hace sin sacrificar la alta disponibilidad, la alta durabilidad, la elasticidad y el acceso al sistema de archivos POSIX que proporciona Amazon EFS. AWS recomienda el almacenamiento Standard-IA si necesita que todo su conjunto de datos sea fácilmente accesible y desea ahorrar automáticamente en costos de almacenamiento para los archivos a los que se accede con menos frecuencia.

### NO es viable para el acceso entre cuentas de objetos de bucket de S3

Utilizar roles IAM y políticas basadas en recursos para delegar el acceso entre cuentas dentro de diferentes particiones mediante acceso programático únicamente

### Evitar que otros dominios no autorizados accedan a su API

Restringir el acceso mediante CORS

### Application Load Balancer pero no se ha registrado ningún objetivo con los grupos de objetivos

HTTP 503: Service unavailable

El Load Balancer genera el error HTTP 503: Service unavailable error when the target groups for the load balancer have no registered targets.

### Correcto en relación con la API CreateQueue SQS

**No es posible cambiar el tipo de cola después de crearla**- No se puede cambiar el tipo de cola después de crearla y no se puede convertir una cola estándar existente en una cola FIFO. Debe crear una nueva cola FIFO para su aplicación o eliminar la cola estándar existente y volver a crearla como cola FIFO.

**El valor del tiempo de espera de visibilidad de la cola está en segundos, y por defecto es de 30 segundos.**- El tiempo de espera de visibilidad de la cola se expresa en segundos. Los valores válidos son: Un número entero de 0 a 43.200 (12 horas), el valor por defecto es 30.

### AWS Serverless Application Repository (SAR)

El repositorio de aplicaciones sin servidor de AWS es un repositorio administrado para aplicaciones sin servidor. Permite a equipos, organizaciones y desarrolladores individuales almacenar y compartir aplicaciones reutilizables, así como ensamblar e implementar fácilmente arquitecturas sin servidor de maneras nuevas y potentes.

### Aumentar la memoria de la función

La memoria es la principal palanca de que disponen los desarrolladores de Lambda para controlar el rendimiento de una función. Se puede configurar la cantidad de memoria asignada a una función Lambda, entre 128 MB y 10.240 MB. La consola Lambda asigna por defecto a las nuevas funciones la configuración más pequeña y muchos desarrolladores también eligen 128 MB para sus funciones.

### API SQS

**DeleteQueue** - Elimina la cola especificada por QueueUrl, independientemente de su contenido. Al eliminar una cola, los mensajes que contenga dejarán de estar disponibles.

Cuando eliminas una cola, el proceso de eliminación tarda hasta 60 segundos. Es posible que las peticiones que envíes relacionadas con esa cola durante esos 60 segundos tengan éxito. Por ejemplo, una petición SendMessage puede tener éxito, pero después de 60 segundos la cola y el mensaje que envió ya no existen.

Cuando eliminas una cola, debes esperar al menos 60 segundos antes de crear una cola con el mismo nombre.

**PurgeQueue** - Elimina los mensajes de una cola especificada por el parámetro QueueURL. Cuando se utiliza la acción PurgeQueue, no se pueden recuperar los mensajes eliminados de una cola. Sin embargo, la cola permanece.

**RemovePermission** - Revoca cualquier permiso de la política de colas que coincida con el parámetro Etiqueta especificado.

### Especificar una clave KMS para utilizar

AWS Key Management Service (KMS) le facilita la creación y administración de claves criptográficas y el control de su uso en una amplia gama de servicios de AWS y en sus aplicaciones.

Para que AWS CodeBuild cifre sus artefactos de salida de compilación, necesita acceso a una clave maestra de cliente (CMK) de AWS KMS. De forma predeterminada, AWS CodeBuild utiliza la CMK administrada por AWS para Amazon S3 en su cuenta de AWS. La siguiente variable de entorno proporciona estos detalles:

CODEBUILD_KMS_KEY_ID: El identificador de la clave AWS KMS que CodeBuild está utilizando para cifrar el artefacto de salida de la compilación (por ejemplo, arn:aws:kms:region-ID:account-ID:key/key-ID o alias/key-alias).

### Habilitar cifrado SQS KMS

El cifrado del lado del servidor (SSE) le permite transmitir datos confidenciales en colas cifradas. SSE protege el contenido de los mensajes en las colas mediante claves administradas en AWS Key Management Service (AWS KMS).

### DeleteOnTermination para cada volumen EBS

Cuando una instancia termina, el valor del atributo DeleteOnTermination para cada volumen EBS adjunto determina si se conserva o se elimina el volumen. Por defecto, el atributo DeleteOnTermination se establece en True para el volumen root y en False para todos los demás tipos de volumen.

Establezca el atributo DeleteOnTermination en False mediante la línea de comandos - Si la instancia ya se está ejecutando, puede establecer DeleteOnTermination en False mediante la línea de comandos.

### Crear un rol IAM para EC2

Los roles IAM se han incorporado para que sus aplicaciones puedan realizar peticiones API de forma segura desde sus instancias, sin necesidad de que usted gestione las credenciales de seguridad que utilizan las aplicaciones. En lugar de crear y distribuir sus credenciales de AWS, puede delegar el permiso para realizar peticiones API utilizando roles IAM.

### Enrutamiento desigual

- Sticky sessions están habilitadas para el load balancer - Esta puede ser la razón de un posible enrutamiento desigual del tráfico por parte del load balancer. Las Sticky Sessions son un mecanismo para enrutar peticiones al mismo objetivo en un grupo de objetivos. Esto es útil para servidores que mantienen información de estado para proporcionar una experiencia continua a los clientes. Para utilizar las Sticky Sessions, los clientes deben soportar Cookies.

- Las instancias de un tipo de capacidad específico no se distribuyen por igual entre las zonas de disponibilidad

### ECS problema de sincronización

Terminó la instancia de contenedor mientras estaba en estado STOPPED, lo que provocó este problema de sincronización - Si termina una instancia de contenedor mientras está en estado STOPPED, esa instancia de contenedor no se elimina automáticamente del Cluster. Tendrá que dar de baja su instancia de contenedor en estado STOPPED utilizando la consola de Amazon ECS o la interfaz de línea de comandos de AWS. Una vez dada de baja, la instancia de contenedor ya no aparecerá como recurso en su Cluster de Amazon ECS.

### Drift Detection de CloudFormation

La detección de desviaciones le permite detectar si la configuración real de un stack difiere, o se ha desviado, de su configuración esperada. Utilice CloudFormation para detectar desviaciones en un stack completo o en recursos individuales dentro del stack. Se considera que un recurso se ha desviado si alguno de sus valores de propiedad reales difiere de los valores de propiedad esperados. Esto incluye si la propiedad o el recurso se han eliminado. Se considera que un stack se ha desviado si uno o más de sus recursos se han desviado.

### Elastic Beanstalk instancias fallidas después de la terminación

Elastic Beanstalk las sustituirá por instancias que ejecuten la versión de la aplicación del despliegue satisfactorio más reciente.

Al procesar un lote, Elastic Beanstalk desconecta todas las instancias del lote del balanceador de carga, despliega la nueva versión de la aplicación y, a continuación, vuelve a conectar las instancias. Si habilita el drenaje de conexiones, Elastic Beanstalk drena las conexiones existentes de las instancias de Amazon EC2 de cada lote antes de comenzar el despliegue.

Si un despliegue falla después de que uno o varios lotes se hayan completado correctamente, los lotes completados ejecutan la nueva versión de su aplicación, mientras que los lotes pendientes siguen ejecutando la versión antigua. Puede identificar la versión que se ejecuta en las instancias de su entorno en la página de estado de la consola. Esta página muestra el ID del despliegue más reciente que se ejecutó en cada instancia de su entorno. Si finaliza las instancias del despliegue fallido, Elastic Beanstalk las sustituye por instancias que ejecutan la versión de la aplicación del despliegue correcto más reciente.

### Elastic Beanstalk Implantacion con actualizaciones inmutables o en modo de división del tráfico

Las implantaciones inmutables realizan una actualización inmutable para lanzar un conjunto completo de nuevas instancias que ejecutan la nueva versión de la aplicación en un grupo de Auto Scaling separado, junto con las instancias que ejecutan la versión antigua. Los despliegues inmutables pueden evitar problemas causados por despliegues Rolling parcialmente completados.

Los despliegues con división del tráfico permiten testear las instancias canarias como parte del despliegue de la aplicación. En un despliegue de división del tráfico, Elastic Beanstalk lanza un conjunto completo de instancias nuevas, al igual que durante un despliegue inmutable. A continuación, reenvía un porcentaje especificado del tráfico entrante de clientes a la nueva versión de la aplicación durante un período de evaluación determinado.

Algunas políticas sustituyen todas las instancias durante el despliegue o la actualización. Esto hace que se pierdan todos los saldos de ráfagas de Amazon EC2 acumulados. Ocurre en los siguientes casos:

Actualizaciones de plataformas administradas con el reemplazo de instancias habilitado
Actualizaciones inmutables
Despliegues con actualizaciones inmutables o división de tráfico activada


### Step Functions

AWS Step Functions es un orquestador de funciones sin servidor que facilita la secuenciación de funciones de AWS Lambda y varios servicios de AWS en aplicaciones críticas para el negocio. A través de su interfaz visual, puede crear y ejecutar una serie de flujos de trabajo checkpointed y basados en eventos que mantienen el estado de la aplicación. La salida de un paso actúa como entrada para el siguiente. Cada paso de su aplicación se ejecuta en orden, según lo defina su lógica empresarial.

AWS Step Functions le permite implementar un proceso empresarial como una serie de pasos que conforman un flujo de trabajo. Los pasos individuales del flujo de trabajo pueden invocar una función de Lambda o un contenedor que tenga cierta lógica empresarial, actualizar una base de datos como DynamoDB o publicar un mensaje en una cola una vez que ese paso o todo el flujo de trabajo complete la ejecución.

### Almacenar string secreto como SecureString en SSM Parameter Store

Con AWS Systems Manager Parameter Store, puede crear parámetros SecureString, que son parámetros que tienen un nombre de parámetro de texto sin formato y un valor de parámetro cifrado. Parameter Store utiliza AWS KMS para cifrar y descifrar los valores de parámetro de los parámetros Secure String. Además, si utiliza CMK administradas por el cliente, puede utilizar políticas de IAM y políticas de claves para administrar el cifrado y descifrado de permisos. Para recuperar el valor descifrado solo tiene que realizar una llamada a la API.

### Auditar usando CloudTrail

AWS CloudTrail es un servicio que permite la gobernanza, la normativa, la auditoría operativa y la auditoría de riesgos de su cuenta de AWS. Con CloudTrail, puede logs, monitorizar continuamente y retener la actividad de la cuenta relacionada con acciones a través de su infraestructura de AWS. CloudTrail proporciona un historial de eventos de la actividad de su cuenta de AWS, incluidas las acciones realizadas a través de la consola de administración de AWS, los SDK de AWS, las herramientas de línea de comandos y otros servicios de AWS.

CloudTrail le permitirá ver todas las llamadas API realizadas a SSM y KMS.

### API  Gateway - Actualizar el valor de la Variable de etapa

Actualizar el valor de la Variable de etapa del nombre de etapa de test al de prod.

Después de crear su API, debe desplegarla para que sus usuarios puedan llamarla. Para desplegar una API, debe crear un despliegue de API y asociarlo a una etapa. Una etapa es una referencia lógica a un estado del ciclo de vida de su API (por ejemplo, dev, prod, beta, v2). Las etapas de la API se identifican mediante el ID de la API y el nombre de la etapa. Se incluyen en la URL que se utiliza para invocar la API. Cada etapa es una referencia con nombre a una implementación de la API y está disponible para que las aplicaciones cliente la llamen.

Las etapas permiten un sólido control de versiones de la API. En nuestro caso de uso actual, después de que las actualizaciones pasen la prueba, puedes promover la etapa de test a la etapa de producción. La promoción puede realizarse volviendo a desplegar la API en la etapa prod o actualizando un valor de Variable de etapa del nombre de etapa de test al de prod.

### Despliegue in situ

Se detiene la aplicación en cada instancia del grupo de despliegue, se instala la última revisión de la aplicación y se inicia y valida la nueva versión de la aplicación. Puede utilizar un balanceador de carga para que cada instancia se desregistre durante su despliegue y se restablezca el servicio una vez finalizado el despliegue.

### Regla de salida a la ACL de red (NACL) para permitir el envío de la respuesta al cliente

Hay que añadir una regla de salida a la ACL de red (NACL) para permitir el envío de la respuesta al cliente en el intervalo de puertos efímero.

Los grupos de seguridad son con estado, por lo que permitir el tráfico entrante a los puertos necesarios habilita la conexión. Las ACL de red no tienen estado, por lo que debe permitir tanto el tráfico entrante como el saliente. Por defecto, cada ACL de red personalizada deniega todo el tráfico entrante y saliente hasta que se añaden reglas.

Para habilitar la conexión a un servicio que se ejecuta en una instancia, la ACL de red asociada debe permitir ambos: 1. 1. Tráfico entrante en el puerto en el que escucha el servicio 2. 3. Tráfico saliente a puertos efímeros

Cuando un cliente se conecta a un servidor, un puerto aleatorio del rango de puertos efímeros (1024-65535) se convierte en el puerto de origen del cliente.

El puerto efímero designado se convierte en el puerto de destino para el tráfico de retorno del servicio. El tráfico saliente al puerto efímero debe estar permitido en la ACL de red.

### Modelo de aplicación sin servidor de AWS (AWS SAM)

Utiliza la especificación de AWS SAM para definir su aplicación sin servidor. Las plantillas de AWS SAM son una extensión de las plantillas de AWS CloudFormation, con algunos componentes adicionales que facilitan el trabajo con ellas. AWS SAM necesita las plantillas de CloudFormation como base para su configuración.

### Afirmaciones sobre la configuración de datos de usuario de EC2

- Por defecto, los scripts introducidos como datos de usuario se ejecutan con privilegios de usuario root.
- Por defecto, los datos de usuario sólo se ejecutan durante el ciclo de arranque cuando se lanza una instancia por primera vez.

### Volumenes EBS

Amazon EBS funciona con AWS KMS para cifrar y descifrar su volumen de EBS. Puede cifrar tanto el volumen de arranque como el de datos de una instancia EC2. Cuando crea un volumen EBS cifrado y lo adjunta a un tipo de instancia soportado, se cifran los siguientes tipos de datos:

1. Datos en reposo dentro del volumen
1. Todos los datos que se mueven entre el volumen y la instancia
1. Todos los Snapshots creados a partir del volumen
1. Todos los volúmenes creados a partir de esas Snapshots

**Los volúmenes EBS soportan tanto el cifrado en vuelo como el cifrado en reposo mediante KMS**
Las operaciones de cifrado se producen en los servidores que alojan instancias EC2, lo que garantiza la seguridad tanto de los datos en reposo como de los datos en tránsito entre una instancia y su almacenamiento EBS conectado.

### AWS Lambda - Conectar Lambda a instancia RDS(VPC, subred privada)

Configurar Lambda para conectarse a la VPC con la subred privada y el grupo de seguridad necesarios para acceder a RDS - Puede configurar una función de Lambda para conectarse a subredes privadas en una nube privada virtual (VPC) de su cuenta. Utilice Amazon Virtual Private Cloud (Amazon VPC) para crear una red privada para recursos como bases de datos, instancias de caché o servicios internos. Conecte su función Lambda a la VPC para obtener acceso a recursos privados durante la ejecución. Cuando conecta una función a una VPC, Lambda crea una interfaz de red elástica para cada combinación de grupo de seguridad y subred en la configuración de VPC de su función. Esta es la forma correcta de dar acceso RDS a Lambda.

### HTTPS en AWS CloudFront

**Entre los clientes y CloudFront, así como entre CloudFront y el backend.**

Para las distribuciones web, puede configurar CloudFront para que requiera que los espectadores utilicen HTTPS para solicitar sus objetos, de modo que las conexiones se cifren cuando CloudFront se comunique con los espectadores.

También puede configurar CloudFront para que utilice HTTPS para obtener objetos de su origen, de modo que las conexiones se cifren cuando CloudFront se comunique con su origen.

### Metricas de políticas de escalado de seguimiento de objetivos

**ASGAverageCPUUtilization**: Es una métrica predefinida para la política de escalado de seguimiento de objetivos. Representa la utilización media de CPU del grupo de Auto Scaling.

**ASGAverageNetworkOut**: métrica predefinida para la política de escalado de seguimiento de objetivos. Representa el número medio de bytes enviados a todas las interfaces de red por el grupo de Auto Scaling.

**ALBRequestCountPerTarget**: métrica predefinida para la política de escalado de seguimiento de objetivos. Representa el número de peticiones completadas por objetivo en un grupo de objetivos de Application Load Balancer.

### Condiciones de host

Puede utilizar condiciones de host para definir reglas que enruten peticiones basadas en el nombre de host en la cabecera de host (también conocido como enrutamiento basado en host). Esto le permite soportar múltiples subdominios y diferentes dominios de nivel superior utilizando un único Load Balancer.

Un nombre de host no distingue entre mayúsculas y minúsculas, puede tener una longitud máxima de 128 caracteres y puede contener cualquiera de los siguientes caracteres: 1. A-Z, a-z, 0-9 2. - . 3. * (coincide con 0 o más caracteres) 4. ? (coincide exactamente con 1 carácter)

Debe incluir al menos un carácter ".". Sólo puede incluir caracteres alfabéticos después del carácter "." final.

