# Qué son las redes
Las **redes** son cómo están conectadas las computadoras (y otros dispositivos tecnológicos) entre sí, y los servicios que permiten esto.

Una muy conocida es el Internet, que consiste en una red de computadoras abierta al mundo. Para que Internet funcione es necesario contar con direcciones IP, enrutadores, DNS y seguridad. AWS provee servicios que permiten la creación de redes y la entrega de contenido a los usuarios de manera rápida.

## Redes en la nube

Entre los servicios de AWS para implementar redes en la nube encontramos:

- **[Amazon Virtual Private Cloud (Amazon VPC)](https://platzi.com/clases/2733-aws-redes/48886-que-es-una-vpc/):** permite definir y aprovisionar una red privada para nuestros recursos de AWS
- **[AWS Transit Gateway](https://aws.amazon.com/transit-gateway/?whats-new-cards.sort-by=item.additionalFields.postDateTime&whats-new-cards.sort-order=desc):** Permite conectar VPC con los recursos locales (on-premises) mediante un _hub_ central
- [**AWS PrivateLink**](https://aws.amazon.com/privatelink/?privatelink-blogs.sort-by=item.additionalFields.createdDate&privatelink-blogs.sort-order=desc): proporciona conectividad privada entre las VPC y aplicaciones locales, sin exponer el tráfico al Internet público
- [**Amazon Route 53**](https://platzi.com/clases/2733-aws-redes/48888-route-53/): permite alojar nuestro propio DNS administrado

## Redes a escala

Estos servicios nos permiten escalar el tráfico de red según las necesidades:

- **Elastic Load Balancing**: permite distribuir automáticamente el tráfico de red a través de un grupo de recursos, con el fin de mejorar la escalabilidad
- **AWS Global Accelerator**: redirige el tráfico a través de la red global de AWS para mejorar el rendimiento de las aplicaciones globales
- **Amazon CloudFront**: entrega de forma segura datos, videos y aplicaciones a clientes de todo el mundo con baja latencia.



# Qué es una VPC
Una VPC es una red virtual privada. Cada computadora que está conectada a otra computadora por medio de un cable, enrutador o antena de wifi, requiere de una **interfaz de red** para ser conectada. La interfaz de red es el puente entre nuestra computadora y la tecnología ya utilizada para conectarse a la otra computadora.

Una vez que conectamos las computadoras, debemos configurar la red, para lo cual necesitamos un [rango de direcciones IP](https://platzi.com/clases/2225-redes/35586-clases-de-redes/).

## Qué es el rango de direcciones IP

El rango de direcciones IP es como una comunidad cerrada local, donde los equipos se podrán comunicar solo con otros equipos dentro de la misma red. A cada equipo se le asigna una dirección IPv4. Es decir, se le dan 4 números que varían del 0 al 255 separados por un punto. Para redes privadas ya se tienen especificados los rangos de IP:

- 10.0.0.1
- 172.16.0.1
- 192.168.0.1

## Para qué sirve Amazon VPC

Amazon VPC permite crear una red virtual para poder conectarnos a todos los servicios de AWS que existan en un rango de direcciones IP locales (por ejemplo, 10.0.0.0/24, que representa del rango de IP entre 10.0.0.0 y 10.0.0.255). Esta red virtual será como una pequeña comunidad cerrada para nuestras máquinas virtuales y todos los servicios que tengamos dentro de AWS.

### Componentes de Amazon VPC

Amazon VPC posee los siguientes componentes para controlar el tráfico interno y externo de nuestras VPC

- **Nat Gateway:** si deseamos que nuestras máquinas virtuales puedan acceder a internet, debemos utilizar este componente
- **Internet Gateway:** permite que Internet pueda acceder a nuestra instancia de EC2
- **ACL Control List:** controla el tráfico que vamos a permitir dentro y fuera de la VPC
# Escogiendo CloudFront

Antes de hablar de CloudFront, recordemos cómo funciona [AWS ElastiCache](https://platzi.com/clases/2732-aws-computo/47026-evaluando-elasticache/). **ElastiCache es un servicio que almacena en memoria caché las solicitudes a la base de datos, para evitar el consultar la base de datos cada vez que se necesite acceder a información.** Este servicio se ubica entre el sitio web y la base de datos

**CloudFront funciona de manera similar, solo que este es un servicio intermedio entre el navegador (o el cliente) y el sitio web**. El propósito de CloudFront es entregar datos, aplicaciones y sitios web en todos el mundo con baja latencia. Para esto, AWS cuenta con **edge locations** (o ubicaciones de borde), es decir, múltiples ubicaciones en el mundo desde las cuales CloudFront puede servir contenido.

## Casos de uso de CloudFront

Supongamos que un cliente accede a nuestro sitio web. En realidad, el cliente primero accede a CloudFront. Entonces CloudFront redirige automáticamente la solicitud de archivo desde el _edge location_ más cercano. Los archivos se almacenan en la caché de la ubicación de borde primero, durante un periodo de tiempo limitado que nosotros necesitemos.

Si un cliente solicita el contenido que está almacenado en caché por más tiempo que el vencimiento especificado, CloudFront verifica en el servidor de origen para ver si hay una nueva versión del archivo disponible. Si el archivo ha sido modificado, se retorna la nueva versión del archivo. En caso contrario, se entrega la versión que estaba en caché.

Cualquier cambio que realicemos en los archivos se replicará en las ubicaciones de borde a medida que sus visitantes están entrando y solicitando el contenido. Esto es lo que mantiene a los sitios web rápidos sin importar la ubicación del usuario.

### Características de CloudFront

- CloudFront es seguro: ofrece protección contra ataques DDOS, ya que los primeros servidores en recibir estos ataques serán los de CloudFront y no los tuyos. Además, CloudFront está protegido ante picos de tráfico.
- CloudFront también permite ejecutar funciones de [AWS Lambda](https://platzi.com/clases/2732-aws-computo/47016-aprendiendo-sobre-lambda/) en las ubicaciones de borde.
- CloudFront ofrece múltiples métricas en tiempo real, y es rentable.

# Qué es Route 53

[DNS](https://platzi.com/clases/2053-introweb/32966-dns/) es un sistema que asigna direcciones IP a nombres de dominio. **Route 53 es un servicio de alojamiento de DNS, que cuesta tan solo $0.5 por nombre de dominio por mes. Route 53 cuenta con distintas opciones de política de enrutamiento.**

## Políticas de enrutamiento

Las políticas de enrutamiento nos permiten determinar a dónde se dirigirá un usuario cuando acceda a nuestro dominio. Estas políticas son:

### Ruteo simple

El **ruteo simple** utiliza el servicio de DNS estándar. Es decir, el tráfico en un dominio se enruta hacia un recurso muy específico.

### Política ponderada

La **política ponderada** (o _weighted routing_) te permite asociar múltiples recursos con un solo nombre de dominio, y ver qué tanto tráfico es dirigido a cada recurso. Esto se determina con un número del 0 al 255, donde el cero representa que el recurso no recibe ningún tráfico, y el 255 indica que el recurso recibe todo el tráfico.

Mediante la política ponderada podemos probar distintas versiones de nuestro sitio web con un número reducido de usuarios. Luego podemos realizar una transición lenta de nuestros usuarios hacia la nueva versión del sitio.

### Política de geolocalización

Usando la **política de geolocalización** podemos escoger qué recursos servir en función de la ubicación geográfica de nuestros usuarios. Esto permite servir contenido específico según la región, así como restringir la distribución del mismo solo a las regiones permitidas.

### Política de latencia

La **política de latencia** se trata de entregar los recursos desde la región de AWS que esté más cercana a la ubicación del usuario, a fin de reducir el tiempo de respuesta.

### Política de conmutación por error

La **política de conmutación por error** redirige el tráfico a un recurso cuando este está en buen estado, o a uno diferente cuando el primer recurso no está en buen estado.

### Política de respuesta de múltiples valores

La **respuesta de múltiples valores** permite devolver varios valores, como direcciones IP a los servidores web, en respuesta a las consultas de DNS. Se pueden especificar varios valores para casi cualquier registro, pero este direccionamiento también permite verificar el estado de cada recurso, por lo que Route 53 devuelve los valores únicamente para los recursos en buen estado.

**Esta política no es sustituto de un balanceador de carga**, pero la capacidad de devolver varias direcciones IP (cuyo estado sea comprobable) permite usar el DNS para mejorar la disponibilidad y el equilibrio de la carga.

# Cómo crear el diagrama de una VPC

Aprendámos a crear los componentes básicos de una VPC desde cero. **Primero necesitamos hacer un diagrama para entender cómo están divididos estos componentes básicos.**

Para originar el diagrama nos dirigimos [a esta herramienta de diagramas de flujo](https://app.diagrams.net/) y escogemos dónde guardaremos el diagrama (en esta clase se escoge Google Drive, pero puedes guardarlo donde prefieras). Entonces le damos a _**“Create New Diagram”** -> **“Blank Diagram”**._

## Creando el diagrama de la VPC

En el recuadro de búsqueda podemos poner “AWS VPC”. Escogemos la siguiente figura.

![VPC shape](https://static.platzi.com/media/articlases/Images/2022-05-30.png)

Luego, buscamos las siguientes figuras: “AWS Internet Gateway”, “User”, “network access control”, “router” y “subnet”. Entonces las ordenamos de la siguiente manera  
![Diagrama de VPC](https://static.platzi.com/media/user_upload/AWS7-5047ce6b-0603-478d-9aa8-0ea37debb655.jpg)  
Este es el diagrama final. Muestra que cuando un usuario intenta acceder al VPC se encontrará con el [**Internet Gateway**](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html). Luego, el tráfico será dirigido al **router**, que se encargará de redirigirlo a una de las dos subnets las cuales contienen un **Network Access Control List.** Este se encargará de validar que el usuario pueda acceder al contenido.

# Cómo crear la VPC y el internet gateway

Una vez creado nuestro [diagrama de vpc](https://platzi.com/clases/2733-aws-redes/48889-crea-el-diagrama/), [iniciamos sesión en AWS](https://console.aws.amazon.com/console/home?nc2=h_ct&src=header-signin) para crear los primeros componentes de nuestra VPC.

## Pasos para crear la VPC

1. En la caja de búsqueda de AWS buscamos **VPC** y seleccionamos el primer resultado.
2. Nos dirigimos a **“Sus VPC”** y le damos a **“Crear VPC”**.
3. Colocamos las siguientes opciones, y dejamos el resto de valores por defecto:

- **Etiqueta de nombre - opcional**: DemoVPCLaboratorio.
- **Bloque de CIDR IPv4**: Entrada manual de CIDR IPv4.
- **CIDR IPv4**: 10.0.0.0/24.  
    ![Configuración de la VPC](https://static.platzi.com/media/articlases/Images/2022-05-30%20%281%29.png)

Entonces le damos a **Crear VPC**.

## Pasos para crear el Internet Gateway

1. Nos dirigimos a **“Gateways de Internet”** -> **“Crear gateway de Internet”**.
2. En **“Etiqueta de nombre”**, colocamos **“DemoIGWLaboratorio”**, y le damos a **“Crear gateway de Internet”**.
3. Nos aparecerá nuestro nuevo Internet Gateway con un estado “Detached”, ya que no está ligado a ninguna VPC.
4. Para conectar el Intenet Gateway a nuestra VPC, simplemente le damos clic en **“Acciones”** -> **“Conectar a la VPC”**.
5. Aquí seleccionamos nuestra VPC, y le damos clic a **“Concetar gateway de Internet”**. Ojo, **el Internet Gatway y la VPC deben estar en la misma región**.

Ya con esto creamos dos de los componentes de nuestra VPC.

# Cómo crear la tabla de enrutamiento y otros componentes

Una vez que [creamos nuestra VPC y el Internet Gateway y los conectamos](https://platzi.com/clases/2733-aws-redes/49130-crear-la-vpc-y-crear-el-internet-gateway/), procedemos a crear la **tabla de enrutamiento**, las **listas de acceso de control** y las **subredes**.

## Pasos para crear la tabla de enrutamiento

1. Desde la [página del servicio de VPC](https://console.aws.amazon.com/vpc/home), nos dirigimos a **“Tablas de ruteo”**.
2. Notamos que ya existe una tabla de ruteo asociada a nuestra VPC, que se creó automáticamente junto con la VPC.
3. La seleccionamos, nos dirigimos a la sección de rutas, y hacemos clic en **“Editar rutas”**.  
    ![Editar rutas](https://static.platzi.com/media/articlases/Images/2022-05-31.png)
4. Hacemos clic en **“Agregar ruta”**, colocamos **0.0.0.0/0** y **“Puerta de enlace de internet”**, y seleccionamos el [Internet Gateway](https://platzi.com/clases/2733-aws-redes/49130-crear-la-vpc-y-crear-el-internet-gateway/) que creamos en la clase pasada.
5. Le damos en **“Guardar cambios”**. De esta manera, todo el mundo podrá acceder a nuestra VPC mediante el Internet Gateway.  
    ![Agregar ruta](https://static.platzi.com/media/articlases/Images/2022-05-31%20%281%29.png)

## Pasos para crear Access Control List

1. En el apartado de **“Seguridad”** del servicio de VPC, nos dirigimos a **“_ACL_ de red”**.
2. Le damos clic a **“Crear _ACL_ de red”**. Crearemos dos _ACL_ de red, uno para cada subred. Le damos los nombres _NACLA_ y **NACLB**, y en VPC escogemos nuestra VPC.
3. Le damos clic en **“Crear _ACL_ de red”**.  
    ![Crear ACL de red](https://static.platzi.com/media/articlases/Images/2022-05-31%20%282%29.png)

### Pasos para añadir una regla de entrada y una de salida

Ahora, para cada _ACL_ de red creado debemos añadir una regla de entrada y una de salida, con el fin de permitir el tráfico HTTP en el puerto 80. Para esto:

1. Seleccionamos una _ACL_ de red
2. Nos vamos a **“Reglas de entrada”** -> **“Editar reglas de entrada”**.  
    ![Editar reglas de entrada](https://static.platzi.com/media/articlases/Images/2022-05-31%20%283%29.png)
3. Le damos clic en **“Añadir una nueva regla”**. Y colocamos los siguientes parámetros

- **Número de regla**: 100 (las reglas se evalúan comenzando por la regla de número más bajo).
- **Tipo**: HTTP (80).
- **Origen**: 0.0.0.0/0.
- **Permitir/denegar**: Permitir.

4. Le damos a **“Guardar cambios”**.
5. Repetimos el proceso con la regla de salida y con el otro _ACL_ (_NACLB_), colocando los mismos parámetros anteriores. Ahora solo falta añadir estos _ACL_ a nuestras subredes, las cuales crearemos a continuación.

![Añadir una nueva regla de entrada](https://static.platzi.com/media/articlases/Images/2022-05-31%20%285%29.png)

## Pasos para crear subredes

1. En la sección de **“Subredes”** vamos al botón **“Crear subred”**.
2. Escogemos nuestra VPC, y colocamos los siguientes parámetros:

- **Nombre de la subred:** DemoSubredA.
- **Zona de dispinibilidad:** la primera que te aparezca en el menú de selección, que termine en “a”.
- **Bloque de CIDR IPv4:** 10.0.0.0/25 (asumiendo que tu VPC tiene el bloque de CIDR 10.0.0.0/24)

3. Le damos clic en **“Crear subred”**
4. Repetimos el procedimiento para la otra subred con los siguientes parámetros:

- **Nombre de la subred:** DemoSubredB.
- **Zona de dispinibilidad:** la segunda que te aparezca en el menú de selección, que termine en “b”.
- **Bloque de CIDR IPv4:** 10.0.0.128/25.

![Crear subred](https://static.platzi.com/media/articlases/Images/2022-05-31%20%286%29.png)

Ahora solo falta **asociar los _ACL_ que creamos con las subredes**. Para esto simplemente hacemos clic derecho en _DemoSubredA_ y clic en **“Editar la asociación de ACL de red”**, y seleccionamos la _ACL_ correspondiente (_NACLA_). Entonces le damos en Guardar, y repetimos el procedimiento con _DemoSubredB_.

# Administración y gobernanza con AWS

En el pasado, las empresas u organizaciones tenían que lograr un equilibrio entre innovar y mantener un control de los costos, la seguridad y el cumplimiento. Los servicios de administración y gobernanza de AWS sirven para simplificar este equilibrio. Estos servicios buscan que la administración de AWS sea lo más fácil y optimizada posible.

## Administración de cuentas

Entre los servicios que nos ayudan a administrar nuestras cuentas de AWS tenemos:

- **AWS Control Tower**: una manera fácil de configurar y gobernar un entorno seguro de AWS de múltiples cuentas
- **AWS Organizations**: nos brinda una forma de gobernar, de administrar de manera centralizada nuestros entornos en varias cuentas de AWS
- **AWS Budgets**: nos ayuda a planificar y realizar control de costos

## Servicios de aprovisionamiento

Estos servicios facilitan el aprovisionamiento o la creación y configuración de nuevos recursos de AWS:

- **AWS CloudFormation**: permite modelar y aprovisionar todos sus recursos mediante código
- **AWS OpsWorks**: ayuda a automatizar todas las operaciones con _Chef_ y _Puppet_
- **AWS Service Catalog**: un servicio para crear, organizar y gobernar nuestro propio catálogo curado de productos de AWS en toda nuestra organización
- **Marketplace**: es donde vamos a poder encontrar, probar e implementar software que se ejecuta en AWS

## Servicios para operar el entorno AWS

Estos servicios nos ayudan a operar nuestro entorno de AWS

- **Amazon CloudWatch**: permite observar nuestros servicios a través de métricas y registros
- **Amazon Config**: permite registrar y evaluar las configuraciones de nuestros recursos en AWS
- **AWS CloudTrail**: rastrea toda la actividad del usuario de la cuenta de AWS. Esto es importante en investigaciones de seguridad
- **Systems Manager**: optimiza el rendimiento y la seguridad mientras administramos una gran cantidad de sistemas
- **Amazon X-Ray**: analiza y depura aplicaciones en producción

# Qué es CloudFormation y cuáles son sus beneficios

**CloudFormation** es un servicio que permite provisionar servicios como máquinas virtuales o _VPC_s mediante código. Para esto se usan las _CloudFormation Templates_, que son plantillas en donde especificamos los recursos que queremos desplegar. Estas plantillas pueden estar en formato _JSON_ o _YAML_, y en ellas se define un [_stack_](https://docs.aws.amazon.com/es_es/AWSCloudFormation/latest/UserGuide/stacks.html) o pila de recursos a provisionar.

## Beneficios de CloudFormation

¿Por qué es útil desplegar infraestructura y recursos basados en una plantilla de CloudFormation? Porque ofrece las siguientes ventajas.

### Control de versiones

Ya que podemos definir los recursos que queremos desplegar mediante código, este código lo podemos mantener en un sistema de control de versiones como Git y GitHub. **Esto permite tener un historial completo de nuestros recursos en un solo archivo, así como la colaboración en el despliegue de la infraestructura**.

### Automatización

CloudFormation permite a los encargados de [DevOps](https://platzi.com/clases/1526-gitlab/19272-que-es-devops/) automatizar la creación de infraestructura y recursos en AWS.

### Escala

Gracias a las plantillas podemos replicar la infraestructura en distintas cuentas de AWS y en distintas regiones. Solo debemos ajustar ciertos parámetros.
# Qué es Cloudwatch

**CloudWatch es un servicio de supervision y observabilidad para _AWS_. Está diseñado para que podamos ver todo lo que sucede dentro de nuestra cuenta de _AWS_**. En este sentido, CloudWatch ofrece la posibilidad de:

- Recopilar métricas o datos de sus servicios
- Integrar con unos 80 servicios de AWS
- Tener métricas predefinidas
- Recopilar y desplegar datos en una vista unificada con distintos gráficos.
- Configurar de alarmas de acuerdo a los graficos que nos muestre cloudWaatch
- Enviar archivos de registro y buscar de forma interactiva datos de registros. Posee un almacén de registros centralizado. Esto nos ayuda a encontrar y resolver problemas de manera eficaz.

## Caso de uso de CloudWatch

Imagínate que tienes una máquina virtual a la cual se accede mediante SSH. Si queremos saber cuando alguien intenta piratear nuestra máquina virtual con SSH, **podemos enviar los _logs_ de inicio de sesión a CloudWatch**.

Mediante CloudWatch, **podemos usar un filtro para visualizar el número de intentos de sesión fallidos**. Además, podemos configurar una alerta en el caso de que los intentos fallidos superen cierto límite en un periodo específico de tiempo.
# Cómo aplicar autoescalamiento

El auto escalamiento (_autoscaling_) nos permite escalar la capacidad de nuestras instancias de máquinas virtuales automáticamente, de acuerdo con nuestras condiciones definidas.

**Podemos aumentar la cantidad de instancias que tenemos en ejecución durante los picos de demanda y disminuirlos cuando no los necesitemos**. Esto trae una alta disponibilidad, tolerancia a fallos y un ahorro de costos.

## Pasos para aplicar autoescalamiento

1. Para aprovechar el autoescalamiento, debemos crear un **grupo de auto escalamiento** que asocie nuestras instancias.
2. En este grupo especificaremos un tamaño mínimo (el número mínimo de instancias a correr), y una capacidad deseada (el número óptimo de instancias en función de las necesidades).
3. Entonces se agregarán más instancias según sea necesario hasta alcanzar un máximo.

> Cabe destacar que el Load Balancer de _AWS_ es lo que permite distribuir automaticamente las conexiones a medida que aparecen y desaparecen estos servidores.

Nota: EC2 no es el único servicio que tiene auto escalamiento. DynamoDB y Aurora también implementan este concepto.
# Laboratorio: empezando con CloudFormation

CloudFormation nos permite provisionar infraestructura como código. Para poner a prueba CloudFormation, mediante una plantilla **vamos a crear un _stack_ a partir del cual se desplegará un bucket de [S3](https://platzi.com/clases/2732-aws-computo/47018-s3-y-s3-glacier/)**. Luego, actualizaremos el _stack_ añadiendo otro bucket de S3, y finalmente lo eliminaremos.  
![Diagrama de stack de CloudFormation](https://static.platzi.com/media/articlases/Images/Screenshot%20at%202022-06-03%2015-03-58.png)

## Entendiendo la plantilla

En [este repositorio](https://github.com/platzi/aws-cloud-practitioner/tree/main/lab-cloudformation) encontrarás la plantilla de CloudFormation que usaremos. La plantilla tiene la siguiente estructura JSON (recuerda, CloudFormation acepta formato JSON o YAML):

```json
{
  "AWSTemplateFormatVersion": "2010-09-09",
  "Description": "this template does XXXX",
  "Metadata": {},
  "Parameters": {},
  "Mappings": {},
  "Conditions": {},
  "Transform": {},
  "Resources": {},
  "Outputs": {}
}
```

Estos parámetros corresponden a lo siguiente:

- **AWSTemplateFormatVersion**: este parámetro es opcional. Aquí especificamos la versión de la plantilla
- **Description**: cadena de texto que describe la plantilla. Debe ir después de _AWSTemplateFormatVersion_
- **Metadata**: objetos que proporcionan información adicional sobre la plantilla
- **Parameters**: valores que pasaremos a la plantilla al ejecutarse, ya sea durante la creación o actualización del *stack
- **Mappings**: permite asignar un conjunto de valores a una clave específica. Por ejemplo, para establecer valores en función de una región, podemos crear un _mapping_ que usa el nombre de una región como clave y contiene los valores que deseemos especificar para cada región
- **Conditions**: controla que se creen recursos o se asignen valores a dichos recursos en función de una condición. Por ejemplo, podemos asignar valores distintos para entornos de producción o de prueba
- **Transform**: especifica las [macros](https://docs.aws.amazon.com/es_es/AWSCloudFormation/latest/UserGuide/template-macros.html) que AWS CloudFormation usa para procesar la plantilla
- **Resources**: aquí se declaran los recursos a incluir en el _stack_. Por ejemplo, instancias EC2 o _buckets_ de S3.
- **Outputs**: declara valores de salida que pueden ser usados en otros _stacks_

## Pasos para crear el stack

1. Nos dirigimos a la [página de CloudFormation](https://console.aws.amazon.com/cloudformation/home) desde nuestra cuenta de AWS (en esta página podremos conocer más sobre el servicio en cuestión).
2. Aquí le damos a **“Crear stack”**.
3. Para crear el stack, en “Especificar plantilla” seleccionamos **“Cargar un archivo de plantilla”**, y cargamos el archivo [createstack.json](https://github.com/platzi/aws-cloud-practitioner/blob/main/lab-cloudformation/createstack.json). Este archivo simplemente define un _bucket_ de S3 llamado “platzilab”.

```json
{
  "Resources": {
    "platzilab": {
      "Type": "AWS::S3::Bucket"
    }
  }
}
```

![Subir plantilla](https://static.platzi.com/media/articlases/Images/Screenshot%20at%202022-06-03%2016-10-52.png)  
4. Le damos clic a siguiente y, a continuación, escogemos un nombre para el _stack_ o pila. En este caso, la llamamos **cfnlab**, y le damos a siguiente.  
5. Opcionalmente, podemos añadir etiquetas para identificar la pila, y un rol de IAM.  
6. Dejamos el resto de configuraciones por defecto y le damos a siguiente. Entonces nos llevará a revisar las configuraciones, y le damos a **“Crear pila”**.  
7. Podremos ver el proceso de creación de la pila, los eventos y los recursos que fueron creados. Si te fijas en el nombre del bucket creado, **verás que este está compuesto por el nombre de la pila, el nombre que le asignamos al bucket en la plantilla, y una cadena de texto aleatoria**. Esto es para evitar crear recursos con nombre duplicados.
![Pila y bucket creados](https://static.platzi.com/media/articlases/Images/Screenshot%20at%202022-06-03%2016-23-28.png)
# Laboratorio: actualizando y eliminando la stack

Ahora que creamos nuestra pila de CloudFormation, procederemos a actualizarla añadiendo otro _bucket_ de S3. Después, veremos cómo eliminar la pila.

## Pasos para actualizar la pila

1. Para actualizar la pila primero usaremos el archivo [updatestack1.json](https://github.com/platzi/aws-cloud-practitioner/blob/main/lab-cloudformation/updatestack1.json). El contenido de este archivo es el siguiente:

```json
{
  "Resources": {
    "platzilab": {
      "Type": "AWS::S3::Bucket"
    },
    "platzilabalexis": {
      "Type": "AWS::S3::Bucket"
    }
  }
}
```

Como podrás notar, definimos el mismo _bucket_ que en la clase anterior, más un nuevo _bucket_ con ID lógico “platzilabelalexis”.

2. Ahora, en la página de CloudFormation, escogemos la pila que creamos y le damos a **“Actualizar”**.  
    ![Escoger la pila](https://static.platzi.com/media/articlases/Images/Screenshot%20at%202022-06-04%2010-29-03.png)
    
3. En “Preparar la plantilla” escogemos **“Reemplazar la plantilla actual”** y cargamos el archivo **updatestack1.json**.
    
4. Le damos a Siguiente tres veces, y notamos que en “Vista previa del conjunto de cambios” nos muestra que solo va a añadir un nuevo _bucket_ de S3, **puesto que el _bucket_ con ID lógico “platzilab” ya existe**. Entonces le damos a **“Actualizar pila”**.
    

![Vista previa de cambios](https://static.platzi.com/media/articlases/Images/Screenshot%20at%202022-06-04%2010-36-32.png)

Si nos vamos a ver nuestros _buckets_ de S3, encontraremos que se ha creado uno nuevo cuyo nombre incluye “platzilabalexis”.

### Crear una pila con un nombre de _bucket_ explícito

Podemos crear otra pila dándole un nombre explícito a los _buckets_ que queremos provisionar. Para ello, usemos el archivo [updatestack2.json](https://github.com/platzi/aws-cloud-practitioner/blob/main/lab-cloudformation/updatestack2.json).

```
{
  "Resources": {
    "platzilab": {
      "Type": "AWS::S3::Bucket",
      "Properties": {
        "BucketName": "mibucket123"
      }
    },
    "platzilabalexis  ": {
      "Type": "AWS::S3::Bucket"
    }
  }
}
```

Nota que en este caso el _bucket_ con ID lógico “platzilab” tiene en sus propiedades el nombre de bucket “mibucket123”. Este nombre debe ser único en todo _AWS_. **Si intentamos crear la pila con un _bucket_ con nombre repetido, tendremos un error y no se creará la pila**.

## Cómo eliminar las pilas

Para ello simplemente seleccionamos una pila y le damos a **“Eliminar”**. Nos va a pedir confirmación, entonces le damos a **“Eliminar pila”**. Repetimos el proceso para todas las pilas. Si exploramos nuestros buckets de S3, veremos que ya no están los que creamos con CloudFormation.
# Empezando con Machine Learning

**El _machine learning_ es un tipo de inteligencia artificial donde podemos escribir programas que aprenden de los datos que se le proporcionan**, y “recuerdan” los resultados de procesar estos datos. Un programa de _machine learning_ aprende al ejecutarse una y otra vez. Esta clase de programas tienen usos en distintas industrias:

- Automóviles automáticos
- Relojes Inteligentes
- Agricultura
- Perfil Financiero
- Correos electrónicos

## Servicios de inteligencia artificial en AWS

Entre los servicios de AWS que usan inteligencia artificial o _machine learning_ encontramos:

- **Amazon Kendra**: provee un sistema de búsqueda inteligente a nuestros clientes
- **Amazon Personalize**: brinda recomendaciones personalizadas a nuestros clientes

### Servicios de analisis de métricas comerciales

- **Amazon Lookout for metrics**: detecta automáticamente cambios inesperados en aspectos como el rendimiento de los ingresos y la retención de los clientes, ayudándonos a identificar la causas
- **Amazon Forecast**: nos ayuda a crear modelos de pronósticos precisos
- **Amazon Fraud Detector**: identifica actividades en línea potencialmente fraudulentas

### Servicios de visión artificial

**Amazon Rekognition permite analizar imágenes, videos y extraer el significado de estos**. Es uno de los servicios más populares de AWS en cuanto a inteligencia artificial.

### Servicios de idiomas

- **Amazon Polly**: ayuda a convertir el texto en un habla realista
- **Amazon Transcribe**: permite agregar traducciones de voz a texto de calidad
- **Amazon Lex**: permite generar agentes conversacionales o bots de chat
# Qué es AWS Rekognition

_Amazon _Rekognition__ es un servicio que nos permite analizar imágenes y videos mediante aprendizaje automático. Para ello, le pasamos una imagen al servicio, y nos devuelve una lista de elementos que puede contener esa imagen, junto con un porcentaje de confianza para cada elemento.  
![Imagen analizada por Rekognition](https://static.platzi.com/media/articlases/Images/2022-06-06.png)

Un caso de uso de _Rekognition_ es para detectar imágenes con contenido para adultos o violento, a fin de moderar lo que se sube en alguna plataforma.

## Explorando _Rekognition_

Iniciamos sesión en _AWS_ y nos dirigimos a la [página de _Rekognition_](https://console.aws.amazon.com/rekognition/home). En la parte de _Demos_, escogemos **“Celebrity recognition”**. Nos encontraremos una imagen de Jeff Bezos junto a un porcentaje de confianza.

Podemos subir la imagen de cualquier celebridad y obtendremos un porcentaje de confianza. Probemos con una imagen de los 3 _Spider-Man_ (Tom Holland, Andrew Garfield y Tobey Maguire). Para ello simplemente le damos a **“Upload”** y escogemos la imagen.  
![Reconocimiento de los 3 spiderman](https://static.platzi.com/media/articlases/Images/2022-06-06%20%281%29.png).

Como se puede apreciar, _Rekognition_ reconoce a los tres actores con un porcentaje de confianza.

Cabe destacar que _Rekognition_ también nos retorna un objeto _Response_, el cual contiene distintas características de la imagen, como la posición de los actores, e incluso un estimado de cuál sentimiento expresan sus caras.
# Amazon Polly

**Amazon Polly nos permite generar discursos realistas a partir de texto**. Exploremos cómo podemos usar Amazon Polly.

## Explorando Amazon Polly

Nos dirigimos a la [página del servicio de Polly](https://console.aws.amazon.com/polly/home), y le damos clic a **“Pruebe Polly”**. Aquí tenemos distintas opciones de idioma, dialectos y voces, en función del motor que escojamos.

**Podemos escoger un motor neural o estándar**. El motor neural produce el habla más similar a la humana posible, mientras que el estándar solo provee voz con un sonido natural, pero nos da más opciones de voces.

Una vez que escojamos el motor, idioma y voz, podemos probar Polly introduciendo un texto y dándole a **“Escuchar”**.

![Probando Polly](https://static.platzi.com/media/articlases/Images/2022-06-07.png)

Cabe destacar que podemos guardar el resultado en un _bucket_ de S3. Además, podemos personalizar el formato de archivo a guardar y la pronunciación, esto en “Configuración adicional”.

# Amazon Transcribe
**Amazon Transcribe permite crear transcripciones de voz a texto de calidad para un amplio abanico de casos de uso** (por ejemplo, accesibilidad). Exploremos cómo podemos usar Amazon Transcribe.

## Explorando Amazon Transcribe

En la [página del servicio de Amazon Transcribe](https://console.aws.amazon.com/transcribe/home) podemos explorar sus opciones y casos de uso. También podemos poner a prueba el servicio haciendo clic en **“Create a transcript”**.

A continuación, escogemos el lenguaje y presionamos en **“Start streaming”**. El navegador nos va a pedir permiso para usar el micrófono. Una vez que otorgamos el permiso, podemos comenzar a hablar y veremos como nuestro discurso se transcribe en tiempo real. Para detener la transcripción, simplemente le damos a **“Stop streaming”**.  
![Prueba de Amazon Transcribe](https://static.platzi.com/media/articlases/Images/2022-06-07%20%281%29.png)

