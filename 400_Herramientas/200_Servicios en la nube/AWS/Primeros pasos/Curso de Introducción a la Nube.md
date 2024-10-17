# **Componentes de la arquitectura agnóstica (distribuida en al menos 2 zonas de disponibilidad):**

**DNS (platziwallet com):** nombre de dominio. Donde llegan todos los usuarios. Reglas de enrutamiento para el dominio¿ Cómo administro el dominio? ¿Dónde va a estar? ¿Lo voy a tener en el CP o en GoDaddy?

**CDN(Content Delivery Network)**: Recibe el tráfico. Puede tener reglas de direccionamiento basado en ciertos criterios y según el origen de los requests. TIene certificado de seguridad (HTTPS) ¿Que CDN voy a utilizar?Cloudflare, Akamai, CloudFront, entre otros.

**WAF (Web Application Firewall):** Para seguridad y protección. Reglas de denegación de servicio ¿Que WAF voy a tener? Imperva, utilizar el del CP, voy a comprar reglas de OWASP.

**BALANCEADOR - API GATEWAY:** Puerta de entrada a la app.

**AUTENTICACION y AUTORIZACION:** Si el usuario está registrado y que permisos tiene. Antes de que el requests llegue a nuestro backend. ¿Que servicio de autenticación voy a usar del mercado?  

**BACKEND - (Servidores, Funciones o Contenedores):** donde está gran parte de nuestra app (microservicios). Zona privada (no acceso directo por internet). ¿ Dónde va a correr nuestro backend?

**BASE DE DATOS: DB Master y DB Standby. DB Master:** continuamente recibe requests de lectura y escritura. DB Standby: modelo activo- pasivo. Si se cae el DB Master, DB Standby comenzará a recibir los requests¿La DB va a ser relacional o noSql(llave valor o memoria o documentos)? ¿Que motor de BD voy a usar

**ALMACENAMIENTO:** Objeto, Bloques o Archivos.

**CONECTIVIDAD - HÍBRIDA (on-premises):** ¿Cómo me conecto? ¿VPN y sacrifico rendimiento?¿Contrato una conexión dedicada con mayor costo?
## **SERVICIOS TRANSVERSALES**:

**OBSERVAVILIDAD:** Monitoreo (medición de métricas, umbrales, alertamiento), trazas (el tiempo que se demoran en conectarse los componentes de nuestra aplicación y logs), experiencia de usuario, detección de anomalías del monitoreo,

**COMPLIANCE:** reglas. Ejemplo: toda la información que se guarde en reposo debe estar cifrada (almacenamiento y db).

**AUDITORÍA:** Para todos los roles y personas que pueden modificar la arquitectura, tener la trazabilidad de que cambios hizo, cuando los hizo y sobre que componentes de la arquitectura.

**CIFRADO - KMS:** todo debe estar cifrado en reposo y en tránsito. KMS (Key Management System Service): administración y gestión de llaves.

![[100_Knowledge/400_Herramientas/200_Servicios en la nube/AWS/Primeros pasos/Pasted image 20240415171313.png]]

# **¿Cómo sería nuestra arquitectura si la app corriera completamente basada en servidores? DIFERENCIAS (balanceador y backend):**

**Balanceador de aplicaciones:** balanceamos tráfico HTTPS. Capa 7 del modelo. El algoritmos del balanceador va a ser un round robin (alterna una y otra zona).
   
**AUTOESCALAMIENTO (autoscaling group):** ante más demanda, basándonos en una imagen del servidor (AMI: Imagen base que ya tiene todo preinstalado), estos crecen en cantidad. Cada servidor nuevo tarda 3 minutos en crearse desde la AMI y hasta que el balanceador determina que está saludable para mandarle tráfico. La escalabilidad horizontal que no requiere downtime (que la app se caiga). Definir cantidad mínima de servidores para soportar la app, la cantidad deseada y la cantidad máxima. Debemos definir la cantidad máxima para no crecer indefinidamente y que se nos consuma todo el costo de un mes.

**Métricas de monitoreo:** para definir cuando comenzamos a crecer en servidores. Ejemplo: cuando la CPU > 60 % sume un servidor y cuando la CPU > 80% sume 2 servidores. También: cuando la CPU % < 60 % reduzca 1 servidor y cuando CPU < 40 % reste 2 servidores. Siempre y cuando no llegue a menos de la capacidad mínima.  
Se puede escalar en cualquier parámetro (% CPU, RAM, etc) pero lo mejor es escalar sobre parámetros de demanda. Ejemplo: Cantidad de usuarios.

**Tener en cuenta:** como escalar, el tiempo de escalamiento y la alta disponibilidad.

![[100_Knowledge/400_Herramientas/200_Servicios en la nube/AWS/Primeros pasos/Pasted image 20240415171153.png]]




