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

### Plantilla de AWS CloudFormation

La plantilla de AWS CloudFormation es un archivo de texto con formato JSON o YAML que describe su infraestructura de AWS. Las plantillas incluyen varias secciones principales. La sección "Recursos" es la única obligatoria. La sección opcional "Transform" especifica una o más macros que AWS CloudFormation utiliza para procesar su plantilla.

### AWS Serverless Application Model (SAM)

AWS Serverless Application Model (SAM) es un framework de código abierto para crear aplicaciones sin servidor. Proporciona una sintaxis abreviada para expresar funciones, API, bases de datos y mapeos de origen de eventos. Con sólo unas pocas líneas por recurso, puede definir la aplicación que desee y modelarla utilizando YAML.

La transformación de AWS::Serverless, que es una macro alojada en AWS CloudFormation, toma una plantilla completa escrita en la sintaxis del modelo de aplicación sin servidor de AWS (AWS SAM) y la transforma y expande en una plantilla compatible con AWS CloudFormation. Por lo tanto, la presencia de la sección "Transform" indica que el documento es una plantilla SAM.

### Modelo de aplicación sin servidor de AWS (AWS SAM)

Utiliza la especificación de AWS SAM para definir su aplicación sin servidor. Las plantillas de AWS SAM son una extensión de las plantillas de AWS CloudFormation, con algunos componentes adicionales que facilitan el trabajo con ellas. AWS SAM necesita las plantillas de CloudFormation como base para su configuración.

### SAM soporta los siguientes tipos de recursos

AWS::Serverless::Api

AWS::Serverless::Application

AWS::Serverless::Function

AWS::Serverless::HttpApi

AWS::Serverless::LayerVersion

AWS::Serverless::SimpleTable

AWS::Serverless::StateMachine

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

### IAM Access Analyzer

AWS IAM Access Analyzer le ayuda a identificar los recursos de su organización y cuentas, como buckets de Amazon S3 o roles de IAM, que se comparten con una entidad externa. Esto le permite identificar el acceso no intencionado a sus recursos y datos, lo que supone un riesgo para la seguridad.

Puede establecer el ámbito del analizador en una organización o una cuenta de AWS. Esta es su Zona de Confianza. El analizador examina todos los recursos compatibles dentro de su Zona de confianza. Cuando Access Analyzer encuentra una directiva que permite el acceso a un recurso desde fuera de su zona de confianza, genera un hallazgo activo.

### Política de confianza

Las políticas de confianza definen qué entidades principales (cuentas, usuarios, roles y usuarios federados) pueden asumir el rol. Un rol IAM es tanto una identidad como un recurso que soporta políticas basadas en recursos. Por este motivo, debe adjuntar tanto una política de confianza como una política basada en identidades a un rol de IAM. El servicio IAM sólo soporta un tipo de política basada en recursos denominada política de confianza de rol, que se adjunta a un rol IAM.

### Autorizador Lambda

Un autorizador de Lambda de Amazon API Gateway (anteriormente conocido como autorizador personalizado) es una función de Lambda que proporciona para controlar el acceso a su API. Un autorizador de Lambda utiliza estrategias de autenticación de token de portador, como OAuth o SAML. Antes de crear un autorizador de Lambda de API Gateway, primero debe crear la función de AWS Lambda que implementa la lógica para autorizar y, si es necesario, autenticar a la persona que llama.

### Variables de la política IAM

En lugar de crear políticas individuales para cada usuario, puede utilizar variables de política y crear una única política que se aplique a varios usuarios (una política de grupo). Las variables de política actúan como marcadores de posición. Cuando realiza una petición a AWS, el marcador de posición se sustituye por un valor de la petición cuando se evalúa la política.

A modo de ejemplo, la siguiente política otorga a cada uno de los usuarios del grupo acceso programático completo a un objeto específico del usuario (su propio "directorio personal") en Amazon S3.

### Cognito User Pools

Tras una autenticación correcta, Amazon Cognito devuelve tokens de grupos de usuarios a su aplicación. Puede utilizar los tokens para conceder a sus usuarios acceso a sus propios recursos del lado del servidor o a Amazon API Gateway.

Los grupos de usuarios de Amazon Cognito implementan tokens de ID, acceso y actualización según lo definido por el estándar abierto OpenID Connect (OIDC).

El token de ID es un token web JSON (JWT) que contiene información sobre la identidad del usuario autenticado, como el nombre, el email y el número de teléfono. Puede utilizar esta información de identidad dentro de su aplicación. El token de identificación también se puede utilizar para autenticar usuarios contra sus servidores de recursos o aplicaciones de servidor.

### Muestra de X-Ray

Al personalizar las reglas de muestreo, puede controlar la cantidad de datos que se registran y modificar el comportamiento de muestreo sobre la marcha sin modificar ni volver a desplegar el código. Las reglas de muestreo indican al SDK de X-Ray cuántas peticiones debe registrar para un conjunto de criterios. X-Ray SDK aplica un algoritmo de muestreo para determinar qué peticiones se rastrean. Sin embargo, el hecho de que nuestra aplicación no envíe datos a X-Ray no ayuda a determinar la causa del fallo.

### Amazon RDS

Amazon RDS utiliza la funcionalidad de replicación integrada del motor de base de datos PostgreSQL para crear un tipo especial de instancia de base de datos denominada réplica de lectura a partir de una instancia de base de datos de origen. La instancia de base de datos de origen se convierte en la instancia de base de datos principal. Las actualizaciones realizadas en la instancia de base de datos primaria se copian de forma asíncrona en la réplica de lectura. Puede reducir la carga de su instancia de base de datos primaria dirigiendo las consultas de lectura de sus aplicaciones a la réplica de lectura. Utilizando réplicas de lectura, puede escalar elásticamente más allá de las limitaciones de capacidad de una única instancia de base de datos para cargas de trabajo de base de datos de lectura intensiva. Para el caso de uso dado, puede conseguir un rendimiento de lectura óptimo para consultas SQL utilizando el endpoint de réplica de lectura para la carga de trabajo de lectura intensiva.

### Planes de uso de API Gateway

Amazon API Gateway es un servicio de AWS para crear, publicar, mantener, monitorizar y proteger API REST, HTTP y WebSocket a cualquier escala. Los desarrolladores de API pueden crear API que accedan a AWS o a otros servicios web, así como a los datos almacenados en el Cloud de AWS.

Un plan de uso especifica quién puede acceder a una o más etapas y métodos de API implementados, y también cuánto y con qué rapidez pueden acceder a ellos. El plan utiliza claves de API para identificar a los clientes de API y mide el acceso a las etapas de API asociadas para cada clave.

Puede configurar planes de uso y claves de API para permitir que los clientes accedan a las API seleccionadas según las cuotas y tasas de petición acordadas que se ajusten a sus requisitos empresariales y a sus limitaciones presupuestarias.

### Politica de escalado de seguimiento

Si utiliza una política de escalado de seguimiento de objetivos basada en una métrica de cola de Amazon SQS personalizada, el escalado dinámico puede ajustarse a la curva de demanda de su aplicación de forma más eficaz.

El problema de utilizar una métrica de Amazon SQS de CloudWatch como ApproximateNumberOfMessagesVisible para el seguimiento de objetivos es que el número de mensajes en la cola puede no cambiar proporcionalmente al tamaño del Auto Scaling Group que procesa los mensajes de la cola. Esto se debe a que el número de mensajes en la cola de SQS no define únicamente el número de instancias necesarias. El número de instancias de su grupo de Auto Scaling puede depender de varios factores, incluido el tiempo que se tarda en procesar un mensaje y la cantidad aceptable de latencia (retardo de la cola).

