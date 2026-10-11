# Gusanazos

Juego de artillería por turnos con terreno destructible. Se puede jugar online entre dos navegadores o con dos jugadores en el mismo dispositivo.

Todo el juego está en un solo archivo, `index.html`, sin compilación ni dependencias que instalar.

## Subirlo a Vercel

### Opción A: desde GitHub (sin instalar nada)

1. En github.com, crea un repositorio nuevo, por ejemplo `gusanazos`.
2. Dentro del repositorio, pulsa **Add file → Upload files** y sube `index.html` (y este README si quieres).
3. En vercel.com, pulsa **Add New… → Project**, elige el repositorio y luego **Deploy**. En *Framework Preset* deja **Other**; no hace falta tocar nada más.
4. En menos de un minuto tendrás una dirección del tipo `gusanazos.vercel.app`.

Cada vez que subas un cambio a GitHub, Vercel publica la versión nueva solo.

### Opción B: desde la terminal (necesita Node.js)

```bash
cd gusanazos
npx vercel          # la primera vez te pide iniciar sesión; acepta las opciones por defecto
npx vercel --prod   # publica en la dirección definitiva
```

## Cómo se juega online

1. Uno pulsa **Crear partida online** y le pasa a su rival el código de 5 letras o el enlace.
2. El otro abre el enlace, o escribe el código y pulsa **Unirme**.
3. La partida empieza sola. El anfitrión juega con los Rojos y el invitado con los Azules.

La conexión es directa entre los dos navegadores (P2P con WebRTC). El servidor gratuito de PeerJS solo sirve para que os encontréis; la partida no pasa por ningún servidor vuestro.

**Limitación conocida:** algunas redes, como la wifi de algunas empresas o ciertas conexiones móviles, bloquean las conexiones directas. Si dos personas no consiguen conectarse, suele bastar con que una cambie de red, por ejemplo pasando de datos móviles a wifi. Para que funcione en el 100 % de las redes habría que añadir un servidor TURN; hay opciones gratuitas con límites, como Metered o Cloudflare.

## Controles

- **Teclado:** ← → moverse · ↑ ↓ apuntar · mantener Espacio para cargar y soltar para disparar · Enter saltar · 1–4 armas · C centrar la cámara · M ver el mapa entero.
- **Móvil:** con los botones de debajo del campo.
- **Mirar el mapa:** arrastra el campo con el dedo o con el ratón (cualquier botón). Zoom con la rueda o pellizcando. «Centrar» vuelve a seguir la acción; al disparar o cambiar de turno la cámara vuelve sola.

## Personalización

- **Skins:** en el menú eliges color, sombrero (gorra, vaquero, corona, vikingo, fiesta, pirata, chistera, cascos) y ojos. Tu rival ve tu skin en el online.
- **Mapas:** Pradera, Desierto, Nieve, Volcán y Golosinas, cada uno con su cielo, texturas, decorados, clima y líquido. Lo elige quien crea la partida (o «Aleatorio»).

| Arma | Cómo funciona |
|---|---|
| Bazuca | Se carga la potencia; le afecta el viento |
| Granada | Rebota y explota a los 3 segundos |
| Escopeta | Disparo recto e instantáneo, daño pequeño |
| Dinamita | Se suelta a tus pies; explota a los 4 segundos y hace mucho daño |

Después de disparar tienes 3 segundos para ponerte a cubierto.

## Probar el online en un solo ordenador

Abre el juego en dos pestañas del mismo navegador añadiendo `?local` a la dirección (por ejemplo `gusanazos.vercel.app/?local`). Crea la sala en una pestaña y únete con el código en la otra. Este modo no usa Internet; sirve para probar cambios.
