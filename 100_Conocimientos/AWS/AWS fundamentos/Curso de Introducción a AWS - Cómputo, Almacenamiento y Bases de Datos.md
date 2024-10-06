## Cómputo AWS
### Instancias o máquinas virtuales

Una **máquina virtual** es un _software_ que simula un sistema operativo, y que puede ejecutar programas dentro de dicho sistema como si fuera una computadora real. Los servicios de máquinas virtuales (o instancias) en AWS son:

- **Amazon EC2**: máquinas virtuales seguras y redimensionables.
- **Amazon EC2 Spot**: cargas de trabajo tolerante a fallas, por hasta el 90% del precio normal (nota: Amazon puede reclamar estas instancias en cualquier momento con solo dos minutos de anticipación).
- **Amazon EC2 AutoScaling**: agrega o elimina automáticamente la capacidad informática para satisfacer tus necesidades bajo demanda.
- **Amazon EC2 LightSail**: plataforma en la nube fácil de usar para crear una aplicación o un sitio web.

### Contenedores

Un **contenedor** es una unidad de software que empaca un _software_ en específico junto con sus dependencias. Se diferencian de las máquinas virtuales en que estas virtualizan el _hardware,_ mientras que los contenedores [virtualizan el sistema operativo](https://cloud.google.com/learn/what-are-containers). Los servicios de contenedores de AWS son:

- **Amazon Elastic Container Services (ECS)**: servicio para correr contenedores confiables y escalables.
- **Amazon Elastic Container Registry (ECR)**: servicio para almacenar, administrar e implementar [imágenes de contenedores](https://platzi.com/clases/2066-docker/32856-conceptos-fundamentales-de-docker-imagenes/).
- **Amazon Elastic Kubernetes Service (EKS)**: servicio de [Kubernetes](https://platzi.com/cursos/k8s/) administrado por AWS.

### _Serverless_

La computación **_serverless_** se refiere a que **la responsabilidad de administrar servidores o máquinas virtuales se le delega al proveedor de nube,** por lo que sólo debemos precuparnos por el código de nuestras aplicaciones. **Amazon Lambda** nos permite ejecutar piezas de código sin servidores.

### Servicios de borde (_Edge_)

El [_Edge Computing_](https://www.xataka.com/internet-of-things/edge-computing-que-es-y-por-que-hay-gente-que-piensa-que-es-el-futuro) se refiere al **cómputo y procesamiento de datos en una ubicación cercana a la necesaria para el negocio.** Los servicios de borde o _edge_ computing de AWS son:

- **Amazon Outposts**: permite ejecutar los servicios de AWS en nuestros propios servidores en lugar de Amazon.
- **Amazon Snow Family**: es una familia de dispositivos desde un disco duro portátil hasta un semi-remolque completo lleno de discos de almacenamiento. Estos dispositivos te permiten cargar archivos en ellos, para luego ser enviados a Amazon y cargados en sus servidores.
- **AWS Wavelength**: permite acceder a los servicios AWS desde dispositivos 5G sin pasar por Internet.
- **VMWare AWS**: permite migrar cargas de trabajo de VMWare a AWS.
- **AWS Local Zones**: permite ejecutar las aplicaciones más cerca de los usuarios finales, a una menor latencia.



##  #EC2
** [EC2](https://platzi.com/clases/1323-aws-cloud-practico/12577-que-es-ec2/) permite alquilar máquinas virtuales, llamadas _instancias EC2_.** Puedes elegir diferentes tipos de #EC2 con diferente CPU, RAM y almacenamiento. Hay instancias optimizadas para cómputo, memoria y almacenamiento, [entre otras](https://docs.aws.amazon.com/es_es/AWSEC2/latest/UserGuide/instance-types.html).

En #EC2, el sistema de pago más común es por hora o por segundo, dependiendo el tipo de instancia. Por ejemplo, para una instancia que cueste $0.1 la hora, puedes pagar, ya sea una instancia por 24 horas o 24 instancias por una hora. En ambos casos pagas lo mismo (24 * 0.10 = $2.4).

### Opciones y precios bajo demanda

Las instancias pueden redimiensionarse. Puedes empezar por una instancia de bajo costo, y si necesitas aumenta su capacidad, apagas la instancia y seleccionas un nuevo tipo de instancia. Cuando enciendas de nuevo la instancia, verás su capacidad aumentada. La siguiente tabla muestra **algunos tipos de instancias.**

|Nombre|Especificaciones|Precio|
|---|---|---|
|t3.nano|2 vCPU’s, 0.5 GiB RAM|$0,0052/hora|
|t3.xlarge|4 vCPU’s, 16 GiB RAM|$0,1664/hora|
|c6g.8xlarge|32 vCPU’s, 64 GiB RAM|$1,088/hora|
|X1e.xlarge|128 vCPU’s, 3904 GiB RAM, 2x 1920 GB SSD|$26,688/hora|

### Hosts dedicados

Los hosts dedicados en Amazon Web Services (AWS) son infraestructuras de servidores físicos que ofrecen un nivel exclusivo de recursos computacionales para las cargas de trabajo de los clientes. En lugar de compartir estos servidores con otros usuarios, los hosts dedicados permiten a los clientes tener un control más granular sobre la ubicación y asignación de sus instancias de Amazon EC2. Esto puede ser beneficioso para aplicaciones que requieren una mayor seguridad, cumplimiento normativo o rendimiento constante.

Los hosts dedicados también brindan la flexibilidad de llevar licencias de software existentes a la nube sin incurrir en costos adicionales. Al utilizar hosts dedicados, los principiantes en AWS pueden garantizar una mayor aislación de recursos y una mayor predictibilidad en el rendimiento de sus aplicaciones, al tiempo que aprovechan la escala y la elasticidad de la nube de AWS.


## Almacenamiento de AWS
### Tipos de almacenamiento y sus servicios

Podemos utilizar distintos tipos almacenamiento datos, y para estos hay servicios de AWS. Los tipos de almacenamiento son:

- **Basado en archivos**: el más conocido por todos. Archivos organizados por carpetas y subcarpetas (sistema de ficheros). En esta categoría encontramos a [Amazon Elastic File System (EFS)](https://aws.amazon.com/es/efs/) y [Amazon FSx for Windows File Server](https://aws.amazon.com/es/fsx/windows/).
- **Bloque**: los archivos se almacenan en volúmenes por fragmentos de datos de igual tamaño, sin procesar. Este tipo de almacenamiento es utilizado como disco duro de nuestros servidores o máquinas virtuales. En esta categoría está [Amazon Elastic Block Store (EBS)](https://aws.amazon.com/es/ebs/).
- **Objetos**: la información almacenada se almacena como objetos, de manera que cada objeto recibe un identificador único y se almacena en un modelo de memoria plana. Un ejemplo de esto es [Amazon Simple Storage Service (S3)](https://aws.amazon.com/es/s3/).

### Respaldo de datos

**Amazon Backup administra y automatiza de forma centralizada** las copias de seguridad en los servicios de AWS.

### Servicios de transferencia de datos

¿Qué pasa si necesitamos transferir datos de nuestros servidores hacia AWS (o viceversa)? AWS ofrece distintos servicios para la transferencia de datos.

- **AWS Storage Gateway**: un conjunto de servicios de almacenamiento en la [nube híbrida](https://platzi.com/clases/2200-introduccion-azure/38231-tipos-de-nube-publica-privada-e-hibrida/) que brinda acceso en las instalaciones al almacenamiento en la nube.
- **AWS DataSync**: acelera el traslado de datos desde y hacia AWS hasta diez veces más rápido de lo normal.
- **AWS Transfer Family**: escala de forma segura tus transferencias recurrentes de archivos de **Amazon S3** y **Amazon EFS** con los protocolos [FTP](https://www.arsys.es/soporte/hosting-web/ftp/que-es-ftp#:~:text=FTP%20es%20un%20protocolo%20que,directorios%2C%20borrar%20ficheros%2C%20etc.), [SFTP](https://es.wikipedia.org/wiki/SSH_File_Transfer_Protocol) y [FTPS](https://es.wikipedia.org/wiki/FTPS).



## #S3

[Amazon S3](https://aws.amazon.com/es/s3/) es un servicio de almacenamiento de objetos, líder en la industria. Otorga una **garantía de no pérdida de datos del 99.999999999%** (11 9’s).

### Clases de almacenamiento en S3

Amazon nos ofrece [distintas clase de almacenamiento](https://aws.amazon.com/es/s3/storage-classes/?nc=sn&loc=3) S3 en función de nuestras necesidades de acceso y disponibilidad de los datos.

- **S3 Standard**: almacenamiento de objetos de alta durabilidad, disponibilidad y rendimiento para datos a los que se obtiene acceso con frecuencia.
- **S3 Standard-IA**: se utiliza con datos a los que se accede con menos frecuencia, pero que requieren un acceso rápido cuando es necesario.
- **S3 Zone-IA**: similar a Standard-IA, pero con un menor costo de almacenamiento ya que solo usa una zona de disponibilidad. Distinto de las demás clases de almacenamiento de S3, que almacenan datos en un mínimo de tres zonas de disponibilidad (AZ).
- **S3 Glacier**: ofrece el almacenamiento de menor costo para los datos de larga duración y acceso poco frecuente. Tiene un costo de $1 por TB al mes. Tiene tres opciones para la recuperación de datos (estándar, masiva y acelerada).
- **S3 Glacier Deep Archive**: la clase de almacenamiento más económica de Amazon S3. Admite la retención a largo plazo y la conservación digital de datos a los que se accede una o dos veces al año.
- **S3 Intelligent-Tiering**: un tipo de almacenamiento que intenta ahorrar costos moviendo archivos entre los distintos tipos de almacenamiento S3, basado en los patrones de uso de los archivos.


## #EFS
**Amazon Elastic File System (EFS)** brinda un sistema de archivos elástico, sencillo, sin servidor y práctico basado en **NFS** para las máquinas virtuales de EC2.

[**NFS**](https://www.computerweekly.com/es/definicion/Sistema-de-archivos-de-red-NFS) es un **protocolo de archivos en red que permite acceder a archivos y directorios que no están en tu sistema.** Esto permite que miles de máquinas puedan conectarse a [EFS](https://aws.amazon.com/es/efs/) y procesar los datos que allí se encuentran.

### Características de EFS

EFS es altamente disponible y duradero. **Provee protección contra una interrupción de la zona de disponibilidad,** replicando los archivos en múltiples zonas dentro de una región.

Adicionalmente:

- EFS brinda dos clases de almacenamiento: Standar y Standar IA (para acceso poco frecuente). Puedes implementar políticas para que tus archivos se muevan de Standar a Standar IA después de cierto tiempo.
- Los datos están **encriptados de manera automática.**



## AWS Storage Gateway
**AWS Storage Gateway nos brinda acceso a almacenamiento en la nube prácticamente ilimitado desde nuestra propia infraestructura**.

Storage Gateway se compone de tres puertas de acceso diferentes:

### File Gateway

**File Gateway** provee interfaces [SMB](https://es.wikipedia.org/wiki/Server_Message_Block) y NFS para amazon S3, tanto en Windows como en Linux. Gracias a [File Gateway](https://aws.amazon.com/es/storagegateway/file/), en ambos sistemas operativos veremos un sistema de archivos tal cual como si fuera un disco montado en nuestros computadores, los cuales escriben archivos al sistema, y **File Gateway se encarga de guardarlos en S3**.

Gracias a esto **podemos guardar archivos a S3 como si se tratara de guardar archivos locales.** Los archivos S3 luego pueden ser usados por cualquier servicio de AWS.

### Tape Gateway

Supón que tienes copias de seguridad en cintas físicas. **Tape Gateway te permite migrar copias de seguridad a una bibliteca de cintas virtuales en AWS.** Tape Gateway es compatible con los principales _software_ de respaldo.

Los contenidos de tus cintas se guardan en S3, lo que te permite implementar **S3 Glacier** y **S3 Glacier Deep Archive** para guardar tus copias de seguridad a largo plazo. Una vez que implementas [Tape Gateway](https://aws.amazon.com/es/storagegateway/vtl/), puedes olvidarte de los costos relacionados a mantener las cintas físicas.

### Volume Gateway

[**Volume Gateway**](https://aws.amazon.com/es/storagegateway/volume/#:~:text=Volume%20Gateway%20brinda%20vol%C3%BAmenes%20de,cach%C3%A9%20como%20en%20modo%20almacenado.) otorga **almacenamiento en bloque** con protocolo [iSCSI](https://community.fs.com/es/blog/iscsi-storage-basics-plan-iscsi-san.html#:~:text=el%20almacenamiento%20iSCSI%3F-,iSCSI%20es%20un%20protocolo%20de%20red%20de%20%C3%A1rea%20de%20almacenamiento,trav%C3%A9s%20de%20redes%20TCP%2FIP.), respaldado en la nube. Almacena datos en S3 de acuerdo a dos modos:

- **Modo caché**: almacena los datos principales en S3, mientras que los datos de acceso frecuente se guardan localmente y en caché.
- **Modo almacenado**: todos los datos se guardan localmente, mientras que se hace una copia de seguridad de manera asíncrona en S3.

### Conclusión

Vimos tres posibilidades de uso de [Amazon Storage Gateway](https://aws.amazon.com/es/storagegateway/). Para cada caso de uso, hay una puerta de acceso adecuada, ya sea **File**, **Tape** o **Volume Gateway**.

## Implementar política de acceso a nivel de bucket

Para crear una política de acceso, podemos apoyarnos de [AWS Policy Generator](https://awspolicygen.s3.amazonaws.com/policygen.html), una herramienta que nos permite generar políticas de acceso de AWS.

Estando en la herramienta, en _Select Policy Type_, seleccionamos **S3 Bucket Policy**. **En _Principal_, escribimos un asterisco (*).** En _Actions_, ubicamos la acción **getObject**. En **_Amazon Resource Name (ARN)_,** colocamos el **ARN** de nuestro bucket seguido de slash y asterisco (/*). El **ARN** lo podemos obtener en **bucket** -> **propiedades** -> **Información general sobre el bucket** -> **Nombre de recurso de Amazon (ARN)**.

Entonces hacemos **click en _Add Statement_,** y luego en **Generate policy**. **Copiamos el JSON** que nos aparece en pantalla. Debería ser similar a esto.

```
{
  ""Id"": ""Policy1649360676835"",
  ""Version"": ""2012-10-17"",
  ""Statement"": [
    {
      ""Sid"": ""Stmt1649360674639"",
      ""Action"": [
        ""s3:GetObject""
      ],
      ""Effect"": ""Allow"",
      ""Resource"": ""arn:aws:s3:::ciro-platzi-123/*"",
      ""Principal"": ""*""
    }
  ]
}
```

Nos dirigimos a la parte de **Permisos del bucket** -> **Política del bucket**. Hacemos click en **editar, pegamos el código JSON** generado por la herramienta, y **guardamos cambios.**

Si hiciste todo bien, te debería salir ““**Accesible públicamente**”” justo debajo del nombre de tu bucket.



## Base de datos de AWS

### Bases de datos relacionales

Los servicios de [bases de datos relacionales](https://ayudaleyprotecciondatos.es/bases-de-datos/relacional/) en AWS son:

- **Amazon Aurora**: base de datos relacional compatible con [MySQL](https://platzi.com/cursos/sql-mysql/) y [PostgreSQL](https://platzi.com/cursos/postgresql/) creada para la nube.
    
- **Amazon Relational Database Service (Amazon RDS)**: servicio de bases de datos relacionales administrado para MySQL, PostgreSQL, MariaDB, Oracle BYOL o SQL Server. Facilita la configuración, el uso y el escalado de varios motores de bases de datos.
    
- **Amazon Redshift**: ideal para analítica. Usa SQL para analizar datos estructurados y semiestructurados en almacenamientos de datos, bases de datos operativas y lagos de datos, con _hardware_ y _machine learning_ diseñados por AWS para ofrecer rendimiento al mejor precio a cualquier escala. A propósito, Platzi tiene un curso de [Redshift](https://platzi.com/cursos/redshift-big-data/)
    

### Bases de datos clave-valor

**Amazon DynamoDB** es una base de datos de documentos y valores clave que ofrece un rendimiento de milisegundos de un solo dígito a cualquier escala. **Está dirigida a aplicaciones de web de alto tráfico, sistemas de comercio electrónico y aplicaciones de juego.**

### Bases de datos en memoria

**Amazon ElastiCache** es un servicio de [almacenamiento de caché en memoria](https://aws.amazon.com/es/caching/?nc1=h_ls) completamente administrado que admite casos de uso flexibles y en tiempo real. Se usa para almacenar en caché administración de sesiones, tablas de clasificación de juegos y aplicaciones Geo-Espaciales. En ElastiCache encontramos **ElastiCache para Memcached** y **ElastiCache para Redis**.

### Bases de datos basadas en documentos

**Amazon DocumentDB** es un servicio de base de datos de larga duración, de alta disponibilidad, rápida, escalable y completamente administrado para operar cargas de trabajo de [MongoDB](https://platzi.com/cursos/mongodb/) esenciales. Entre sus casos de uso se encuentra la gestión de contenidos, catálogos y perfiles de usuario.

## RDS

Amazon RDS permite crear, ejercutar y ejecutar **bases de datos relacionales** en la nube. Las **bases de datos relacionales** son **aquellas en las que los datos almacenados poseen una relación entre sí.** Los datos se pueden consultar con un lenguaje de consulta llamado _SQL_.

En Amazon RDS puedes escoger entre 6 motores de bases de datos relacionales diferentes: MYSQL, MariaDB, PostgreSQL, Oracle, SQL Server y Amazon Aurora.

### Ventajas de Amazon RDS

Una de las ventajas de Amazon RDS es que facilita la configuración, siendo un servicio completamente administrando (PAAS). Además:

- RDS es **altamente escalable,** y puede ser usado en múltiple zonas de disponibilidad.
- **Permite crear réplicas de bases de datos** de solo lectura.
- RDS realiza **copias de seguridad automática,** y es **tolerante a fallos.**
- En RDS solo **pagas por lo que usas.**


## DynamoDB
**DynamoDB es una base de datos [NOSQL](https://www.mongodb.com/es/nosql-explained) de documentos clave-valor**, que ofrece un rendimiento en milisegundos de un solo dígito. Entre sus casos de uso tenemos manejo de datos actualizados en tiempo real.

Una **base de datos clave-valor** almacena datos en forma de claves y valores/atributos. En un documento de **Dynamo DB** podemos tener claves y una cantidad de atributos distinta para cada clave. Estos atributos también pueden ser de distintos tipos.

### Características de DynamoDB

**DynamoDB** es completamente administrado (PAAS). Funciona en múltiples regiones y **puede manejar hasta 20 millones de solicitudes por segundo.** Además, cuenta con **seguridad, respaldo y restauración** integrados.

## ElastiCache
**Amazon ElastiCache** es un servicio de almacenamiento en memoria 100% administrado que admite casos de uso flexibles y en tiempo real.

Es una **base de datos en memoria que almacena datos a los que se ha accedido previamente en [memoria caché](https://aws.amazon.com/es/caching/?nc1=h_ls),** para mejorar la rapidez de acceso a estos datos. Consultar datos en _caché_ siempre es más rápido que consultar directamente la base de datos.

Un ejemplo de uso es el de un sitio de noticias, al cual se accede miles de veces al día. Si los artículos se mantienen en una base de datos en memoria, se podrá acceder a estos mucho más rápido.

ElastiCache posee dos motores, [**Redis**](https://redis.io/) y [**Memcached**](https://memcached.org/). Ambos se monitorean a sí mismos continuamente, y pueden ser escalados hacia arriba o abajo en función de la demanda de la aplicación.