La solución es utilizar una métrica de retraso por instancia cuyo valor objetivo sea el retraso por instancia aceptable para mantener. Puede calcular estas cifras de la siguiente manera:

Backlog por instancia: Para calcular el retraso por instancia, comience con el atributo de cola ApproximateNumberOfMessages para determinar la longitud de la cola SQS (número de mensajes disponibles para recuperar de la cola). Divida ese número por la capacidad de ejecución de la flota, que para un grupo Auto Scaling es el número de instancias en estado InService, para obtener el backlog por instancia.

Retraso aceptable por instancia: Para calcular su valor objetivo, determine primero lo que su aplicación puede aceptar en términos de latencia. A continuación, tome el valor de latencia aceptable y divídalo por el tiempo medio que tarda una instancia EC2 en procesar un mensaje.

Para ilustrarlo con un ejemplo, digamos que el ApproximateNumberOfMessages actual es 1500 y la capacidad de ejecución de la flota es 10. Si el tiempo medio de procesamiento es de 0,1 segundos para cada mensaje y la latencia más larga aceptable es de 10 segundos, el retraso aceptable por instancia es de 10 / 0,1, lo que equivale a 100. Esto significa que 100 es el valor objetivo. Esto significa que 100 es el valor objetivo para su política de seguimiento de objetivos. Si el backlog por instancia es actualmente de 150 (1500 / 10), su flota se escala, y se escala en cinco instancias para mantener la proporción con el valor objetivo.

En resumen: ***Utilizar métrica de backlog por instancia con política de escalado de seguimiento de objetivos***

### ElastiCache definido en .ebextensions/

Cualquier recurso creado como parte de su .ebextensions es parte de su plantilla de Elastic Beanstalk y será eliminado si el entorno es terminado.

### Base de datos RDS definida externamente

Para desacoplar la instancia de base de datos del entorno, puede ejecutar una instancia de base de datos en Amazon RDS y configurar la aplicación para que se conecte a ella en el lanzamiento. Esto le permite conectar varios entornos a una base de datos, finalizar un entorno sin afectar a la base de datos y realizar actualizaciones sin interrupciones con despliegues Blue/Green. Para permitir que las instancias de Amazon EC2 de su entorno se conecten a una base de datos externa, puede configurar el grupo Auto Scaling Group del entorno con un grupo de seguridad adicional.

### Rolling

La política de despliegue Rolling despliega la nueva versión por lotes. Cada lote se pone fuera de servicio durante la fase de despliegue, reduciendo la capacidad de su entorno por el número de instancias en un lote. El coste sigue siendo el mismo, ya que el número de instancias EC2 no aumenta. Esta política evita el tiempo de inactividad y minimiza la reducción de la disponibilidad, a costa de un mayor tiempo de despliegue.

### Inmutable

La política de despliegue 'Inmutable' garantiza que la nueva versión de la aplicación se despliegue siempre en las nuevas instancias, en lugar de actualizar las instancias existentes. También tiene la ventaja adicional de una reversión rápida y segura en caso de que falle el despliegue.

### Todo a la vez

Esta política despliega la nueva versión en todas las instancias simultáneamente. Aunque "Todo a la vez" es el método de despliegue más rápido, la aplicación puede dejar de estar disponible para los usuarios (o tener una baja disponibilidad) durante un breve periodo de tiempo.

### Tipos de credenciales NO es soportado por IAM para CodeCommit

**Nombre de usuario y contraseña de IAM** - Las credenciales de nombre de usuario y contraseña de IAM no se pueden utilizar para acceder a CodeCommit.

### Utilizar el parámetro

Utilizar el parámetro ***--region***: Si no se establece el parámetro de región, el comando CLI se ejecuta contra la región predeterminada de AWS.

### Invocar la función !FindInMap

!FindInMap [ MapName, TopLevelKey, SecondLevelKey ] - La función intrínseca Fn::FindInMap devuelve el valor correspondiente a las claves de un mapa de dos niveles declarado en la sección Mappings. Sintaxis YAML para el nombre completo de la función: Fn::FindInMap: [ MapName, TopLevelKey, SecondLevelKey ]

La forma abreviada de la sintaxis anterior es : !FindInMap [ MapName, TopLevelKey, SecondLevelKey ]

Donde,

MapName - Es el nombre lógico de un mapeo declarado en la sección Mappings que contiene las claves y los valores. TopLevelKey - Es el nombre de la clave de nivel superior. Su valor es una lista de pares clave-valor. SecondLevelKey - El nombre de la clave de segundo nivel, que se establece en una de las claves de la lista asignada a TopLevelKey.

Considere la siguiente plantilla YAML:

<pre><code>
Mappings:
    RegionMap:
        us-east-1:
        HVM64: "ami-0ff8a91507f77f867"
        HVMG2: "ami-0a584ac55a7631c0c"
        us-west-1:
        HVM64: "ami-0bdb828fd58c52235"
        HVMG2: "ami-066ee5fd4a9ef77f1"
        eu-west-1:
        HVM64: "ami-047bb4163c506cd98"
        HVMG2: "ami-31c2f645"
        ap-southeast-1:
        HVM64: "ami-08569b978cc4dfa10"
        HVMG2: "ami-0be9df32ae9f92309"
        ap-northeast-1:
        HVM64: "ami-06cd52961ce9f0d85"
        HVMG2: "ami-053cdd503598e4a9d"
Resources:
    myEC2Instance:
        Type: "AWS::EC2::Instance"
        Properties:
        ImageId: !FindInMap
            - RegionMap
            - !Ref 'AWS::Region'
            - HVM64
        InstanceType: m1.small
</code></pre>

La plantilla de ejemplo contiene un recurso AWS::EC2::Instance cuya propiedad ImageId es establecida por la función FindInMap.

MapName se establece en el mapa de interés, "RegionMap" en este ejemplo. TopLevelKey se establece en la región donde se crea el stack, que se determina utilizando el pseudoparámetro "AWS::Region". SecondLevelKey se establece en la arquitectura deseada, "HVM64" en este ejemplo.

FindInMap devuelve la AMI asignada a FindInMap. Para una instancia HVM64 en us-east-1, FindInMap devolvería "ami-0ff8a91507f77f867".

### Instancias dedicadas

Las instancias dedicadas son instancias de Amazon EC2 que se ejecutan en una nube privada virtual (VPC) en hardware dedicado a un único cliente. Las Instancias Dedicadas que pertenecen a diferentes cuentas de AWS están físicamente aisladas a nivel de hardware, incluso si dichas cuentas están vinculadas a una cuenta de un único cliente. Sin embargo, las Instancias Dedicadas pueden compartir hardware con otras instancias de la misma cuenta de AWS que no sean Instancias Dedicadas.

Un Host Dedicado también es un servidor físico dedicado para su uso. Con un Hosts dedicado, tiene visibilidad y control sobre cómo se colocan las instancias en el servidor.

### ALB access logs

Elastic Load Balancing proporciona logs de acceso que capturan información detallada sobre las peticiones enviadas a su Load Balancer. Cada logs contiene información como la hora a la que se recibió la petición, la dirección IP del cliente, las latencias, las rutas de petición y las respuestas del servidor. Puede utilizar estos logs de acceso para analizar patrones de tráfico y solucionar problemas. Los logs de acceso son una función opcional de Elastic Load Balancing que está desactivada de forma predeterminada.

### X-Ray

