# Supermercado VR para Meta Quest 3S + Wolvic

## Qué es
Actividad WebXR en español para practicar una compra completa:
1. Leer/seguir una lista.
2. Coger los productos correctos.
3. Meterlos en la cesta (se registra automáticamente al seleccionarlos).
4. Ir a caja sin desplazamiento físico.
5. Escanear los productos.
6. Elegir pago con tarjeta o efectivo.
7. Embolsar cada producto.
8. Finalizar y repetir.

Está pensada para alumnado de educación especial: interacción mediante apuntar + gatillo, mensajes breves, refuerzo sonoro, voz opcional, ausencia de locomoción con joystick y dos niveles de longitud.

## Archivos
- `index.html`: actividad completa.
- `diagnostico.html`: comprueba HTTPS, `navigator.xr`, compatibilidad `immersive-vr` y permite abrir una sesión VR mínima.

## IMPORTANTE: no abrir como archivo local
WebXR necesita un contexto seguro. Publica los archivos en un sitio HTTPS. Una opción sencilla es GitHub Pages.

## Publicar con GitHub Pages
1. Crea una cuenta de GitHub si no tienes.
2. Crea un repositorio nuevo, por ejemplo `supermercado-vr`.
3. Sube `index.html` y `diagnostico.html` a la raíz.
4. En el repositorio: **Settings > Pages**.
5. En **Build and deployment**, elige desplegar desde una rama y selecciona `main` / raíz.
6. GitHub mostrará una dirección HTTPS parecida a `https://TUUSUARIO.github.io/supermercado-vr/`.
7. Escribe esa URL en Wolvic o crea un marcador.
8. Antes de usar la actividad con alumnos abre `.../diagnostico.html` en cada gafa.

## Uso en las Quest
1. Abrir Wolvic.
2. Abrir la dirección HTTPS de la actividad.
3. Elegir nivel guiado (3 productos) o estándar (5).
4. Pulsar `ENTRAR EN REALIDAD VIRTUAL`.
5. Apuntar a los objetos con el controlador y pulsar el gatillo.

## Si no entra en VR
1. Comprueba que la URL empieza por `https://`.
2. Abre `diagnostico.html`.
3. Debe indicar:
   - Contexto seguro: `true`.
   - `navigator.xr`: `true`.
   - `immersive-vr`: `true`.
4. Si alguno falla, revisa Wolvic, su configuración WebXR y/o la política MDM/red de la Consejería. No intentes saltarte las restricciones del dispositivo.

## Personalización rápida de la lista
Dentro de `index.html`, busca:

```js
const MODES = {
  guided: ['leche', 'pan', 'manzana'],
  standard: ['leche', 'pan', 'manzana', 'arroz', 'zumo']
};
```

Puedes cambiar el orden o sustituir productos por cualquiera de estos identificadores:
`leche`, `pan`, `manzana`, `arroz`, `zumo`, `yogur`, `galletas`, `pasta`, `cereal`, `agua`, `tomate`, `chocolate`.

## Dependencia
La página carga A-Frame 1.8.0 desde `https://aframe.io/releases/1.8.0/aframe.min.js`.
Por tanto, el filtrado de red debe permitir tanto tu sitio HTTPS como `aframe.io`. Si en el centro `aframe.io` estuviera bloqueado, la solución correcta es alojar también una copia local de A-Frame en el mismo sitio web (no instalar una APK ni eludir el MDM).

## Seguridad y comodidad
- Usa un espacio físico despejado y Guardian/límites configurados según las normas del centro.
- La experiencia evita locomoción continua y teletransporta de compra a caja para reducir mareo y riesgo de choque.
- Empieza con sesiones cortas y supervisadas.
