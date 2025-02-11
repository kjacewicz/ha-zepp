Tras conseguirlo con la Xiaomi Band 7, ahora te enseñamos cómo instalar HA en tu reloj Zepp para controlar tus dispositivos.

# Índice 

Modelos compatibles
Características de la aplicación
Instalación de la aplicación
Preparación previa
Instalación mediante el instalador
Instalación a través del terminal
Configuración de la aplicación
Créditos y agradecimientos

# Modelos compatibles

Gracias a los miembros de nuestra comunidad hemos podido testear y adaptar la aplicación a los siguientes modelos:

- Amazfit GTS 3
- Amazfit GTR 3
- Amazfit GTR 3 Pro
- Amazfit GTS 4 Mini
- Amazfit GTS 4
- Amazfit GTR 4
- Amazfit Cheetah Pro
- Amazfit Active
- Amazfit Active Edge
- Amazfit Balance
- Amazfit T-REX 2
- Amazfit Bip 5 Unity
- Amazfit Band 7
- Xiaomi Band 7 (en este caso necesitas un paso previo, revisa esta entrada)

Estamos realizando cambios en la aplicación para hacerla compatible con más dispositivos Zepp, si tienes uno que no está en la lista, pásate por nuestra comunidad de Telegram para probarlo! Por otro lado, si estás pensando en comprar alguno, te recomiendo que revises los precios de Amazfit Global Retail Store en AliExpress.

# Características de la aplicación

Al  instalar HA en tu reloj Zepp vas a poder hacer lo siguiente:

Mostrar tus entidades en 3 categorías (devices, scripts y sensors)
Controlar tus dispositivos (encender y apagar enchufes y luces, cambiar el brillo y efectos si lo permiten, y controlar entidades media)
Lanzar tus scripts y automatizaciones
Mostrar información de tus sensores

Xiaomi Band 7

Amazfit Active

# Instalación de la aplicación

Si estás preparado, sigue estos pasos para instalar HA en tu reloj Zepp!

## Preparación previa

Si aún no lo has hecho, descarga e instala la aplicación de Zepp (formerly Amazfit) en tu dispositivo móvil. Hecho esto, crea una cuenta e inicia sesión.
		
Zepp（formerly Amazfit）

			Price: Free 
		
‎Zepp (formerly Amazfit)

			Price: Free+ 

Ve a Perfil > Ajustes > Acerca de y pulsa varias veces sobre el logo de Zepp hasta que aparezca en pantalla el siguiente mensaje «Ha activado el modo desarrollador».
Los siguiente que haremos será construir e instalar la aplicación de Home Assistant (suena muy complicado, pero te voy a ir guiando por todos lo pasos).
 Antes de instalar la aplicación necesitas preparar el entorno de 
desarrollo, tal y como nos dicen desde la propia plataforma de Zepp (o en este video explicativo).

Entra en node.js y
 descarga la versión que indica “Recommended For Most Users”. Se 
descargará un fichero que tienes que ejecutar e instalar. Este es necesario para que el entorno de desarrollo funcione correctamente.
Entra en git y descarga la última versión. Se descargará un fichero que tienes que ejecutar e instalar. Este es necesario para tener acceso a los repositorios de GitHub desde tu terminal.
Entra en la consola de desarrolladores de Zepp y crea una cuenta (no uses tu cuenta de Google). Esto es necesario para poder instalar la aplicación de HA en tu reloj Zepp.

Ya casi lo tienes! Sólo queda instalar la aplicación y para ello tienes dos opciones. La más sencilla es descargar y utilizar el instalador que ha creado Barny, pero también te voy a explicar como puedes hacerlo tú mismo a través del terminal de tu ordenador.

## Instalación mediante el instalador

Descarga este fichero, descomprímelo y ejecútalo.
Utiliza tu teclado para seleccionar el idioma (1 para español, 2 para inglés) y pulsa ‘enter’.
Pulsa las teclas ‘4’ y ‘enter’ para instalar Zeus CLI (el software para crear aplicaciones de Zepp). Cierra manualmente la ventana cuando termine la instalación.
Pulsa las teclas ‘5’ y ‘enter’ para comprobar la versión instalada. Si te devuelve el número de la versión, todo ha ido bien. Después cierra manualmente la ventana.
Pulsa las teclas ‘6’ y ‘enter’ para instalar nuestra versión de la aplicación de Home Assistant (o actualizarla a la última versión). Cuando termine la instalación pulsa cualquier tecla para continuar.
Pulsa las teclas ‘7’ y ‘enter’, y selecciona tu dispositivo en el listado (si es necesario, utiliza las flechas del teclado para bajar por el listado). Esto generará un código QR en pantalla, que será el que vamos a utilizar para instalar la aplicación.
Abre la aplicación Zepp en tu dispositivo móvil y ve a Perfil > Tu reloj > Modo de desarrollador,
 pulsa sobre el icono «+» de la esquina superior derecha y luego en 