AWS X-Ray ayuda a los desarrolladores a analizar y depurar aplicaciones distribuidas de producción, como las creadas con una arquitectura de microservicios. Con X-Ray, puede comprender el desempeño de su aplicación y sus servicios subyacentes para identificar y solucionar la causa raíz de los problemas y errores de desempeño. X-Ray proporciona una vista de extremo a extremo de las peticiones a medida que viajan a través de su aplicación, y muestra un mapeo de los componentes subyacentes de su aplicación.

Puede utilizar X-Ray para recopilar datos en todas las cuentas de AWS. El agente de X-Ray puede asumir un rol para publicar datos en una cuenta diferente de aquella en la que se está ejecutando. Esto le permite publicar datos de varios componentes de su aplicación en una cuenta central.

### AWS::AccountId

Con CloudFormation, puede crear una plantilla que describa todos los recursos de AWS que desee (como instancias de Amazon EC2 o instancias de base de datos de Amazon RDS), y AWS CloudFormation se encargará de aprovisionar y configurar dichos recursos por usted.

Los pseudoparámetros son parámetros predefinidos por AWS CloudFormation. Usted no los declara en su plantilla. Utilícelos de la misma forma que lo haría con un parámetro, como argumento de la función Ref.

AWS::AccountId devuelve el ID de cuenta de AWS de la cuenta en la que se está creando el stack.

### AWS::NoValue

Elimina la propiedad de recurso correspondiente cuando se especifica como valor de retorno en la función intrínseca Fn::If.

### AWS::Region

Devuelve un string que representa la región de AWS en la que se está creando el recurso que lo engloba, como us-west-2.

### AWS::StackName

Devuelve el nombre del stack especificado con el comando aws cloudformation create-stack, como "teststack".

### AWS CloudFormation StackSets

AWS CloudFormation StackSets amplía la capacidad de los stacks al permitirle crear, actualizar o eliminar stacks en varias cuentas y regiones de AWS con una sola operación. Utilizando una cuenta de administrador, puede definir y administrar una plantilla de AWS CloudFormation y utilizar la plantilla como base para aprovisionar stacks en cuentas de destino seleccionadas en regiones de AWS especificadas.

Ejemplo: ***Configure una plantilla de AWS CloudFormation que defina los recursos de la prueba de carga. Aproveche el comando de la CLI de AWS create-stack-set para crear un conjunto de stacks en las regiones deseadas.***

### Elastic Load Balancing soporta tres tipos de balanceadores de carga:

Application Load Balancer

Network Load Balancer

Balanceadores de carga clásicos

**Separe el tráfico público del privado** - Los nodos de un balanceador de carga orientado a Internet tienen direcciones IP públicas. Los Load Balancer dirigen las peticiones a sus destinos utilizando direcciones IP privadas. Por lo tanto, sus destinos no necesitan direcciones IP públicas para recibir peticiones de usuarios a través de Internet.

**Construya un sistema de alta disponibilidad** - Elastic Load Balancing proporciona tolerancia a fallos para sus aplicaciones equilibrando automáticamente el tráfico entre los destinos -instancias de Amazon EC2, contenedores, direcciones IP y funciones de Lambda- en varias zonas de disponibilidad, al tiempo que garantiza que solo los destinos en buen estado reciben tráfico.

### Desplegar la función con su asignación de memoria configurada al máximo

Lambda asigna potencia de CPU en proporción a la cantidad de memoria configurada. La memoria es la cantidad de memoria disponible para su función Lambda en tiempo de ejecución. Puede aumentar o disminuir la memoria y la potencia de CPU asignada a su función utilizando la configuración de Memoria (MB). Para configurar la memoria de su función, establezca un valor entre 128 MB y 10.240 MB en incrementos de 1 MB. A 1.769 MB, una función tiene el equivalente de una vCPU (una vCPU-segundo de créditos por segundo).

### Los valores de salida exportados en CloudFormation deben tener nombres únicos dentro de una misma región

Con CloudFormation, puede crear una plantilla que describa todos los recursos de AWS que desee (como instancias de Amazon EC2 o instancias de base de datos de Amazon RDS), y AWS CloudFormation se encarga de aprovisionar y configurar dichos recursos por usted.

Una plantilla de CloudFormation tiene una sección opcional Outputs que declara valores de salida que puede importar a otros stacks (para crear referencias entre stacks), devolver en respuesta (para describir llamadas a stacks) o ver en la consola de AWS CloudFormation. Por ejemplo, puede mostrar el nombre del bucket de S3 de un stack para que sea más fácil encontrarlo.

Puede utilizar Exportar valores de salida para exportar el nombre de la salida de recursos para una referencia entre stacks. Para cada cuenta de AWS, los nombres de exportación deben ser únicos dentro de una región. En este caso, tendríamos un conflicto dentro de us-east-2.

### Etapas

Una etapa es una referencia lógica a un estado del ciclo de vida de su API (por ejemplo, "dev", "prod", "beta", "v2"). Las etapas de la API se identifican mediante el ID de la API y el nombre de la etapa. Puede utilizar una etapa para gestionar y optimizar un despliegue concreto. Por ejemplo, puede configurar ajustes de etapa para habilitar el almacenamiento en caché, personalizar la limitación de peticiones, configurar logs, definir variables de etapa o adjuntar una versión canaria para testear. Tras la implantación inicial, puede añadir más etapas y asociarlas a implantaciones existentes. Puede utilizar la consola de API Gateway para crear una nueva etapa, o puede elegir una etapa existente mientras despliega una API. En general, puede añadir una nueva etapa a un despliegue de API antes de volver a desplegar la API.

### .ebextensions/<mysettings>.config

Puede añadir archivos de configuración de AWS Elastic Beanstalk (.ebextensions) al código fuente de su aplicación web para configurar su entorno y personalizar los recursos de AWS que contiene. Los archivos de configuración son documentos con formato YAML o JSON con una extensión de archivo .config que se colocan en una carpeta denominada .ebextensions y se implementan en el paquete de código fuente de la aplicación.

### KMS almacena la CMK, y recibe datos de los clientes, que cifra y devuelve

Una clave maestra de cliente (CMK) es una representación lógica de una clave maestra. La CMK incluye metadatos, como el ID de la clave, la fecha de creación, la descripción y el estado de la clave. La CMK también contiene el material de la clave utilizado para cifrar y descifrar datos. Puede generar CMK en KMS, en un Cluster de AWS CloudHSM o importarlas desde su infraestructura de administración de claves.

AWS KMS soporta CMK simétricas y asimétricas. Una CMK simétrica representa una clave de 256 bits que se utiliza para el cifrado y el descifrado. Una CMK asimétrica representa un par de claves RSA que se utiliza para cifrado y descifrado o firma y verificación (pero no ambos), o un par de claves de curva elíptica (ECC) que se utiliza para firma y verificación.

AWS KMS soporta tres tipos de CMK: CMK administradas por el cliente, CMK administradas por AWS y CMK propiedad de AWS.

### Utilice AWS CloudTrail para obtener un registro de las acciones realizadas por un usuario

AWS CloudTrail proporciona un registro de las acciones realizadas por un usuario, rol o servicio de AWS en Systems Manager. Mediante la información recopilada por AWS CloudTrail, puede determinar la petición que se realizó a Systems Manager, la dirección IP desde la que se realizó la petición, quién realizó la petición, cuándo se realizó y detalles adicionales.

### API PutRecords

