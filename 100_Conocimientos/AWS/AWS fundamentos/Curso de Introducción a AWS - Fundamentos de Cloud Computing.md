## TI tradicionales
### ¿Cómo funciona un sitio web?

Se tiene un #cliente que se conecta a una #red o #network y redirige la petición a un #servidor 

### ¿Qué esta compuesto un servidor?

- **Computo y memoria**: Un servidor está compuesto por una CPU y una memoria RAM que funciona como el cerebro.
- Almacenamiento: que donde se almacena los datos.
- **Base de datos**: que son datos ordenados de forma estructurada.
- **Redes**: que son los routers, switches, y DNS
	- **Redes**: cables, routers y servidores conectados unos a otros.
	- **Router**: un dispositivo de red que reenvía paquetes de datos entre redes informáticas.
	- **Switch**: toma un paquete y lo envía al servidor/cliente correcto en la red.

## ¿Qué es la computación en la nube?

> La computación en la nube es la **entrega bajo demanda** de computación, almacenamiento de bases de datos, aplicaciones y otros recursos de TI a través de una plataforma de servicios en la nube por medio de Internet con precios de **pago por uso**.

- Suministras el **tipo y tamaño exactamente correctos** de los recursos informáticos que necesitas.
- Puedes acceder **al instante** a todos los recursos que necesitas.
- Una **forma sencilla de acceder** a servidores, almacenamiento, bases de datos y un conjunto de servicios de aplicaciones: poder de computo, almacenamiento y bases de datos.

### Servicios que ya has usado en la nube

- **Gmail** Servicio de email en la nube. Pagas solo por tus emails almacenados (no infraestructura)
- **Dropbox** Servicio de almacenamiento en la nube. Originalmente se construyó en AWS
- **Netflix** Servicio de video en demanda. Construido en AWS.

### Tipos de modelos de computación en la nube

#### Nube Privada

- Servicios de nube usados por una organización (no está expuesta al público).
- Control total.
- Seguridad para aplicaciones sensibles.
- Satisface necesidades comerciales específicas.

#### Nube Pública

- Recursos propios en la nube y operados por proveedores de nube de terceros a través de internet.
- Seis ventajas del cómputo en la nube.
- Google Cloud Platform (GCP), Azure, AWS

#### Nube Híbrida

- Mantener algunos servidores en las instalaciones y extender otras capacidades en la nube.
- Control sobre activos sensibles en tu infraestructura privada
- Flexibilidad y rentabilidad de la nube pública.

#### 5 características de la computación en la nube

1. Autoservicio en demanda
2. Amplio acceso a la red
3. Múltiples inquilinos y agrupación de recursos
4. Elasticidad y escalabilidad
5. Servicio medido

#### 6 ventajas de la computación en la nube

1. Gastos de capital comercial (**capex**) sobre gastos operativos (**opex**)
2. Economías de escala
3. Dejar de adivinar la capacidad
4. Incrementar la velocidad y la agilidad
5. Dejar de gastar dinero en la ejecución
6. Globalizar en minutos

#### Problemas resueltos por la nuble

- Flexibilidad: cambia los tipos de recursos cuando sea necesario
- Rentabilidad: pagar sobre la marcha por lo que se usa
- Escalabilidad: acomodar cargas grandes al hacer que el hardware sea más fuerte o agregando nodos adicionales
- Elasticidad: capacidad de escalar cuando sea necesario
- Alta disponibilidad y tolerancia a fallos, crecer en todos los centros de datos
- Agilidad: desarrollar, probar y ejecutar rápidamente aplicaciones en la nube



## Tipos de computo en la nube

### IaaS: Infraestructura como Servicio
- Azure
- Linode
- Digital ocean
- S2 AWS

>La infraestructura como servicio (IAAS) proporciona componentes básicos de IT en la nube, es decir, **redes, computación, almacenamiento, etc.** A su vez, provee el máximo nivel de flexibilidad para adaptarlo a tus necesidades.
### PaaS: plataforma como Servicio
- Heroku
- Google App Engine
- AWS Elastic Beanstalk

>Los modelos que ofrecen una plataforma como servicio (PAAS) eliminan la necesidad de que administremos la infraestructura y proveen una plataforma para gestionar aplicaciones.
### SaaS: Software como servicio
- Amazon Rekognition
- Dropbox
- Zoom
- Gmail

>El Software como servicio (SAAS) brinda un producto de software terminado que es ejecutado y administrado por el proveedor del servicio.

### On -premises
>On-premises se refiere a una forma tradicional de cómputo en la cual nos encargamos de gestionar nuestra propia infraestructura.

### Responsabilidades según el tipo de cómputo

En la siguiente tabla se muestra qué componentes de IT están administrados según el tipo de cómputo en la nube. “Sí” indica que el componente está administrado por el proveedor de nube, “No” indica que nosotros somos responsables del componente.

| Componente     | On-premises | IAAS | PAAS | SAAS |
| -------------- | ----------- | ---- | ---- | ---- |
| Aplicaciones   | No          | No   | No   | Sí   |
| Data           | No          | No   | No   | Sí   |
| Runtime        | No          | No   | Sí   | Sí   |
| Middleware     | No          | No   | Sí   | Sí   |
| O/S            | No          | No   | Sí   | Sí   |
| Virtualización | No          | Sí   | Sí   | Sí   |
| Servidores     | No          | Sí   | Sí   | Sí   |
| Almacenamiento | No          | Sí   | Sí   | Sí   |
| Redes          | No          | Sí   | Sí   | Sí   |