«Scan». Ahora escanea el código QR generado en la consola y espera a que
 termine la pantalla que indica «Installing». Ahora si navegas por tu 
reloj Zepp, comprobarás que ya tienes en tu menú la opción de «Home Assistant».

## Instalación a través del terminal

Si se ha producido algún fallo en la instalación o simplemente prefieres hacerlo por ti mismo, sigue estos pasos:

En la barra de búsqueda de tu ordenador escribe ‘cmd’ para abrir el terminal del sistema. Introduce el siguiente comando ‘npm i @zeppos/zeus-cli -g’ para instalar Zeus CLI (el software para crear aplicaciones de Zepp).
Cuando termine la instalación, introduce el siguiente comando ‘zeus 
-v’ para verificar que se ha relizado correctamente. Si te devuelve el 
número de la versión, todo ha ido bien.

💡Nota: si en el tercer punto obtienes un error que indica "npm ERR! code EBUSY", lanza el siguiente comando 'npm install -g npm@latest' para instalar la última versión de NPM, y después inténtalo de nuevo 

Ahora vamos a instalar nuestra versión de la aplicación de Home Assistant. Para ello lanza los siguientes comandos desde tu terminal (cada línea es un comando)

git clone https://github.com/TitoTB/ha-zepp
cd ha-zepp
zeus preview

Cuando ejecutes este último comando se abrirá en tu navegador la consola de desarolladores de Zepp, en la que tendrás que hacer login con la cuenta que has creado previamente.
Hecho esto vuelve a la consola, y selecciona tu reloj Zepp entre las opciones disponibles (si es necesario, utiliza las flechas del teclado para bajar por el listado). Esto generará un código QR en pantalla, que será el que vamos a utilizar para instalar la aplicación.
Abre la aplicación Zepp en tu dispositivo móvil y ve a Perfil > Tu reloj > Modo de desarrollador,
 pulsa sobre el icono «+» de la esquina superior derecha y luego en 
«Scan». Ahora escanea el código QR generado en la consola y espera a que
 termine la pantalla que indica «Installing». Ahora si navegas por tu 
reloj Zepp, comprobarás que ya tienes en tu menú la opción de «Home Assistant».

# Configuración de la aplicación

Ya sólo nos queda conectar la aplicación con nuestra instancia de HA. Para ello vuelve a la aplicación de Zepp > Perfil > Tu reloj > Modo de desarrollador > Mini Program > Home Assistant (Settings). En esta pantalla tienes que indicar los siguientes datos:

Local HA instance address. Aqui tienes que indicar la dirección local de tu instancia (‘http://homeassistant.local:8123/’).
External HA instance address. Introduce aquí el dominio con el accedes desde el exterior (por ejemplo, ‘https://aguacatec.es/’).
Long access token. Este tienes que generarlo desde 
Home Assistant. Para ello ve a la aplicación de HA en tu dispositivo 
móvil y, en el menú lateral, pulsa sobre tu nombre de usuario. Baja 
hasta el final de la pantalla, pulsa en “Crear token” y dale un nombre (por ejemplo, “XiaomiBand7”). Pulsa sobre el icono junto al código para copiarlo, y vuelve a la aplicación de Zepp para pegarlo.

En el apartado de «Entities» puedes utilizar el buscador para seleccionar las entidades que quieres controlar (puedes buscar por nombre, dominio o dejarlo vacío para sacar todo el listado).
 Después pulsa sobre el botón «Search» y activa las entidades que 
quieras. También puedes utilizar el botón «Top» para ordenar las 
entidades seleccionadas.

# Créditos y agradecimientos

La aplicación que acabas de instalar se ha desarrollado sobre la base de esta aplicación desarrollada por ga2mer. También tomamos la idea para agrupar las entidades por categorías de esta versión de shorty88.

A partir de aquí, desde la comunidad de aguacatec (Barny y Tito) hemos creado una nueva versión, puliendo la interfaz y extendiendo la compatibilidad a más modelos de relojes que funcionan con Zepp OS.

Source: http://web.archive.org/web/20241103093642/https://aguacatec.es/instalar-ha-en-tu-reloj-zepp/