La matriz de registros de respuesta incluye registros procesados con éxito y registros procesados sin éxito. Kinesis Data Streams intenta procesar todos los registros de cada petición PutRecords. El fallo de un solo registro no detiene el procesamiento de los registros posteriores. Como resultado, PutRecords no garantiza el orden de los registros. Un registro procesado sin éxito incluye los valores ErrorCode y ErrorMessage. ErrorCode refleja el tipo de error y puede ser uno de los siguientes valores: ProvisionedThroughputExceededException" o "InternalFailure". ProvisionedThroughputExceededException" indica que la tasa de peticiones para el stream es demasiado alta, o que los datos solicitados son demasiado grandes para el throughput disponible. Reduzca la frecuencia o el tamaño de sus peticiones.

Para abordar el caso de uso dado, puede aplicar estas mejores prácticas:

Refuerce su stream para aumentar el número de fragmentos en el stream.

Reduzca la frecuencia o el tamaño de sus peticiones.

Distribuya las operaciones de lectura y escritura de la forma más uniforme posible entre todos los fragmentos de los flujos de datos.

Utilice un mecanismo de reintento de error y de backoff exponencial.

### credenciales de seguridad que sólo puede ser creada por el usuario root de la cuenta de AWS

**Pares de claves de CloudFron**t - Los usuarios de IAM no pueden crear pares de claves de CloudFront. Debe iniciar sesión con credenciales de root para crear pares de claves.

Para crear URL firmadas o Cookies firmadas, necesita un firmante. Un firmante es un grupo de claves de confianza que se crea en CloudFront o una cuenta de AWS que contiene un par de claves de CloudFront. AWS recomienda que utilice grupos de claves de confianza con URL firmadas y cookies firmadas en lugar de utilizar pares de claves de CloudFront.

### Activar el almacenamiento en caché de API en API Gateway.

API Gateway proporciona algunas estrategias para optimizar su API con el fin de mejorar la capacidad de respuesta, como el almacenamiento en caché de respuestas y la compresión de la carga útil. Puede habilitar el almacenamiento en caché de API en Amazon API Gateway para almacenar en caché las respuestas de su endpoint. Con el almacenamiento en caché, puede reducir el número de llamadas realizadas a su endpoint y también mejorar la latencia de las peticiones a su API.

### Secciones plantilla YAML de CloudFormation

**Sección 'Conditions' de la plantilla** - Esta sección opcional incluye condiciones que controlan si se crean determinados recursos o si se asigna un valor a determinadas propiedades de recursos durante la creación o actualización de stacks. Por ejemplo, podría crear condicionalmente un recurso que dependa de si el stack es para un entorno de producción o de test.

**Sección 'Resources' de la plantilla** - Esta es la única sección obligatoria y especifica los recursos de la pila y sus propiedades, como una instancia de Amazon Elastic Compute Cloud o un bucket de Amazon Simple Storage Service. Puede hacer referencia a los recursos en las secciones Resources y Outputs de la plantilla.

**Sección 'Parameters' de la plantilla** - Esta sección opcional es útil para pasar valores a la plantilla en tiempo de ejecución (al crear o actualizar un stack). Puede hacer referencia a los parámetros desde las secciones Recursos y Salidas de la plantilla.

### entidades de AWS que pueden utilizar para implementar certificados de servidor SSL/TLS

**AWS Certificate Manager** - AWS Certificate Manager (ACM) es la herramienta preferida para aprovisionar, administrar e implementar certificados de servidor. Con ACM puede solicitar un certificado o implementar un certificado existente de ACM o externo en los recursos de AWS. Los certificados proporcionados por ACM son gratuitos y se renuevan automáticamente. En una región con soporte, puede utilizar ACM para administrar certificados de servidor desde la consola o mediante programación.

**IAM** - IAM se utiliza como administrador de certificados sólo cuando debe soportar conexiones HTTPS en una región que no es soportada por ACM. IAM cifra de forma segura sus claves privadas y almacena la versión cifrada en el almacenamiento de certificados SSL de IAM. IAM soporta la implementación de certificados de servidor en todas las regiones, pero debe obtener su certificado de un proveedor externo para utilizarlo con AWS. No puede cargar un certificado ACM en IAM. Además, no puede administrar sus certificados desde la consola de IAM.

### Registro CNAME

Un registro CNAME mapea las consultas DNS para el nombre del registro actual, como acme.example.com, a otro dominio (example.com o example.net) o subdominio (acme.example.com o zenith.example.org).

Los registros CNAME pueden utilizarse para mapear un nombre de dominio a otro. Aunque debe tener en cuenta que el protocolo DNS no permite crear un registro CNAME para el nodo superior de un espacio de nombres DNS, también conocido como vértice de la Zona. Por ejemplo, si registra el nombre DNS ejemplo.com, el vértice de zona es ejemplo.com. No puede crear un registro CNAME para example.com, pero puede crear registros CNAME para <www.example.com>, newproduct.example.com, etc.

### AWS requiere aproximadamente 5 semanas de datos de uso para generar previsiones de presupuesto

WS requiere aproximadamente 5 semanas de datos de uso para generar previsiones de presupuesto. Si configura un presupuesto para que emita una alerta basada en un importe previsto, esta alerta de presupuesto no se activará hasta que disponga de suficiente información histórica de uso.

### Función Access Advisor en consola IAM

Para ayudar a identificar los roles no utilizados, IAM informa de la marca de tiempo de último uso que representa cuándo se utilizó un rol por última vez para realizar una petición de AWS. Su equipo de seguridad puede utilizar esta información para identificar, analizar y, a continuación, eliminar con confianza los roles no utilizados. Esto ayuda a mejorar la postura de seguridad de sus entornos de AWS. Además, al eliminar los roles no utilizados, puede simplificar sus esfuerzos de monitorización y auditoría al centrarse únicamente en los roles que están en uso.

### Habilitar los tiempos de espera de CodeBuild

Una compilación representa un conjunto de acciones realizadas por AWS CodeBuild para crear artefactos de salida (por ejemplo, un archivo JAR) basados en un conjunto de artefactos de entrada (por ejemplo, una colección de archivos de clases Java).

Las siguientes reglas se aplican cuando se ejecutan varias compilaciones:

Siempre que sea posible, las compilaciones se ejecutan simultáneamente. El número máximo de compilaciones que pueden ejecutarse simultáneamente puede variar.

Las compilaciones se ponen en cola si el número de compilaciones que se ejecutan simultáneamente alcanza su límite. El número máximo de construcciones en una cola es cinco veces el límite de construcciones simultáneas.

Una compilación en cola que no se inicia tras el número de minutos especificado en su valor de tiempo de espera se elimina de la cola. El tiempo de espera por defecto es de ocho horas. Puede anular el tiempo de espera de la cola de construcción con un valor entre cinco minutos y ocho horas cuando ejecute su construcción.

Al establecer la configuración del tiempo de espera, el proceso de compilación finalizará automáticamente una vez transcurrido el tiempo de espera configurado.

### CodeDeploy

AWS CodeDeploy es un servicio de implementación que automatiza las implementaciones de aplicaciones en instancias de Amazon EC2, instancias on-premise o funciones de Lambda sin servidor. AWS CodeBuild es un servicio de integración continua totalmente administrado que compila código fuente, ejecuta pruebas y produce paquetes de software listos para implementar.

WS CodeDeploy es un servicio de "implementación" totalmente administrado que automatiza las implementaciones de software en una variedad de servicios informáticos como Amazon EC2, AWS Fargate, AWS Lambda y sus servidores on-premise. AWS CodeDeploy le facilita el lanzamiento rápido de nuevas características, le ayuda a evitar el tiempo de inactividad durante la implementación de aplicaciones y maneja la complejidad de actualizar sus aplicaciones. Esta es la opción correcta para el caso de uso actual.