## Cómo escoger una región de AWS

Podemos escoger la región de nuestra aplicación basada en distintos aspectos que son.

- El cumplimiento de los requisitos legales y de gobernanza de datos, pues los datos nunca abandonan una región sin su permiso explícito
- La proximidad con los clientes porque lanzan en una región cercana en donde estén para reducir latencia. Puedes revisar esta característica desde tu ubicación a cada región en [cloudping.info](https://www.cloudping.info/).
- Los servicios disponibles dentro de una región debido a que muchos no funcionan en todas partes. Algunos servicios globales o regionales son…
    
    - **Globales**
        - IAM
        - Route 53
        - Cloudfront
        - WAF
    - **Regionales**
        - EC2
        - Beanstalk
        - Lambda
        - Rekognition
### Modelo de responsabilidad compartida

Ahora es crucial determinar las responsabilidades de AWS y del cliente dentro del servicio tecnológico que ofrece la compañía.

**AWS se hace responsable de:**

- Hardware y la infraestructura global
- Regiones
- Zonas de disponibilidad
- Ubicaciones de AWS Edge / puntos de presencia
- Software
- Cómputo
- Almacenamiento
- Bases de datos
- Redes

**El cliente se responsabiliza de:**

- Actualizaciones de S.O.
- Protección de los datos que se almacenan
- Manejo de aplicaciones
- Accesos
- Administración de usuarios y grupos



## Servicios de protección
### Servicios de protección de datos

estos son algunos servicios de protección de AWS y sus funciones para mover nuestras plataformas en la nube:

- **Amazon Macie:** descubre y protege datos sensibles
- **AWS Key Management Service:** almacena y administra claves de cifrado
- **AWS CloudHSM:** proporciona almacenamiento de claves basado en hardware
- **AWS Certificate Manager:** provee, administra e implementa certificados SSL/TLS
- **AWS Secrets Manager:** traslada, gestiona y recupera datos (contraseñas, por ejemplo)

### Servicios de protección de la infraestructura

Es fundamental que cuides de la infraestructura de tu sitio web y AWS ofrece los siguientes servicios de seguridad:

- **AWS Shield:** protege contra ataques de Denegación de Servicio (DDOS)
- **AWS Web Aplication Firewall (WAF):** filtra el tráfico de sitios web maliciosos
- **AWS Firewall Manager:** administra las reglas del firewall de forma centralizada

### Servicios de detección de amenazas

En todo momento nuestra plataforma está expuesta a grandes amenazas y por eso AWS desarrolló los siguientes servicios:

- **Amazon GuarDuty:** detecta automáticamente las amenazas
- **Amazon Inspector:** analiza la seguridad de la aplicación
- **Amazon Config:** registra y evalúa configuraciones de nuestros recursos
- **Amazon CloudTrail:** rastrea la actividad del usuario y el uso de las API que ocupamos en nuestra cuenta.

### Servicios de gestión de identidad

Por último, existen distintas herramientas de gestión de identidad que provee AWS:

- **AWS Identity and Access Management (IAM):** administra de forma segura el acceso a una cuenta, servicios y recursos
- **AWS Inicio de sesión único:** implementa el inicio de sesión único (Single Sign On/SSO)
- **Amazon Cognito:** permite a los usuarios administrar la identidad dentro de las aplicaciones
- **AWS Servicio de Directorio:** implementa y administra un Active Directory service
- **AWS Organizaciones:** funciona para gobernar y administrar de distintas cuentas de AWS de forma centralizada



## Identity and Access Management (IAM) 
Es un servicio gratuito que nos ayuda a administrar los accesos a los servicios y recursos de tu cuenta en AWS. A su vez, puedes crear usuarios, grupos y establecer permisos de acceso a los recursos mediante el uso de políticas.

### **Usuarios y grupos de usuarios de IAM**

Los usuarios y grupos de usuarios son de los principales componentes de IAM. Al crear tu cuenta de AWS te proporcionan un **usuario Root** que tiene acceso a todos los recursos,

Este usuario puede generar otros perfiles y cada uno con un acceso único a distintos recursos de AWS. Además, Root también puede configurar grupos de usuarios, donde cada miembro tiene y puede compartir permisos de acceso.

### **Ejemplos de políticas de IAM**

El acceso a recursos se otorga mediante políticas. Este es un ejemplo de una política que otorga acceso de administrador.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "*",
            "Resource": "*"
        }
    ]
}
```

También está este ejemplo de políticas de acceso a un bucket de S3 (almacenamiento)

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "s3:ListBucket"
            ],
            "Resource": "arn:aws:53 ::: bucket-name"
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3: GetObject",
                "s3: PutObject",
            ],
            "Resource": "arn:aws:53 ::: bucket-name /*"
        }
    ]
}
```

### **IAM Roles**

Además de todas estas funciones, **IAM de AWS** permite asumir roles y otorgar permisos a otras tecnologías. Por ejemplo, podemos conceder a una máquina virtual el acceso a una base de datos mediante un rol de IAM.