# **Cuando la app corre en un orquestador de contenedores (nuestro backend corre en contenedores):**
DIFERENCIAS (backend). KUBERNETES va a ser el orquestador de los contenedores: Vamos a tener por lo menos 2 zonas donde en cada zona va a ver al menos 1 servidor. Cada servidor va a tener los contenedores donde van a correr los microservicios. Ejemplo de microservicios para PlatziWallet: pagos, cobros, saldo, cash-in (consignación), cash-out (retirar), etc. ESCALAMIENTO: por servidores pero también por microservicios. Porque la escalabilidad del microservicio de cash-in es diferente a la escalabilidad del servicio pagos. Porque se puede ingresar dinero una vez (cash-in) pero realizar 25 pagos. Tengo 2 tipos de escalabilidad: del servidor y del microservicio (contenedor).

- **Por SERVIDOR. reglas como:** el microservicio de cobros si lo tengo que escalar lo hago en el servidor que tenga disponible menos ram.

- **Por MICROSERVICIO (servicio de contenedores serverless).** El CP se encarga de los servidores. Es más sencillo el escalamiento porque nos enfocamos en el microservicio puntual y no como escalamos los servidores.


**CICD:** configurar estrategia para llegar a desplegar determinado servicio, versionamiento del microservicio, como lo voy a desplegar, etc.  
REPO de código: como va a ser el CICD, que pasos se van a automatizar, qué pruebas le voy a hacer a la imagen. BASES de DATOS: vamos a usar el STORAGE de los servidores incrementales u otro tipo.

![[100_Knowledge/400_Herramientas/200_Servicios en la nube/AWS/Primeros pasos/Pasted image 20240415171557.png]]



# **Cómo sería tener muchos de los servicios en funciones:**

**DIFERENCIAS**:
**CDN:** hay servicios de cdn que pueden tener funciones. Por ejemplo: para cuando venga un requests transformarlo, para hacer un redireccionamiento 301 o 302 (redireccionamiento de dominio temporal o permanente).

**FUNCIONES del BACKEND:** El API recibe el requests y se lo manda alguna FUNCIÓN. Las reglas del API para la designación de los requests a las funciones sería, por ejemplo: Si la API recibe el request con el pass “/saldos”, le va a mandar ese request a la FUNCIÓN saldos. Entonces para el caso de PlatziWallet tendríamos la funciones de: Saldos, Cash-in, Pagos, entre otras.

**BASE de DATOS**: 1) No Relacional: La DB será llave-valor y cada FUNCIÓN actualizará determinada tabla en la DB. 2) Relacional: No todas las BD relacionales son serverless. Cuando tenemos múltiples funciones consumiendo una BD relacional puede ser que la cantidad de conexiones se caiga. Entonces para la DB relacional los CP están sacando un PROXY de BD. Estos servicios se encargan de todas las conexiones entre cada FUNCIÓN y la DB. Van a manejar el borrowing (pedir prestado canales de conexión). También, garantizan que si se cae el DB Master, solo se pierda un paquete para cuando empiece a funcionar la DB Standby.  
    Entonces, las ventajas del PROXY son: 1) seguridad: garantiza que la comunicación siempre sea en TLS. 2) gestión de conexiones 3) mejorar el tiempo de un failover ante una caída de una zona, por ejemplo.
    
- ORQUESTADOR DE FUNCIONES: se encarga de las relaciones entre funciones. Ejemplo de orquestador: en AWS (step Functions), Apache Airflow se usa como orquestador.
    
- ESCALABILIDAD: va a estar dada por los límites de CP. También podemos reservar concurrencia. Por ejemplo: en AWS para todas las funciones la concurrencia es de 1000 ejecuciones por segundo. Entonces en PlatziWallet se puede reservar 200 concurrencias por segundo para las funciones de Pagos y Consulta de Saldo. Es decir 400 concurrencias por segundo para mis funciones más demandadas. Los otros 600 se van a distribuir a medida de que cada uno de los servicios los vaya utilizando. Por otro lado también se puede hacer un ticket al CP para subir la concurrencia de 1000 a 2000 por ejemplo.
    
- REPO y CICD: hay que ver cómo vamos a desplegar del CICD a la función.
    
- VPC: ¿La función va a correr en una VPC o no? Si es en una VPC hay que tener en cuenta la cantidad de direcciones IP disponibles versus la cantidad de ejecuciones que va a tener esa función para garantizar que tenga IP disponibles.
    
- COLD START: Si la APP no soporta esos segundos iniciales de las funciones podemos pensar en una arquitectura dividida donde tengamos unos servicios en funciones y otros en contenedores. Pues Kubernetes, por ejemplo, no tiene esos segundos iniciales de demora.