El tipo de implementación Blue/Green utiliza el modelo de implementación Blue/Green controlado por CodeDeploy. Este tipo de despliegue permite verificar un nuevo despliegue de servicio antes de enviarle tráfico de producción.

### AWS CodePipeline

AWS CodePipeline es un servicio de "entrega continua" totalmente administrado que le ayuda a automatizar sus canalizaciones de lanzamiento para actualizaciones rápidas y fiables de aplicaciones e infraestructuras. CodePipeline automatiza las fases de creación, test e implementación de su proceso de lanzamiento cada vez que se produce un cambio en el código, en función del modelo de lanzamiento que defina. Esto le permite ofrecer funciones y actualizaciones de forma rápida y fiable. Mientras que CodeDeploy es un servicio de despliegue, CodePipeline es un servicio de entrega continua.

### AWS CodeBuild

AWS CodeBuild es un servicio de integración continua totalmente administrado que compila código fuente, ejecuta pruebas y produce paquetes de software listos para implementarse. Con CodeBuild, no necesita aprovisionar, administrar ni escalar sus propios servidores de creación. CodeBuild se escala de forma continua y procesa varias compilaciones simultáneamente, por lo que sus compilaciones no se quedan esperando en una cola.

### Presentar el identificador único de cada petición en una tabla de DynamoDB. Cambie la función de Lambda para comprobar la tabla en busca del identificador antes de procesar la petición

DynamoDB es una base de datos NoSQL de valores clave, sin servidor y totalmente gestionada, diseñada para ejecutar aplicaciones de alto rendimiento a cualquier escala. DynamoDB ofrece seguridad integrada, copias de seguridad continuas, replicación multirregión automatizada, almacenamiento en caché en memoria y herramientas de importación y exportación de datos. Las funciones de copia de seguridad y restauración bajo demanda permiten crear copias de seguridad completas de DynamoDB. La recuperación puntual (PITR) ayuda a proteger las tablas de DynamoDB de operaciones accidentales de escritura o eliminación. PITR proporciona copias de seguridad continuas de los datos de su tabla DynamoDB, y puede restaurar esa tabla a cualquier punto en el tiempo hasta el segundo durante los 35 días anteriores.

Estas características garantizan que no haya pérdida de datos para la aplicación, cumpliendo así un requisito clave para el caso de uso dado. La solución también debe ser capaz de abordar cualquier petición duplicada sin incoherencias, por lo que la función Lambda debe cambiarse para inspeccionar la tabla para el identificador dado y procesar la petición solo si el identificador es único.

### Secrets Manager

AWS Secrets Manager le permite rotar, gestionar y recuperar fácilmente credenciales de bases de datos, claves API y otros secretos a lo largo de su ciclo de vida. Los usuarios y las aplicaciones recuperan los secretos con una llamada a las API de Secrets Manager, lo que elimina la necesidad de codificar información confidencial en texto sin formato. Secrets Manager ofrece rotación de secretos con integración incorporada para Amazon RDS, Amazon Redshift y Amazon DocumentDB.

### Utilizar la API TransactWriteItems de DynamoDB Transactions

Con las transacciones de Amazon DynamoDB, puede agrupar varias acciones y enviarlas como una única operación de todo o nada TransactWriteItems o TransactGetItems.

TransactWriteItems" es una operación de escritura síncrona e idempotente que agrupa hasta 25 acciones de escritura en una única operación "todo o nada". Estas acciones pueden tener como destino hasta 25 elementos distintos en una o varias tablas de DynamoDB dentro de la misma cuenta de AWS y en la misma región. El tamaño agregado de los elementos de la transacción no puede superar los 4 MB. Las acciones se completan de forma atómica, de modo que o todas se ejecutan correctamente o ninguna lo hace.

Puede incluir opcionalmente un token de cliente cuando realice una llamada a TransactWriteItems para asegurarse de que la petición es idempotente. Hacer que sus transacciones sean idempotentes ayuda a prevenir errores de aplicación si la misma operación se envía varias veces debido a un tiempo de espera de la conexión u otro problema de conectividad.

### Utilizar colas de retardo para posponer la entrega de nuevos mensajes a la cola durante unos segundos

Las colas de retardo te permiten posponer la entrega de nuevos mensajes a una cola durante varios segundos, por ejemplo, cuando tu aplicación de consumo necesita tiempo adicional para procesar los mensajes. Si creas una cola de retardo, los mensajes que envíes a la cola permanecerán invisibles para los consumidores durante el periodo de retardo. El retardo por defecto (mínimo) para una cola es de 0 segundos. El máximo es de 15 minutos.

### Utilizar Cognito User Pools para facilitar el registro y la administración de usuarios para la aplicación móvil

Amazon Cognito proporciona autenticación, autorización y gestión de usuarios para sus aplicaciones web y móviles. Tus usuarios pueden iniciar sesión directamente con un nombre de usuario y una contraseña, o a través de terceros como Facebook, Amazon, Google o Apple.

### Habilitar la integración de S3 y CloudWatch Logs

AWS CodeBuild monitoriza las funciones en su nombre e informa de las métricas a través de Amazon CloudWatch. Estas métricas incluyen el número de compilaciones totales, las compilaciones fallidas, las compilaciones correctas y la duración de las compilaciones. Puede monitorizar sus compilaciones a dos niveles: Nivel de proyecto y nivel de cuenta de AWS. Puede exportar datos de logs de sus grupos de logs a un bucket de Amazon S3 y utilizar estos datos en procesamientos y análisis personalizados, o para cargarlos en otros sistemas.

### Implementar una cola de mensajes fallidos

Amazon SQS soporta las colas de mensajes fallidos, a las que pueden dirigirse otras colas (colas de origen) para los mensajes que no se pueden procesar (consumir) correctamente. Las colas de mensajes fallidos son útiles para depurar la aplicación o el sistema de mensajería, ya que permiten aislar los mensajes problemáticos para determinar por qué no se procesan correctamente. Amazon SQS no crea la cola de mensajes fallidos automáticamente. Primero debe crear la cola antes de utilizarla como cola de mensajes fallidos.

### sin límite

No hay límites de mensajes para almacenar en SQS, pero los "mensajes en vuelo" sí tienen límites. Asegúrese de eliminar los mensajes después de haberlos procesado. Puede haber un máximo aproximado de 120.000 mensajes inflight (recibidos de una cola por un consumidor, pero aún no borrados de la cola).

### dynamodb:UpdateItem, dynamodb:GetItem

Con las transacciones de Amazon DynamoDB, puede agrupar varias acciones y enviarlas como una única operación TransactWriteItems o TransactGetItems de todo o nada.

Puede utilizar AWS Identity and Access Management (IAM) para restringir las acciones que pueden realizar las operaciones transaccionales en Amazon DynamoDB. Los permisos para las acciones Put, Update, Delete y Get se rigen por los permisos utilizados para las operaciones PutItem, UpdateItem, DeleteItem y GetItem subyacentes. Para la acción ConditionCheck, puede utilizar el permiso dynamodb:ConditionCheck en las políticas de IAM.

La acción UpdateItem de las API de DynamoDB edita los atributos de un elemento existente o añade un nuevo elemento a la tabla si aún no existe. Puede poner, eliminar o añadir valores de atributos. También puede realizar una actualización condicional en un elemento existente (insertar un nuevo par nombre-valor de atributo si no existe, o reemplazar un par nombre-valor existente si tiene ciertos valores de atributo esperados).

