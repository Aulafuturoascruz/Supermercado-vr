# Supermercado VR v2 + modo compatible (Quest 3S + Wolvic)

## Qué incluye esta versión
Esta segunda versión intenta resolver el problema más habitual en centros con restricciones de red o MDM:
- **Modo VR (WebXR)**: supermercado más realista con estanterías, dependiente, clientes, más productos y pago con monedas/billetes de euro.
- **Modo compatible**: si la parte VR no carga, la actividad sigue funcionando como una web interactiva normal dentro de Wolvic o en cualquier navegador moderno.

De este modo, **si la Consejería bloquea la librería VR**, el alumnado al menos puede trabajar la actividad en el navegador.

## Archivos
- `index.html`: actividad principal con modo VR + modo compatible.
- `diagnostico.html`: diagnóstico rápido de HTTPS y WebXR.
- `README.md`: guía.

## Funcionamiento
1. Elige nivel:
   - guiado (3 productos)
   - estándar (5)
   - amplio (7)
2. Coge los productos de la lista.
3. Ve a caja.
4. Escanea productos.
5. Paga con tarjeta o efectivo.
6. Embolsa.
7. Repite si quieres.

## Cómo usarlo en las Quest
1. Sube esta nueva versión a GitHub Pages.
2. Abre la URL en **Wolvic**.
3. Si carga la escena 3D y aparece el botón de VR, úsala.
4. Si no carga la VR, usa directamente el **modo compatible**.

## Importante sobre la compatibilidad real
La parte de VR se apoya en **A‑Frame 1.8.0**, una librería web para crear experiencias WebXR. La documentación oficial explica que puede cargarse con una etiqueta `<script>` desde CDN o alojarse por cuenta propia. Si una red bloquea ese recurso, la solución correcta es **servir también esa librería desde el mismo sitio web** o permitir ese dominio, no intentar saltarse el MDM ni instalar apps sin permiso. Ver documentación oficial de A‑Frame. 

## Fuentes fiables consultadas
1. **A‑Frame 1.8.0 – Installation**: explica cómo incluir A‑Frame mediante `<script>` y que también se puede servir por cuenta propia.
   https://aframe.io/docs/1.8.0/introduction/installation.html
2. **A‑Frame – Interactions & Controllers**: documentación oficial sobre interacciones y controladores VR.
   https://aframe.io/docs/1.8.0/introduction/interactions-and-controllers.html
3. **WebXR Device API**: especificación del estándar WebXR.
   https://immersive-web.github.io/webxr/
4. **Wolvic 1.9 / Chromium Wolvic 1.3**: información del navegador usado en visores VR.
   https://www.wolvic.com/blog/release_1.9/
5. **Banco Central Europeo – monedas y billetes en euros**: referencia de denominaciones reales de euro.
   https://www.ecb.europa.eu/euro/coins/html/index.es.html
   https://www.ecb.europa.eu/euro/banknotes/html/index.es.html

## Recomendación práctica
- **Primero** abre `diagnostico.html` en Wolvic.
- **Después** abre `index.html`.
- Si la escena VR no llega a cargar, no esperes indefinidamente: usa el modo compatible.

## Observación didáctica
Esta versión utiliza precios y flujo de compra simplificados con finalidad educativa. Las monedas y billetes usados son reales, pero el objetivo principal es trabajar autonomía, secuenciación, atención y manejo funcional del dinero.
