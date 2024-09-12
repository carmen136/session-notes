heute:

Design im Normalfall zuerst für Smartphone Layouts,
	danach für größere Layouts wie
		Tablets und
			Rechner

-> diese Vorgehensweise nennt man MOBILE-FIRST	


Viewport: 

Smartphonedisplay ist der ganze Viewport -> lässt sich nicht verändern
am Computer kann man verschiedene Viewportbreiten einstellen


Wir programmieren nur Browser Apps, keine nativen Apps


Techniken:


mediaqueries
		> Syntax: @media (media feature) {
			CSS Regel
			}
		> @media screen {
  			/* CSS rules that are only applied on screens */
			}

		> @media print {
  			/* CSS rules that are only applied when printing */
			}
		> max-width media queries sollte man vermeiden - man sollte zuerst über die kleinste Screengröße nachdenken
			und dann media-queries für größere Screens verwenden (min-width)

		> @media (orientation: portrait) {
 			 /* CSS-Regeln, die nur angewendet werden, wenn der Bildschirm im Hochformat ausgerichtet ist */
			}

		> @media (orientation: landscape) {
  			/* CSS-Regeln, die nur angewandt werden, wenn sich der Bildschirm im Querformat befindet */
			}
		> @media (min-aspect-ratio: 8/5) {
			/* The aspect-ratio feature is specified as a <ratio> value representing the width-to-height aspect ratio of the viewport.*/
			}
		> @media (any-pointer: none) {
  			/* CSS rules that are only applied when the device has no pointer (neither touch nor cursor)*/
			}

		> @media (any-pointer: coarse) {
  			/* CSS rules that are only applied when the device has a coarse pointer (mostly touch */
			}

		> @media (any-pointer: fine) {
 			 /* CSS rules that are only applied when the device has a fine pointer (cursor)*/
			}
		> @media (device-pixel-ratio: 1) {
 			/*CSS rules that are only applied when the device has a pixel ratio of 1 (mostly older screens)*/
			}

		> @media (device-pixel-ratio: 2) {
  			/* CSS rules that are only applied when the device has a pixel ratio of 2 (newer screens like the retina screen on your MacBook)*/
			}

		> @media (device-pixel-ratio: 3) {
  			/* CSS rules that are only applied when the device has a pixel ratio of 3 (some high resolution tablets and phones) */
			}
		> @media (prefers-color-scheme: dark) {
  			/* CSS rules that are only applied when the user prefers a dark color scheme */
			}

		> @media (prefers-color-scheme: light) {
  			/* CSS rules that are only applied when the user prefers a light color scheme */
			}
		> @media (prefers-reduced-motion: reduce) {
  			/* CSS rules that are only applied when the user prefers reduced motion */
			}
		> @media (prefers-contrast: more) {
  			/* CSS rules that are only applied when the user prefers a higher contrast */
			}
		> man kann mediaqueries auch kombinieren mit "and" -> @media (min-width: 600px) and (orientation: landscape) -> hier muss beides erfüllt sein
		> gleiches styling in mehreren (voneinander unabhängigen -> also nicht "and" sondern "or") cases mit "," -> @media (min-width: 600px), (orientation: portrait)

Häufig vorkommende Breakpoints:

When using min-width media queries it can be helpful to use common breakpoints.

	> no media query (default): extra-small, xs, mobile
	> (min-width: 600px): small, sm, large mobile
	> (min-width: 900px): medium, md, tablet
	> (min-width: 1200px): large, lg, desktop
	> (min-width: 1536px): extra-large, xl, large desktop

💡 These breakpoints are based on the MUI breakpoints. Other frameworks and projects might define a completely different set of breakpoints. Mostly they are defined to be between the most common screen sizes.
Another example for common breakpoints are the ones from Tailwind CSS.



Tipp: Variablen je nach breakpoints in den mediaqueries festlegen:
Bsp.:

:root {
  --font-size: 12px;
}

@media (min-width: 600px) {
  :root {
    --font-size: 16px;
  }
}

@media (min-width: 1200px) {
  :root {
    --font-size: 20px;
  }
}

body {
  font-size: var(--font-size);
}


Tipp: Verschiedene Bilder anzeigen lassen je nach Bildschirmgröße (-> je nach mediaquery):

The html picture element allows you to define multiple source elements for an image.
The browser will choose the first source that matches the given media query. 
If no source element matches, the browser will use the img element as a fallback.

The img element is required, so that there is always a fallback.

<picture>
  <source
    media="(min-width: 1200px)"
    srcset="https://source.unsplash.com/random/1400x1050"
  />
  <source
    media="(min-width: 900px)"
    srcset="https://source.unsplash.com/random/800x600"
  />
  <img src="https://source.unsplash.com/random/400x300" alt="" />
</picture>




relative Einheiten -> responsive units:
		> vh (viewport height) - 1 vh = 1% of the viewport height
		> vw (viewport width) - 1 vw = 1% of the viewport width
		> em - 1 em is the font size of the current element
		> rem - 1 rem is the font size of the root element
		> % - relative to the related property of the parent or current element
			> width: 1 % = relativ zur Breite des Elternelements
			> padding-top: 10 % = 10% zur Höhe des Elternelements
			> font-size: 50 % = halb so groß wie die Schriftgröße des Elternelements
			> transform: translateX(50%) = Verschiebung auf der X-Achse um 50% der aktuellen Elementbreite
		> calc() - man kann verschiedene Einheiten kombinieren und berechnen 
			> z.B: calc(100vh - 100px)
			> z.B: calc(50 % - 10rem)


Tipps: 

> relative Einheiten für alle Elemente, die skaliert werden müssen, wie z. B. Schriftgrößen, Ränder und Polsterungen.
> absolute Einheiten für Elemente, die nicht skaliert werden sollen, wie z. B. die Breite und Höhe von Bildern.
> die Einheit rem für Schriftgrößen, da sie auf der gesamten Website einheitlich skaliert wird.
> die Einheiten vw und vh für Elemente, die relativ zum Ansichtsfenster skaliert werden sollen.