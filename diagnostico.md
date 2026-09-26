# Diagnóstico · solquerandi.com

Cabañas Sol Querandí — Santa Elena 174, Parque Lago, Mar de Cobo (Buenos Aires).
Análisis del sitio actual: 5 problemas concretos, verificables y con consecuencia
directa sobre las reservas que entran.

---

## 1. El formulario de contacto tira los mensajes a la basura — y le dice al cliente que los ha enviado

**Qué está mal.** El formulario "Enviar mensaje" no envía nada a ninguna parte. En
el código de la web, al pulsar el botón solo ocurre esto:

```js
alert("Mensaje enviado - SolQuerandi.com ✔"), c(""), i("");
```

Muestra el cartel de *"Mensaje enviado ✔"*, vacía los campos y termina. No hay
ninguna conexión con un servidor, ni un envío de email, ni un servicio de
formularios. El mensaje se pierde en el mismo instante en que el visitante lo
escribe.

**Por qué le cuesta clientes.** Es el peor escenario posible: la familia que
quiere reservar escribe sus fechas, ve el tick verde de confirmación y se queda
esperando una respuesta que no va a llegar nunca. No vuelve a insistir, porque
cree que el mensaje ya está enviado. Y Sol Querandí ni siquiera se entera de que
existió esa consulta. Cada reserva perdida por esta vía es invisible: no aparece
en ningún sitio, no se puede contar. Con tres cabañas en temporada, hablamos de
un agujero que no se ve pero se paga.

**Cómo lo resuelve la nueva.** El contacto deja de depender de un formulario.
Los botones llevan directamente a WhatsApp y al email real, que son canales que
no pueden fallar en silencio: o el mensaje sale del teléfono del cliente, o el
cliente lo ve. Si además se quiere formulario, se conecta a un servicio que
entrega el mensaje al correo y avisa si algo falla.

---

## 2. No hay un teléfono ni un WhatsApp en toda la web

**Qué está mal.** Se puede recorrer el sitio entero —portada, cabañas,
comodidades, ubicación, contacto— sin encontrar un solo número de teléfono. No
existe en ninguna parte del código. Los únicos contactos son el formulario roto
del punto 1, el email `solquerandi@gmail.com` y los enlaces a Instagram y
Facebook.

**Por qué le cuesta clientes.** Quien busca cabañas en la costa decide rápido y
pregunta por WhatsApp: disponibilidad para el finde largo, si aceptan mascotas,
si queda sitio para dos coches. Es una conversación de dos minutos que termina en
reserva. Sin un número visible, esa persona no escribe: se va al siguiente
alojamiento de la lista, que sí lo tiene. Y quien reserva por Booking le deja a
Booking la comisión de cada noche, cuando podría haber reservado directo.