No es necesario incluir la acción dynamodb:PutItem para este caso de uso.

Por lo tanto, la política IAM debe incluir permisos para obtener y actualizar el elemento en la tabla de DynamoDB.

### Volumen de 200 GiB con 15000 IOPS

Esta configuración no es válida. El ratio máximo de IOPS provisionadas respecto al tamaño de volumen solicitado (en GiB) es de 50:1. Por lo tanto, para un volumen de 200 GiB, las IOPS máximas posibles son 200*50 = 10000 IOPS.

### Configurar la aplicación para obtener las variables y las credenciales del almacén de parámetros de AWS Systems Manager aprovechando las rutas jerárquicas únicas del almacén de parámetros para cada variable de cada entorno

Los almacenes de parámetros son una capacidad de AWS Systems Manager que proporciona un almacenamiento seguro y jerárquico para la administración de datos de configuración y la administración de secretos. Puede almacenar datos como contraseñas, Strings de bases de datos, ID de imágenes de máquina de Amazon (AMI) y códigos de licencia como valores de parámetros. Puede almacenar valores como texto sin formato o datos cifrados. Puede hacer referencia a los parámetros de Systems Manager en sus scripts, comandos, documentos SSM y flujos de trabajo de configuración y automatización utilizando el nombre único que especificó al crear el parámetro.

Gestionar docenas o cientos de parámetros como una lista plana lleva mucho tiempo y es propenso a errores. También puede ser difícil identificar el parámetro correcto para una tarea. Esto significa que podría utilizar accidentalmente el parámetro equivocado, o podría crear múltiples parámetros que utilizan los mismos datos de configuración.

Las jerarquías de parámetros ayudan a organizar y gestionar los parámetros. Una jerarquía es un nombre de parámetro que incluye una ruta que se define utilizando barras inclinadas (/).

### Amazon Kinesis Data Firehose

Es un servicio totalmente administrado para entregar datos de streaming en tiempo real a destinos como Amazon Simple Storage Service (Amazon S3), Amazon Redshift, Amazon Elasticsearch Service (Amazon ES) y Splunk. Con Kinesis Data Firehose, no necesita escribir aplicaciones ni gestionar recursos. Usted configura sus productores de datos para que envíen datos a Kinesis Data Firehose, y éste los entrega automáticamente al destino que haya especificado.

### Amazon ElastiCache con Amazon S3 como backup

Amazon ElastiCache es un almacén de datos en memoria totalmente gestionado, compatible con Redis o Memcached. ElastiCache NO es un destino soportado por Amazon Kinesis Data Firehose.

### CloudFormation actualmente soporta los siguientes tipos de parámetros

<pre>
    <code>
        String – Una cadena literal
        Number – Un entero o flotante
        List< Number> – Una matriz de números enteros o flotantes
        CommaDelimitedList – Una matriz de Strings literales separadas por comas
        AWS::EC2::KeyPair::KeyName – Un nombre de par de claves de Amazon EC2
        AWS::EC2::SecurityGroup::Id – Un ID de grupo de seguridad
        AWS::EC2::Subnet::Id – Un ID de subred
        AWS::EC2::VPC::Id – Un ID de VPC
        List<AWS::EC2::VPC::Id> – Una matriz de VPC IDs
        List<AWS::EC2::SecurityGroup::Id> – Una matriz de IDs de grupos de seguridad
        List<AWS::EC2::Subnet::Id> – Una matriz de IDs de subred
    </code>
</pre>

### Utilizar la opción --dry-run de la CLI de AWS

La opción --dry-run comprueba si tiene los permisos necesarios para la acción, sin realizar realmente la petición, y proporciona una respuesta de error. Si dispone de los permisos necesarios, la respuesta de error es DryRunOperation; de lo contrario, es UnauthorizedOperation.

### Escrituras condicionales

DynamoDB soporta opcionalmente escrituras condicionales para operaciones de escritura (PutItem, UpdateItem, DeleteItem). Una escritura condicional sólo tiene éxito si los atributos del elemento cumplen una o más condiciones esperadas. En caso contrario, devuelve un error.

Por ejemplo, puede que desee que una operación PutItem tenga éxito sólo si no hay ya un elemento con la misma clave primaria. O impedir que una operación UpdateItem modifique un elemento si uno de sus atributos tiene un valor determinado. Las escrituras condicionales son útiles cuando varios usuarios intentan modificar el mismo elemento. Esta es la opción correcta para el escenario actual.

### Utilizar las API de lectura y escritura transaccionales de DynamoDB en los elementos de la tabla como una operación única de todo o nada.

Puede utilizar las transacciones de DynamoDB para realizar cambios coordinados de todo o nada en varios elementos, tanto dentro de las tablas como entre ellas. Las transacciones proporcionan atomicidad, consistencia, aislamiento y durabilidad (ACID) en DynamoDB, ayudándole a mantener la corrección de los datos en sus aplicaciones.

### Completar ambas operaciones en RDS MySQL en un único bloque de transacciones

Amazon Relational Database Service (Amazon RDS) facilita la configuración, el funcionamiento y el escalado de una base de datos relacional con soporte para transacciones en el Cloud. Una base de datos relacional es una colección de elementos de datos con relaciones predefinidas entre ellos. RDS soporta las aplicaciones de bases de datos más exigentes. Puede elegir entre dos opciones de almacenamiento respaldado por SSD: una optimizada para aplicaciones de procesamiento de transacciones en línea (OLTP) de alto rendimiento, y la otra para uso general rentable.

### Definir un archivo appspec.yml en el directorio raíz

Un archivo AppSpec debe ser un archivo con formato YAML llamado appspec.yml y debe colocarse en la raíz de la estructura de directorios del código fuente de una aplicación.

El archivo AppSpec se utiliza para:

Mapear los archivos fuente en la revisión de su aplicación a sus destinos en la instancia.

Especificar permisos personalizados para los archivos desplegados.

Especificar los scripts que se ejecutarán en cada instancia en las distintas fases del proceso de despliegue.

Durante el despliegue, el agente CodeDeploy busca el nombre del evento actual en la sección hooks del archivo AppSpec. Si no encuentra el evento, el agente de CodeDeploy pasa al siguiente paso. Si se encuentra el evento, el agente de CodeDeploy recupera la lista de scripts a ejecutar. Los scripts se ejecutan secuencialmente, en el orden en que aparecen en el archivo. El estado de cada script se registra en el archivo logs del agente de CodeDeploy en la instancia.

Si un script se ejecuta correctamente, devuelve un código de salida de 0 (cero). Si el agente de CodeDeploy instalado en el sistema operativo no coincide con lo que aparece en el archivo AppSpec, el despliegue falla.

### Un grupo de usuarios es un directorio de usuarios en Amazon Cognito

Con un grupo de usuarios, sus usuarios pueden iniciar sesión en su aplicación web o móvil a través de Amazon Cognito. Sus usuarios también pueden iniciar sesión a través de proveedores de identidad social como Google, Facebook, Amazon o Apple, y proveedores de identidad SAML. Tanto si sus usuarios inician sesión directamente como a través de un tercero, todos los miembros del grupo de usuarios tienen un perfil de directorio al que puede acceder a través de un kit de desarrollo de software (SDK).

Los grupos de usuarios proporcionan:

Servicios de registro e inicio de sesión.

Una interfaz de usuario web integrada y personalizable para registrar a los usuarios.

