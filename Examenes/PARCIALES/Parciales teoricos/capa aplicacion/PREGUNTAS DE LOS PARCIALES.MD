# PUERTOS:
FTP: control:21; datos:(ACT 20;PAS <1023).
CORREO:25/587; POP3:110; IMAP:143;
DNS:53; HTTP:80; HTTPS:443;

# HTTP
* HTTP 1.0 metodos: GET(se envia en URL, no espera datos en BODY)-POST-HEAD-PUT-DELETE-LINK-UNLINK.
* HOST VIRTUALES: a partir 1.0. Se puede usar varios servicios en un mismo HOST.(Multiplexacion).
* Comandos TRACE, HEAD y CONNECT a partir de < HTTP 1.1.
* http2: en vez dse usar multiples conexiones, se usa una sola conexion Con requerimientos divididos en STREAMS escritos en binario, se establecen prioridades, estos streams se dividen en mensajes   divididos en frames. donde dicen a que frames pertenece cada mensaje ej:  #data, #header # push-promise...

6. HTTP. Indicar afirmaciones verdaderas para el http/2 y http/3
    a. http/2 Usa conexiones persistentes por default. 
    b. Los HTTP <=2 usan TCP. http/3 usa QUICK->UDP.
    c- http/2 mayormente se implementa sobre TLS, aunque no es requisito.
    d. Ambos dividen la conexión en streams y pueden mandar parte de datos con diferentes prioridades. 
    f. Tanto http/2 como http/3 mejoran el rendimiento de HTTP sin cambiar semántica, cambian SINTAXIS.
    * HTTP/2 resuelve el problema de HOL
    * Los streams pueden ser priorizados
    *  < HTTP 2 son textuales y >=  HTTP 2 es BINARIO
    * Cadastream no necesita utilizar una nueva conexión TCP

2. ¿Cómo mejoran la velocidad de carga de las páginas web el protocolo HTTP? Marque todas las opciones correctas:
a. En HTTP/1.0 en adelante a través de la caché web y recursos en caché. mejorando aceleracion de la velocidad de carga
b. En HTTP/1.1 mejora la velocidad al utilizar múltiples conexiones simultáneas para cada recurso.(evita "HOL" head of line Blocking).
c. En HTTP/2  nultiplexación, compresión de cabeceras y priorización de solicitudes.

4. HTTP. Indicar qué características mejoran el rendimiento de HTTP:
    a-Pipelining
    b-Conexiones persistentes
    c-Compresión de headers
    d-eBinary Framing
    NO: implementación de cookies y uso SSL NO MEJORAN EL RENDIMIENTO.

3. HTTP Catching mejoras 
    a- En el Requerimiento (solicitud del cliente): If-Modified-Since & If-None-Match.
    b- en el Respuesta(servidor): ETag & Last Modified

# FTP
10. Marque las opciones correctas sobre FTP.
    a. En el FTP pasivo, la conexión de datos la inicia el cliente desde el port <1023.
    b. En el FTP activo, la conexión de datos la inicia el servidor desde el port 20.
    c. Un archivo descargado se obtiene a través del canal de DATOS.
    d. FTP utiliza un canal de datos y un canal de control (2 conexiones)
    e. Los clientes FTP requieren NO interfaz gráfica
    f. Corre sobre TCP
    g. NO Es soportado por los navegadores utilizando la URI ftp://
    h. Es un protocolo antiguo, en desuso
    i. NO CONEXIONES PERSISTENTES, mantiene estado (si esta autenticado). 
    j. No es necesario autenticarse para su uso, puede ser incognito.

# TLS/SSL
9. TLS/SSL. Indicar características
    a. Implementa autenticación del servidor.
    b. HTTP,POP3,imap usan TLS para asegurar las comunicaciones.
    c. Provee cifrado para garantizar confidencialidad de los datos.
    d. Como parte del handshake el servidor envla su certificado que contiene su clave PUBLICA.
    e. Los mensajes se cifran con la clave de sesion,la cual es un secreto compartido entre cliente y servidor (ambos la conocen).

# DNS
Iterativa: Al realizar una consulta como DNS local a un ROOTSERVER/TLD/AUTORITATIVO, por no tener cacheada la respuesta .
Recursiva: Cuándo se consulta al servidor DNS local y a un open DNS como 8.8.8.8.
SOA- nos da el servidor PRIMARIO (nos muestra NOMBRE y NRO SERIE).

# EMAIL POP3/IMAP SMTP/DNS
3. SMTP/DNS. Si el usuario ada@a.com envía un e-mall a bob@b.org, el MTA de "a" deberá consultar.
    a- MX    b- A y/o AAAA
5. Comandos EMAIL y las relaciones a los HEADER: MUA local - commandos:
    b. FROM - MAIL FROM.  e. TO - RCPT TO. C.HELO  b.QUIT D.DATA

8. EMAIL partes involucradas desde SALIDA a RECEPCION: 
    MUA: Enviar correos electrónicos a través de una interfaz con el usuario.
    MSA: Procesa el mail del mua y lo deja en el MTA.
    MTA: Transportar los correos electrónicos entre diferentes servidores de correo electrónico.
    MDA/LDA: Entregar los correos electrónicos al buzón del destinatario.
    MAA (usa POP3/IMAP): AUTENTICA AL MUA, le permite el acceso al buzón de correo electrónico.

9. POP e IMAP.
    a. POP3 e IMAP permiten correr de forma segura utilizando SSL/TLS
    b. POP3 E IMAP NECESITA autenticación.
    C. El protocolo POP3 solo permite acceder a la carpeta INBOX del mailbox.
    d. IMAP permite gestionar carpetas del lado del servidor 
    e. LIST, USER Y PASS son comandos del protocolo POP3
    a-POP3 descarga obligatoriamente los mensajes del servidor al dispositivo del usuario.
    b- IMAP permite el acceso a los mensajes desde múltiples dispositivos y la manipulación de mensajes en el servidor (en carpetas).
    c- POP3/IMAP protocolos requieren autenticación ASCII 7 bits en 8 NVT.
    
9. ¿cuáles son los posibles protocolos utilizados por el MUA y el MTA respectivamente? Marque todas las opciones correctas:
    MUA: POP3, MTA: SMTP  ::    MUA: IMAP, MTA: SMTP
5. E-MAIL. Indicar características verdaderas de protocolo SMTP
    a. Usa conexiones persistentes.
    b. NO requiere autenticación.
    c. Usa como protocolo de transporte TCP.
    d. Usa por default el puerto 25.
    e- Se utiliza para la comunicación entre MTAS.
    f- comando del protocolo: mail from, rcpt to, quit,helo, data
    g- ESMTP: extiende SMTP y puede usar 8bits MIME y TLS.

# OTROS
1. Arquitectura cliente-servidor en términos de distribución de tareas y responsabilidades?
    a. PEER to PEER: La arquitectura distribuye las tareas de manera equitativa entre clientes y servidores. 
    b. MAINFRAIM: Los servidores realizan todas las tareas, y los clientes solo solicitan información (DUMB CLIENT).
    c. cliente-servidor: Los servidores gestionan recursos y servicios, mientras que los clientes solicitan y utilizan esos recursos.

5. ¿Cuál es el propósito de la delegación de autoridad en una red? Selecciona todas las respuestas correctas.
    a-Facilitar la administración DISTRIBUIDA de la red.
    b- Reducir la carga de trabajo en servidores centrales.
    c- Permitir que los servidores locales tomen decisiones autónomas.
    NOTA- NO MEJORA LA SEGURIDAD EN LA RED.

################################################################################# 