**Cómo lo resuelve la nueva.** Un botón de WhatsApp fijo en la barra superior,
visible desde el primer segundo y en todo momento, más el teléfono repetido en
grande en el cierre de la página. El mensaje va preescrito ("Hola, quería
consultar disponibilidad en Sol Querandí"), así el cliente solo tiene que pulsar
enviar.

---

## 3. Al compartir el enlace por WhatsApp aparece la foto de un desconocido

**Qué está mal.** La imagen que acompaña al enlace cuando alguien lo comparte
(`og:image`, en `social-image.png`) es la tarjeta de presentación personal de
**"Hashir Shoaib | Engineer, Programmer, Web Developer, Photographer, Athlete,
Artist"** — el autor de la plantilla que se usó para montar el sitio. Nadie la
cambió. En la misma línea, el icono de la web (`logo192.png`) sigue siendo el
logotipo azul de React que viene por defecto.

**Por qué le cuesta clientes.** Compartir el enlace es el boca a boca de hoy: un
huésped contento pasa la web al grupo familiar. Lo que ese grupo ve no son las
cabañas, ni el cartel de SQ, ni la playa: ven un fondo azul con el nombre de un
señor que no tiene nada que ver con Mar de Cobo. Parece un enlace equivocado, o
directamente sospechoso. Nadie pincha en eso.

**Cómo lo resuelve la nueva.** La imagen de compartir es la foto del frente de
Sol Querandí con su cartel, y el título y la descripción hablan de las cabañas y
de Mar de Cobo. Cuando alguien pasa el enlace, se ve el negocio.

---

## 4. Google entra en la web y ve una página en blanco

**Qué está mal.** El sitio está hecho como aplicación React: el archivo que llega
al navegador está literalmente vacío de contenido. Todo el texto —las tres
cabañas, las comodidades, la ubicación, el entorno— lo dibuja después el
JavaScript. El HTML real que reciben Google y las redes sociales cabe en dos
líneas y termina así:

```html
<noscript>You need to enable JavaScript to run this app.</noscript>
<div id="root"></div>
```

Y encima, el idioma declarado del sitio es inglés (`lang="en"`) cuando todo el
contenido está en español.

**Por qué le cuesta clientes.** Ni una sola de las palabras por las que alguien
busca —"cabañas Mar de Cobo", "alojamiento Parque Lago", "cabañas frente al mar
Mar Chiquita"— está en el HTML que se indexa. Los robots de WhatsApp y Facebook,
que directamente no ejecutan JavaScript, no ven absolutamente nada. La web
existe, pero es invisible para quien todavía no la conoce. Toda la captación
depende entonces de Booking, que cobra su comisión en cada reserva.

**Cómo lo resuelve la nueva.** Es una página HTML normal: todo el contenido está
escrito en el archivo, listo para leerse sin ejecutar nada. Idioma español
declarado, título y descripción orientados a las búsquedas reales de la zona, y
carga instantánea también con mala cobertura en la playa.

---

## 5. El 9,7 de Booking está enterrado, y no hay precios ni forma de reservar

**Qué está mal.** Sol Querandí tiene un **9,7 sobre 10 en los Booking.com
Traveller Review Awards 2023** y un índice de respuesta del 100%. Ese dato está
en la web como una imagen suelta, sin destacar, perdida entre el resto. Al mismo
tiempo, en todo el sitio no aparece ni un precio, ni un calendario, ni un botón
de reservar: el visitante no puede saber cuánto cuesta ni si hay sitio libre. El
pie de página cierra con "Copyright © 2023", que le dice a cualquiera que la web
lleva años sin tocarse.

**Por qué le cuesta clientes.** El 9,7 es el mejor argumento de venta que tiene
el negocio y lo está regalando: es exactamente lo que convence a alguien que duda
entre tres cabañas parecidas. Y sin una orientación de precio, mucha gente ni
pregunta — asume que será caro, o simplemente no quiere el trámite de escribir
para averiguarlo. El resultado combinado es que el visitante que sí llegó a la
web se marcha sin dejar rastro.

**Cómo lo resuelve la nueva.** El 9,7 aparece en grande, animado, con el sello de
Booking, en el momento del recorrido en que el visitante ya se ha enamorado del
sitio. Las tres cabañas —Antú, Cuyen y Saráh— se presentan con su capacidad real
y todo lo que incluyen, y cada una termina en un botón de consulta directa por
WhatsApp. Sin fechas en el pie: nada que delate el paso del tiempo.

---

## De propina (no cuentan como los 5, pero se ven)

- La paleta de colores es la de Bootstrap recién instalado (el azul `#0d6efd`):
  el negocio no tiene ningún color propio en su propia web, cuando su cartel
  pintado a mano tiene una terracota preciosa.
- Las tipografías son las del sistema por defecto, sin ninguna elección de
  diseño detrás.
- Las tres cabañas tienen fotos excelentes y muy humanas (una novia saliendo
  hacia su boda, el frente iluminado de noche) que están reducidas a miniaturas
  dentro de tarjetitas pequeñas.
- Antú y Cuyen comparten exactamente la misma descripción, palabra por palabra.

---

## Lo que sí tienen, y es mucho

Conviene decirlo, porque la propuesta se apoya en esto: el material de partida es
bueno. 34 fotos propias, tres cabañas bien equipadas, una ubicación
extraordinaria (frente a la albufera de Mar Chiquita, patrimonio de la Unesco, a
100 metros de una playa de 4 km), un 9,7 de Booking y una atención que responde
al 100% de los mensajes en pocas horas. No hace falta inventar nada: hace falta
enseñarlo.