Inicio de sesión social con Facebook, Google, inicio de sesión con Amazon e inicio de sesión con Apple, así como inicio de sesión con proveedores de identidad SAML de su grupo de usuarios.

Gestión del directorio de usuarios y perfiles de usuario.

Funciones de seguridad como la autenticación multifactor (MFA), comprobaciones de credenciales comprometidas, protección de toma de control de cuentas y verificación de teléfono y correo electrónico.

Flujos de trabajo personalizados y migración de usuarios a través de disparadores de AWS Lambda.

Para utilizar un grupo de usuarios de Amazon Cognito con su API de Amazon API Gateway, primero debe crear un autorizador del tipo COGNITO_USER_POOLS y, a continuación, configurar un método de API para utilizar ese autorizador. Una vez desplegada la API, el cliente debe primero registrar al usuario en el grupo de usuarios, obtener un token de identidad o acceso para el usuario y, a continuación, llamar al método API con uno de los tokens, que normalmente se establecen en el encabezado Authorization de la petición.

Para el caso de uso dado, puede utilizar un grupo de usuarios de Cognito para administrar cuentas de usuario y configurar un autorizador de grupo de usuarios de Amazon Cognito en API Gateway para controlar el acceso a la API. Debe utilizar una función Lambda para almacenar las imágenes reales en S3 y los metadatos de las imágenes en DynamoDB. Por último, puede obtener las imágenes mediante la función Lambda que aprovecha los metadatos almacenados en DynamoDB.

### VPC Flow Logs

VPC Flow Logs es una característica que le permite capturar información sobre el tráfico IP que entra y sale de las interfaces de red de su VPC. Los datos de los logs de flujo se pueden publicar en Amazon CloudWatch Logs o Amazon S3. Una vez creado un logs de flujo, puede recuperar y ver sus datos en el destino elegido.

Puede crear un logs de flujo para una VPC, una subred o una interfaz de red. Si crea un logs de flujo para una subred o VPC, se supervisa cada interfaz de red de esa subred o VPC.

Los datos del registro de flujo para una interfaz de red supervisada se registran como logs de flujo, que son eventos de registro que constan de campos que describen el flujo de tráfico.

### Cognito Sync

Amazon Cognito Sync es un servicio de AWS y una biblioteca de clientes que permite la sincronización entre dispositivos de los datos de usuario relacionados con la aplicación. Puede utilizarlo para sincronizar los datos de perfil de usuario entre dispositivos móviles y la web sin necesidad de su propio backend. 

### La tabla de enrutamiento en la subred de la instancia debe tener una ruta a un Gateway de Internet

Una tabla de enrutamiento contiene un conjunto de reglas, llamadas rutas, que se utilizan para determinar hacia dónde se dirige el tráfico de red desde su subred o Gateway. La tabla de enrutamiento en la subred de la instancia debería tener una ruta definida hacia el Gateway de Internet.

### Generar una clave SSH pública a partir de una clave SSH privada. A continuación, importe la clave en cada una de sus regiones de AWS.

Esta es la forma correcta de reutilizar claves SSH en tus regiones AWS:

1. Genere un archivo de clave SSH pública (.pub) a partir del archivo de clave SSH privada (.pem).
1. Establezca la región de AWS a la que desea importar.
1. Importe la clave SSH pública a la nueva región.

### S3 Access Logs está apuntando al mismo bucket y es responsable del crecimiento sustancial del tamaño del bucket

Cuando su bucket de origen y su bucket de destino son el mismo bucket, se crean logs adicionales para los logs que se escriben en el bucket. Los logs adicionales sobre logs pueden hacer más difícil encontrar el log que está buscando. Esta configuración aumentaría drásticamente el tamaño del bucket de S3.

### 5,3 TiB

Los volúmenes SSD de propósito general (gp2) ofrecen un almacenamiento rentable ideal para una amplia gama de cargas de trabajo. Estos volúmenes ofrecen latencias de un milisegundo y la capacidad de alcanzar los 3.000 IOPS durante largos periodos de tiempo. Entre un mínimo de 100 IOPS (a 33,33 GiB y menos) y un máximo de 16.000 IOPS (a 5.334 GiB y más), el rendimiento básico se escala linealmente a 3 IOPS por GiB de tamaño de volumen.

### Para implementar una imagen de contenedor en Lambda, la imagen de contenedor debe implementar la API de tiempo de ejecución de Lambda

Para implementar una imagen de contenedor en Lambda, la imagen de contenedor debe implementar la API de tiempo de ejecución de Lambda. Los clientes de interfaz de tiempo de ejecución de código abierto de AWS implementan la API. Puede añadir un cliente de interfaz de tiempo de ejecución a su imagen base preferida para hacerla compatible con Lambda.

### Debe crear la función Lambda desde la misma cuenta que el registro de contenedores en Amazon ECR

Puede empaquetar el código de su función Lambda y las dependencias como una imagen de contenedor, utilizando herramientas como la CLI de Docker. A continuación, puede cargar la imagen en su registro de contenedores alojado en Amazon Elastic Container Registry (Amazon ECR). Tenga en cuenta que debe crear la función Lambda desde la misma cuenta que el registro de contenedores en Amazon ECR.

### Agregar las dependencias en el código fuente durante la etapa de compilación de CodeBuild.

AWS CodeBuild es un servicio de creación totalmente administrado. No hay servidores que aprovisionar y escalar, ni software que instalar, configurar y operar.

Un proceso típico de creación de aplicaciones incluye fases como la preparación del entorno, la actualización de la configuración, la descarga de dependencias, la ejecución de pruebas unitarias y, por último, el empaquetado del artefacto creado.

La descarga de dependencias es una fase crítica del proceso de compilación. El tamaño de estos archivos dependientes puede oscilar entre unos pocos KB y varios MB. Dado que la mayoría de los archivos dependientes no cambian con frecuencia entre compilaciones, puedes reducir notablemente el tiempo de compilación almacenando en caché las dependencias.

Esto permitirá que el paquete de código que se despliegue en Elastic Beanstalk contenga tanto las dependencias como el código, acelerando así el tiempo de despliegue en Elastic Beanstalk.

### Utilizar cifrado de sobre y hacer referencia a los datos como archivo dentro del código

Aunque AWS KMS soporta el envío de datos de hasta 4 KB para ser cifrados directamente, el cifrado de sobres puede ofrecer importantes ventajas de rendimiento. Cuando cifra datos directamente con AWS KMS, estos deben transferirse a través de la red. El cifrado de sobres reduce la carga de la red, ya que sólo la petición y la entrega de la clave de datos, mucho más pequeña, van por la red. La clave de datos se utiliza localmente en su aplicación o servicio de AWS de cifrado, lo que evita la necesidad de enviar todo el bloque de datos a AWS KMS y sufrir latencia de red.

Las variables de entorno de AWS Lambda pueden tener un tamaño máximo de 4 KB. Además, la API directa 'Encrypt' de KMS también tiene un límite máximo de 4 KB para la carga útil de datos. Para cifrar 1 MB, es necesario utilizar el SDK de cifrado y empaquetar el archivo cifrado con la función lambda.

### Redistribuir la API en un escenario existente o en un escenario nuevo

Después de crear su API, debe desplegarla para que sus usuarios puedan llamarla. Para desplegar una API, debe crear un despliegue de API y asociarlo a una etapa. Una etapa es una referencia lógica a un estado del ciclo de vida de su API (por ejemplo, dev, prod, beta, v2). Las etapas de la API se identifican mediante el ID de la API y el nombre de la etapa. Cada vez que actualice una API, debe volver a desplegarla en una etapa existente o en una nueva. La actualización de una API incluye la modificación de rutas, métodos, integraciones, autorizadores y cualquier otro elemento que no sea la configuración de la etapa.

### Configurar el escalado automático de aplicaciones para gestionar la concurrencia aprovisionada de Lambda de forma programada

La concurrencia es el número de peticiones que una función Lambda está atendiendo en un momento dado. Si se vuelve a invocar una función Lambda mientras se está procesando una petición, se asigna otra instancia, lo que aumenta la concurrencia de la función.

Debido a un pico de tráfico, cuando las funciones Lambda se escalan, esto provoca que la parte de las peticiones que son servidas por nuevas instancias tengan una latencia mayor que el resto. Para permitir que su función escale sin fluctuaciones en la latencia, utilice concurrencia provisionada. Al asignar concurrencia provisionada antes de un aumento en las invocaciones, puede asegurarse de que todas las peticiones son servidas por instancias inicializadas con una latencia muy baja.

Puede configurar el Autoescalado de Aplicaciones para gestionar la concurrencia provisionada de forma programada o en función de la utilización. Utilice el escalado programado para aumentar la concurrencia aprovisionada en previsión de picos de tráfico. Para aumentar la concurrencia aprovisionada automáticamente según sea necesario, utilice la API de Application Auto Scaling para registrar un destino y crear una política de escalado.

### Utilizar la capacidad de backup bajo demanda de DynamoDB para escribir en Amazon S3 y descargar localmente

Esta opción no es viable para el caso de uso dado. DynamoDB cuenta con dos métodos de copia de seguridad integrados (bajo demanda y recuperación puntual) que escriben en Amazon S3, pero no tendrá acceso a los buckets de S3 que se utilizan para estas copias de seguridad.

### ValidateService

ValidateService es el último evento del ciclo de vida del despliegue. Se utiliza para verificar que la implantación se ha realizado correctamente..

### AfterInstall

Puede utilizar este evento del ciclo de vida de la implantación para tareas como configurar la aplicación o cambiar los permisos de los archivos

### ApplicationStart

Normalmente se utiliza este evento del ciclo de vida de despliegue para reiniciar los servicios que se detuvieron durante ApplicationStop

### AllowTraffic

Durante este evento del ciclo de vida de despliegue, se permite el acceso del tráfico de Internet a las instancias después de un despliegue. Este evento está reservado para el agente de AWS CodeDeploy y no se puede utilizar para ejecutar scripts.

### Crear un rol IAM con acceso a S3 en la Cuenta B y establecer la Cuenta A como entidad de confianza. Crear otro rol (perfil de instancia) en la Cuenta A y adjuntarlo a las instancias EC2 en la Cuenta A y añadir una política en línea a este rol para asumir el rol de la Cuenta B

Puede dar a las instancias EC2 de una cuenta ("cuenta A") permisos para asumir un rol de otra cuenta ("cuenta B") para acceder a recursos como buckets S3. Debe crear un rol de IAM en la cuenta B y establecer la cuenta A como entidad de confianza. A continuación, adjunte una política a este rol de IAM para que delegue el acceso a Amazon S3.

### API Gateway que expone la funcionalidad de Lambda

Amazon API Gateway es un servicio totalmente administrado que facilita a los desarrolladores la creación, publicación, mantenimiento, monitorización y protección de API a cualquier escala. Las API actúan como la "puerta de entrada" para que las aplicaciones accedan a los datos, la lógica empresarial o la funcionalidad de sus servicios backend.

### Instancias reservadas de zona

Una instancia reservada de zona proporciona una reserva de capacidad en la Zona de disponibilidad especificada. Las reservas de capacidad le permiten reservar capacidad para sus instancias de Amazon EC2 en una zona de disponibilidad específica para cualquier duración. Esto le ofrece la posibilidad de crear y administrar Reservas de capacidad independientemente de los descuentos de facturación que ofrecen los Planes de ahorro o las Instancias reservadas regionales.

### AWS Security Token Service (STS)

AWS Security Token Service (AWS STS) es un servicio web que le permite solicitar credenciales temporales con privilegios limitados para usuarios de AWS Identity and Access Management (IAM) o para usuarios autenticados por usted (usuarios federados). Sin embargo, no está soportado por API Gateway.

### Plantillas SAM

Las plantillas del modelo de aplicación sin servidor (SAM) incluyen varias secciones principales. Transform y Resources son las únicas secciones obligatorias.

### Compartir URLs pre-firmadas con recursos que necesitan acceso

Todos los objetos por defecto son privados, con el propietario del objeto teniendo permiso para acceder a los objetos. Sin embargo, el propietario del objeto puede, opcionalmente, compartir objetos con otros mediante la creación de una URL prefirmada, utilizando sus propias credenciales de seguridad, para conceder permiso limitado en el tiempo para descargar los objetos. Al crear una URL prefirmada para su objeto, debe proporcionar sus credenciales de seguridad, especificar un nombre de bucket, una clave de objeto, especificar el método HTTP (GET para descargar el objeto) y la fecha y hora de caducidad. Las URL prefirmadas sólo son válidas durante el tiempo especificado.

### Configurar endpoints de VPC para DynamoDB que proporcionen el acceso interno necesario sin utilizar Internet público

Cuando crea un punto de enlace de VPC para DynamoDB, cualquier petición a un punto de enlace de DynamoDB dentro de la región (por ejemplo, dynamodb.us-west-2.amazonaws.com) se enruta a un punto de enlace privado de DynamoDB dentro de la red de Amazon. No es necesario que modifique sus aplicaciones que se ejecutan en instancias EC2 en su VPC. El nombre del endpoint sigue siendo el mismo, pero la ruta a DynamoDB permanece completamente dentro de la red de Amazon y no accede a la Internet pública. Utilice políticas de endpoint para controlar el acceso a DynamoDB. El tráfico entre su VPC y el servicio de AWS no sale de la red de Amazon.

### Utilizar ConsistentRead = true al realizar la operación GetItem para cualquier elemento

DynamoDB soporta lecturas consistentes y fuertemente consistentes.

Lecturas eventualmente consistentes

Al leer datos de una tabla de DynamoDB, es posible que la respuesta no refleje los resultados de una operación de escritura completada recientemente. La respuesta puede incluir algunos datos obsoletos. Si repite la petición de lectura al cabo de poco tiempo, la respuesta debería devolver los datos más recientes.

Lecturas fuertemente consistentes

Cuando se solicita una lectura fuertemente consistente, DynamoDB devuelve una respuesta con los datos más actualizados, reflejando las actualizaciones de todas las operaciones de escritura anteriores que tuvieron éxito.

DynamoDB utiliza lecturas fuertemente consistentes de forma predeterminada. Las operaciones de lectura (como GetItem, Query y Scan) proporcionan un parámetro ConsistentRead. Si establece este parámetro en true, DynamoDB utiliza lecturas fuertemente consistentes durante la operación. En este caso de uso, para asegurarse de que la aplicación sólo utiliza el último valor actualizado de cualquier elemento, debe utilizar lecturas fuertemente consistentes estableciendo ConsistentRead = true para la operación GetItem.

### Arreglar el rol IAM

Cree un rol IAM con permisos de escritura y asígnelo a los recursos que ejecutan su aplicación. Puede utilizar AWS Identity and Access Management (IAM) para conceder permisos de X-Ray a los usuarios y recursos informáticos de su cuenta. Este debería ser uno de los primeros lugares por los que empezar comprobando que sus permisos están configurados correctamente antes de explorar otras opciones de solución de problemas.