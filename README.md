# Q-SENSE LAB

## Demostrador de principios y medición cuántica: detección de activos enterrados y cartografía del subsuelo

**Aplicación base:** versión 1.0.0.  
**Actualización matemática:** actualizador local con KaTeX 0.16.27.  
**Idioma:** español de España.  
**Finalidad:** formación y exploración de modelos físicos simplificados.

> \*\*Demostración educativa con datos sintéticos. No representa prestaciones certificadas de un instrumento real.\*\*
>
> No es un simulador metrológico certificado, un gemelo digital de un producto comercial ni una herramienta para decidir excavaciones. Una anomalía simulada no confirma la existencia, geometría, titularidad o estado de un activo.

\---

## Índice

1. [Objetivo y alcance](#1-objetivo-y-alcance)
2. [Estado de la entrega](#2-estado-de-la-entrega)
3. [Inicio rápido](#3-inicio-rápido)
4. [Actualización de ecuaciones con KaTeX](#4-actualización-de-ecuaciones-con-katex)
5. [Requisitos y compatibilidad](#5-requisitos-y-compatibilidad)
6. [Navegación y guía de uso](#6-navegación-y-guía-de-uso)
7. [Controles y resultados comunes](#7-controles-y-resultados-comunes)
8. [Átomos fríos: gravímetro y gradiómetro](#8-átomos-fríos-gravímetro-y-gradiómetro)
9. [Magnetómetro OPM](#9-magnetómetro-opm)
10. [Diamante NV](#10-diamante-nv)
11. [SQUID y realimentación FLL](#11-squid-y-realimentación-fll)
12. [Escenarios de infraestructuras](#12-escenarios-de-infraestructuras)
13. [Experiencias guiadas](#13-experiencias-guiadas)
14. [Exportaciones](#14-exportaciones)
15. [Arquitectura y estructura de archivos](#15-arquitectura-y-estructura-de-archivos)
16. [Desarrollo, compilación y despliegue](#16-desarrollo-compilación-y-despliegue)
17. [Pruebas y validación](#17-pruebas-y-validación)
18. [Seguridad, privacidad y funcionamiento local](#18-seguridad-privacidad-y-funcionamiento-local)
19. [Resolución de problemas](#19-resolución-de-problemas)
20. [Limitaciones y requisitos pendientes](#20-limitaciones-y-requisitos-pendientes)
21. [Mantenimiento y ampliaciones propuestas](#21-mantenimiento-y-ampliaciones-propuestas)
22. [Glosario](#22-glosario)
23. [Referencias, licencias y trazabilidad](#23-referencias-licencias-y-trazabilidad)

\---

## 1\. Objetivo y alcance

Q-SENSE LAB permite recorrer la cadena de medición de cuatro tecnologías:

|Módulo|Sonda|Magnitud|Observable|Estimación|
|-|-|-|-|-|
|Átomos fríos|Átomos de rubidio y pulsos de luz|Gravedad o gradiente|Poblaciones atómicas|Ajuste de fase y selección de rama|
|OPM|Espines en vapor alcalino|Campo magnético residual|Señal óptica temporal|Frecuencia de precesión|
|Diamante NV|Centros nitrógeno-vacante|Campo aproximadamente axial|Fluorescencia ODMR|Separación de resonancias|
|SQUID|Lazo superconductor y uniones Josephson|Flujo y campo normal|Tensión periódica|Rama previa o realimentación FLL|

El gravímetro y el gradiómetro son **modalidades del primer módulo**, no tecnologías adicionales que sustituyan a OPM, NV o SQUID.

La experiencia distingue preparación, interacción, señal, ajuste, resultado y fallo. Los estimadores se alimentan de observables sintéticos; el valor verdadero sirve para generar la señal y comparar el resultado, no para reemplazar el ajuste.

### Usos adecuados

* Explicar principios físicos y cadenas instrumentales.
* Explorar el efecto de parámetros, ruido y muestreo.
* Mostrar ambigüedades de una medida periódica.
* Comparar cadenas de medición sin equiparar magnitudes incompatibles.
* Introducir escenarios idealizados de cavidades, cables y anomalías magnéticas.

### Usos excluidos

* Localización certificada de servicios enterrados.
* Decisiones de excavación, seguridad o mantenimiento de activos reales.
* Presupuestos de incertidumbre metrológica completos.
* Atribución de precisión, profundidad detectable, TRL o coste a fabricantes.
* Sustitución de campañas GPR, EMI, ERT, sondeos o inspección directa.

## 2\. Estado de la entrega

**Aplicación base v1.0.0:** HTML autónomo y ZIP con código, documentación y pruebas.

La implementación base utiliza **JavaScript ES modules, Canvas y SVG nativos**, no React, TypeScript ni Vite. Esta desviación respecto a la recomendación inicial está documentada y permite una distribución sin dependencias npm.

Las pruebas de software no equivalen a validación experimental ni a revisión científica independiente.

## 3\. Inicio rápido

### Opción A: HTML autónomo

1. Descargue `Q-SENSE-LAB.html`.
2. Abra el archivo con un navegador moderno y JavaScript habilitado.
3. Seleccione un módulo.
4. Abra **Laboratorio** o cargue una experiencia guiada.

No necesita instalar Node.js ni disponer de internet para utilizar la aplicación autónoma.

### Opción B: paquete ZIP

1. Extraiga completamente `Q-SENSE-LAB\_Completo.zip`.
2. Abra `ABRIR\_APLICACION.html` dentro de la carpeta extraída.
3. Como alternativa, abra `dist/Q-SENSE-LAB.html`.

No abra la aplicación desde el interior del ZIP sin extraerlo.

### Opción C: código modular

El `index.html` de la raíz carga módulos externos. Utilícelo mediante un servidor local, no por doble clic. Consulte la sección de desarrollo.

## 4\. Actualización de ecuaciones con KaTeX

### 4.1 Archivos implicados

|Archivo|Función|
|-|-|
|`Q-SENSE-LAB.html`|Aplicación autónoma original|
|`Q-SENSE-LAB\_Actualizador\_KaTeX.html`|Actualizador local|
|`Q-SENSE-LAB\_KaTeX.html`|Copia generada al aplicar la actualización|

El actualizador incorpora KaTeX 0.16.27, estilos y fuentes. No usa CDN y procesa el archivo seleccionado en el navegador.

### 4.2 Procedimiento

1. Conserve una copia del HTML original.
2. Abra `Q-SENSE-LAB\_Actualizador\_KaTeX.html`.
3. Seleccione `Q-SENSE-LAB.html` mediante el selector de archivo.
4. Pulse el enlace de descarga que aparece al terminar el procesamiento.
5. Guarde `Q-SENSE-LAB\_KaTeX.html`.
6. Abra esa nueva copia y revise los cuatro módulos.

El original no se modifica. No seleccione el ZIP, `ABRIR\_APLICACION.html` ni el `index.html` modular.

### 4.3 Alcance del renderizado

El actualizador:

* Convierte los bloques `.equation` reconocidos a KaTeX.
* Convierte las fórmulas catalogadas dentro de textos explicativos.
* Reconoce delimitadores LaTeX explícitos `\\(...\\)` y `\\\[...\\]`.
* Observa cambios del DOM para volver a renderizar al cambiar de vista.
* Añade estilos y renderizado al resumen imprimible de la versión compatible.
* Genera HTML matemático y MathML.
* Usa `trust: false` y registra errores de renderizado.

El catálogo probado contiene **36 expresiones**, incluidas las ecuaciones principales y varias relaciones auxiliares.

### 4.4 Qué no garantiza

No se ha auditado exhaustivamente la aplicación original tras aplicar el parche. Por tanto, no se garantiza que **toda** expresión matemática visible haya quedado convertida.

El recorrido de texto excluye SVG, Canvas, controles de selección, código y otros elementos para evitar alterar la interfaz. Las etiquetas dibujadas en Canvas/SVG no pasan automáticamente por KaTeX. Los datos CSV/JSON conservan su formato de datos, no HTML matemático.

Una fórmula nueva sin correspondencia en el catálogo debe escribirse con delimitadores LaTeX o incorporarse al catálogo. No se deben interpretar textos arbitrarios como ecuaciones mediante conversiones heurísticas no verificadas.

### 4.5 Diagnóstico para desarrolladores

En la consola del HTML actualizado:

```javascript
window.katex.version
window.QSLMathReport
```

`QSLMathReport` contiene el número de expresiones renderizadas y los errores registrados. El contador es acumulativo: volver a crear una vista puede aumentar el número; no es un recuento de ecuaciones únicas.

Para solicitar renderizado sobre un contenedor:

```javascript
window.QSLRenderMath(document.body);
```

### 4.6 Compilación y conservación del parche

El proceso de compilación original genera la aplicación base. **No incorpora automáticamente el actualizador KaTeX a los módulos fuente.** Si vuelve a compilar desde el código original, deberá volver a aplicar el actualizador al HTML resultante.

No se debe afirmar que el ZIP base contiene una versión fuente plenamente migrada a KaTeX.

## 5\. Requisitos y compatibilidad

### Para utilizar la aplicación

* Navegador moderno con JavaScript, Canvas y SVG.
* Permiso para abrir archivos HTML locales o acceso a un alojamiento estático autorizado.
* Descargas habilitadas para exportar resultados.
* Ventanas emergentes permitidas si se utiliza el resumen imprimible.

La aplicación base se probó en Chromium en escritorio y en una ventana de 820 px de ancho representativa de tableta. No existe certificación de compatibilidad con todos los navegadores o dispositivos.

### Para desarrollo

* Node.js 20 o superior, recomendado en la entrega base.
* npm para ejecutar los scripts del proyecto.
* Python y Playwright únicamente para las pruebas de navegador.

No hay dependencias npm que instalar en la aplicación base. KaTeX está incorporado en el actualizador y en la copia HTML generada, no en `package.json` de la base.

## 6\. Navegación y guía de uso

### Navegación principal

* Inicio y guía.
* Átomos fríos.
* OPM.
* Diamante NV.
* SQUID.
* Comparador.
* Glosario, modelos y fuentes.

### Vistas de cada módulo

|Vista|Contenido|
|-|-|
|Principio físico|Magnitud, sonda, interacción y ecuaciones|
|Instrumento|Componentes y esquema conceptual|
|Secuencia|Etapas, componente activo y observable disponible|
|Laboratorio|Parámetros, señales, ajustes y resultados|
|Infraestructuras|Perfil espacial de una fuente idealizada|
|Ventajas y límites|Supuestos, dominio y restricciones|

### Niveles de explicación

* **Básico:** intuición y secuencia.
* **Técnico:** variables y procesamiento.
* **Avanzado:** supuestos, calibración y dominio.

### Flujo de aprendizaje recomendado

1. Lea el principio físico.
2. Identifique qué señal se registra realmente.
3. Recorra la secuencia con anterior/siguiente.
4. Ejecute el laboratorio sin ruido.
5. Modifique un parámetro cada vez.
6. Active ruido y repeticiones.
7. Explore un fallo deliberado.
8. Consulte el perfil de infraestructura y transfiera un punto al laboratorio si está dentro del rango.
9. Exporte configuración y resultados para conservar el experimento.

Las animaciones son conceptuales y no están a escala. La velocidad de reproducción no altera los parámetros físicos.

## 7\. Controles y resultados comunes

### Controles

* Iniciar, pausar y reiniciar la secuencia.
* Avanzar y retroceder por etapas.
* Velocidad visual de reproducción.
* Entradas numéricas y deslizadores.
* Activación de ruido sintético.
* Semilla reproducible.
* Número de repeticiones.
* Restauración del escenario.
* Tema claro/oscuro.
* Notación científica opcional.

La interfaz acepta coma decimal. Los valores de JSON usan la sintaxis numérica estándar de JSON.

### Semilla y ruido

La base utiliza Mulberry32 para la secuencia pseudoaleatoria y Box-Muller para ruido normal. La misma configuración y semilla produce los mismos datos. Cambiar la semilla cambia la realización de ruido, no las ecuaciones.

### Panel de resultados

|Campo|Interpretación|
|-|-|
|Verdadero configurado|Magnitud usada para generar el experimento sintético|
|Estimado desde señal|Resultado del procesamiento del observable|
|Error|Estimado menos verdadero|
|Dispersión|Desviación típica muestral de estimaciones válidas|
|Repeticiones válidas|Adquisiciones aceptadas por el modelo|
|Observable|Señal que alimenta el estimador|
|Diagnósticos|Calibraciones, límites y advertencias|

La dispersión no incluye todos los sesgos, calibraciones o fuentes de incertidumbre. Con una única repetición no se calcula desviación típica muestral.

### Estados

* **Válido:** el modelo acepta la estimación bajo sus condiciones.
* **Ambiguo:** existen varias soluciones compatibles.
* **Fuera de rango:** parámetros o hipótesis fuera del dominio.
* **No estimable:** señal o condiciones insuficientes.

Un estado válido no significa precisión certificada ni aptitud para campo.

## 8\. Átomos fríos: gravímetro y gradiómetro

### Cadena de medición

Preparación y enfriamiento → liberación → pulso de división → evolución → reflexión → evolución → recombinación → poblaciones → ajuste de fase.

Las ramas representan ondas de materia, no dos objetos clásicos independientes.

### Modelo

$$
\\varphi=(k\_{\\mathrm{eff}}g-\\alpha)T^2+\\varphi\_{\\mathrm{offset}}+\\varphi\_{\\mathrm{ruido}}
$$

$$
P=\\frac{1+C\\cos\\varphi}{2}
$$

El laboratorio barre una fase de lectura y ajusta:

$$
P(\\theta)=a+b\\cos\\theta+c\\sin\\theta,
\\qquad \\widehat\\varphi=\\operatorname{atan2}(-c,b).
$$

La fase periódica exige un intervalo previo para seleccionar la rama. La referencia de gravedad de la base es 9,81 m/s².

En modo gradiómetro:

$$
\\Delta\\varphi=\\varphi\_{\\mathrm{sup}}-\\varphi\_{\\mathrm{inf}},
\\qquad \\Gamma\\approx\\frac{\\Delta\\varphi}{k\_{\\mathrm{eff}}T^2L}.
$$

### Parámetros documentados de la base

|Clave|Parámetro|Unidad|Rango|
|-|-|-|-|
|`mode`|Modalidad|—|`gravity` / `gradient`|
|`dg`|Anomalía respecto a la referencia|µGal|−1000 a 1000|
|`gamma`|Gradiente|E|−1500 a 1500|
|`T`|Separación entre pulsos|s|0,01 a 0,2|
|`contrast`|Contraste|—|0,05 a 1|
|`L`|Línea base|m|0,1 a 5|
|`N`|Átomos por lectura|—|100 a 1 000 000|
|`common`|Ruido común de fase|rad|0 a 0,5|
|`differential`|Ruido independiente|rad|0 a 0,1|
|`offset`|Offset real|rad|−0,5 a 0,5|
|`calOffset`|Offset calibrado|rad|−0,5 a 0,5|
|`alphaShift`|Cambio del barrido angular|rad/s²|−100 a 100|
|`prior`|Semiancho previo de anomalía|µGal|50 a 2000|

El intervalo previo del gradiente en el motor base es ±2000 E. Algunos controles se ocultan según la modalidad.

### Ruido y gráficos

* Poblaciones y ajuste de franja.
* Fases superior e inferior.
* Diferencia de fase envuelta.
* Ruido común y residual diferencial.
* Estimación por repetición.

El ruido común acopla con factores 0,97 y 1 a los dos canales. Por tanto, su cancelación es parcial. El ruido de población usa una aproximación gaussiana al conteo binomial y se recorta al intervalo \[0,1].

### Límites

Se omiten rotación, Coriolis, aberraciones y duración finita de pulsos. Una sola población no determina una fase única. El modelo no elimina la ambigüedad de inversión del subsuelo.

## 9\. Magnetómetro OPM

### Cadena de medición

Bombeo óptico → polarización → interacción con el campo → precesión libre → modulación óptica → detección → frecuencia → módulo del campo.

La ausencia de criogenia no implica que la celda no necesite calentamiento.

### Modelo

$$
f\_L=\\gamma\_{\\mathrm{Hz}}\\lvert B\\rvert
$$

$$
S(t)=S\_0+A e^{-t/T\_2}\\cos(2\\pi f\_Lt+\\varphi\_0)+\\varepsilon(t)
$$

La base usa FFT con ventana Hann para inicializar la frecuencia y un ajuste posterior de la señal amortiguada. El estimador recibe la señal, el muestreo y calibraciones; no recibe el campo verdadero para sustituir el ajuste.

El campo residual es una suma escalar colineal de señal, fondo y compensación. El modelo no reconstruye un vector ni recupera el signo mediante la frecuencia.

### Parámetros

|Clave|Parámetro|Unidad|Rango|
|-|-|-|-|
|`B`|Campo de señal|nT|−500 a 500|
|`bg`|Fondo|nT|−1000 a 1000|
|`comp`|Compensación|nT|−1000 a 1000|
|`gamma`|Coeficiente giromagnético|Hz/T|6×10⁹ a 8×10⁹|
|`A`|Amplitud óptica|u. n.|0,005 a 1|
|`T2`|Relajación transversal|s|0,005 a 0,3|
|`fs`|Muestreo|Hz|200 a 10 000|
|`duration`|Duración física|s|0,01 a 0,5|
|`sigma`|Ruido óptico|u. n.|0 a 0,2|

El coeficiente inicial es aproximadamente 6,9958×10⁹ Hz/T para la modalidad didáctica Rb-87, F=2. No es una calibración certificada.

### Rechazo de medidas

* Frecuencia sintética igual o superior a Nyquist.
* Menos de tres ciclos durante el registro.
* Menos de dos ciclos coherentes según el criterio del modelo.
* Amplitud ajustada insuficiente.
* Registro fuera del límite de 16 a 8192 muestras.

El diagnóstico de aliasing conoce la frecuencia generada para enseñar el fallo. En un instrumento real esa verdad no está disponible automáticamente.

### Límites

No es una descripción universal de OPM ni de SERF. No se modelan bombeo dinámico, colisiones, desplazamientos ópticos o respuesta vectorial completa.

## 10\. Diamante NV

### Cadena de medición

Inicialización óptica → barrido de microondas → resonancia → reducción de fluorescencia → ajuste ODMR → módulo del campo paralelo.

### Modelo axial

$$
f\_{\\pm}=D\\pm\\gamma\_{\\mathrm{NV}}B\_{\\parallel}
$$

$$
F(f)=F\_0-C\\left\[L(f,f\_-)+L(f,f\_+)\\right]
$$

$$
\\lvert B\_{\\parallel}\\rvert=\\frac{\\lvert f\_+-f\_-\\rvert}{2\\gamma\_{\\mathrm{NV}}}
$$

Se ajustan el centro y la separación de dos Lorentzianas con ancho conocido. Offset y contraste se ajustan linealmente. El desplazamiento común de las resonancias se informa por separado.

La base adopta D de referencia de 2870 MHz y un coeficiente de 0,02802495 MHz/µT.

### Parámetros

|Clave|Parámetro|Unidad|Rango|
|-|-|-|-|
|`B`|Campo configurado|µT|−200 a 200|
|`angle`|Ángulo respecto al eje NV|grados|0 a 180|
|`Dshift`|Desplazamiento común de D|MHz|−3 a 3|
|`width`|FWHM conocida|MHz|0,1 a 3|
|`contrast`|Contraste por resonancia|u. n.|0,005 a 0,2|
|`span`|Semiancho del barrido|MHz|1 a 20|
|`points`|Puntos|—|81 a 481|
|`sigma`|Ruido de fluorescencia|u. n.|0 a 0,02|

### Resolución y dominio

El criterio didáctico exige separación suficiente frente al ancho y al paso, contraste suficiente y mejora respecto a una resonancia. Se rechazan resonancias recortadas por el barrido.

Los campos alejados más de 5° de los ejes 0°/180° se consideran fuera del dominio axial. La proyección mostrada no sustituye una solución del Hamiltoniano completo.

### Límites

* No recupera el signo por desdoblamiento solamente.
* No incluye strain ni mezcla transversal.
* No implementa reconstrucción vectorial de cuatro orientaciones.
* El perfil espacial es 1D, no un mapa vectorial 2D.
* Resolución próxima no equivale a profundidad de detección.

## 11\. SQUID y realimentación FLL

### Cadena de medición

Estado criogénico → acoplamiento de flujo → interferencia Josephson → respuesta eléctrica → tensión → rama previa o FLL → flujo y campo.

### Modelos

$$
\\Phi\_0=\\frac{h}{2e},\\qquad \\Phi=B\_{\\perp}A\_{\\mathrm{eff}}
$$

$$
I\_c(\\Phi)=2I\_0\\left|\\cos\\left(\\frac{\\pi\\Phi}{\\Phi\_0}\\right)\\right|
$$

$$
V(\\Phi)=V\_{\\mathrm{offset}}+V\_{\\mathrm{amp}}\\cos\\left(\\frac{2\\pi\\Phi}{\\Phi\_0}+\\varphi\_0\\right)
$$

La corriente crítica corresponde a un DC SQUID simétrico ideal de inductancia despreciable. La tensión es una función fenomenológica: no es una solución completa de la dinámica Josephson.

### Lazo abierto

Una tensión puede corresponder a varios flujos. La estimación necesita una rama previa explícita. El intervalo inicial de referencia es \[0; 0,5] en unidades de flujo normalizado.

### FLL

El controlador trabaja alrededor de un punto de cuadratura. Obtiene un residual estimado de la tensión local y actualiza la realimentación. El flujo estimado combina realimentación y residual, con unidades consistentes.

**Advertencia dimensional del texto heredado:** algunas explicaciones de la base mezclaban el residual normalizado y el flujo dimensional. El actualizador KaTeX cambia la presentación, no corrige por sí mismo esa convención. Para interpretar el motor, si r es adimensional debe multiplicarse por Φ₀ al sumarlo a un flujo en Wb; si se trabaja en unidades de Φ₀, todos los términos de la suma deben estar normalizados. El límite local del controlador se aplica al residual normalizado con magnitud inferior a 0,24.

### Parámetros

|Clave|Parámetro|Unidad|Rango|
|-|-|-|-|
|`mode`|Lectura|—|`open` / `fll`|
|`profile`|Excitación|—|`ramp` / `step`|
|`B`|Campo normal final|nT|−1000 a 1000|
|`area`|Área efectiva calibrada|µm²|100 a 50 000|
|`amp`|Amplitud de tensión|µV|10 a 300|
|`offset`|Offset de tensión|µV|0 a 500|
|`I0`|Corriente crítica por unión|µA|1 a 50|
|`gain`|Ganancia por muestra|—|0,05 a 1,5|
|`range`|Rango del actuador|Φ₀|0,05 a 10|
|`sigma`|Ruido de tensión|µV|0 a 10|
|`duration`|Duración|s|0,01 a 1|
|`points`|Muestras|—|64 a 512|
|`priorLo` / `priorHi`|Rama previa|Φ₀|Cada extremo: −3 a 3|
|`cryo`|Estado criogénico|—|Operativo / no operativo|

La rama mínima debe ser menor que la máxima. La corriente `I0` modifica la curva crítica ideal, no toda la cadena de tensión.

### Fallos

* Saturación del actuador.
* Salto de flujo fuera de la rama local.
* Pérdida de bloqueo.
* Ambigüedad en lectura abierta.
* Estado criogénico no operativo.

Sin criogenia operativa se pueden mostrar transferencias teóricas, pero no una medida válida. No se inventa una curva universal de temperatura.

## 12\. Escenarios de infraestructuras

### Fuentes idealizadas

|Módulo|Fuente|Salida espacial|
|-|-|-|
|Átomos fríos|Contraste de masa puntual|Anomalía de gravedad o gradiente|
|OPM|Cable infinito o dipolo vertical|Módulo del campo del cable o componente del dipolo|
|NV|Cable infinito o dipolo vertical|Proyección magnética y separación ideal|
|SQUID|Dipolo vertical|Campo normal y flujo acoplado|

El usuario controla profundidad/separación y posición del sensor. Según el módulo, controla masa, corriente o momento dipolar.

La profundidad documentada va de 0,1 a 20 m y la posición de −20 a 20 m. Son rangos del escenario educativo, **no profundidades detectables certificadas**.

### Transferencia al laboratorio

El botón de transferencia utiliza el valor ideal del punto seleccionado como magnitud configurada del laboratorio. La adquisición posterior incorpora el modelo de señal y el ruido del laboratorio. Si el valor excede el rango permitido, se solicita ajustar el escenario.

El perfil no es una inversión geofísica. El cable no incluye retornos o blindajes; la masa y el dipolo puntuales no describen fielmente geometrías extendidas próximas.

## 13\. Experiencias guiadas

|Experiencia|Acción|Aprendizaje|
|-|-|-|
|1. Desplazar una franja|Variar anomalía de gravedad|La fase cambia la población|
|2. Rechazar ruido común|Comparar canales y residual|Cancelación parcial y ruido independiente|
|3. Medir precesión|Variar campo OPM|Frecuencia y módulo del campo|
|4. Provocar aliasing|Reducir/aumentar muestreo|Una FFT puede mostrar una frecuencia incorrecta|
|5. Desdoblar resonancias|Variar B y D|Separación frente a desplazamiento común|
|6. Solapar resonancias|Campo pequeño o ancho grande|Rechazo de una estimación no resuelta|
|7. Periodicidad de flujo|Ampliar/restringir rama previa|Ambigüedad de lectura abierta|
|8. Seguir flujo con FLL|Rampa, salto y rango|Seguimiento, saturación y pérdida de bloqueo|

Cada experiencia contiene pregunta, parámetros iniciales, acción, observación esperada y limitación. La observación esperada no sustituye la lectura de los resultados generados.

## 14\. Exportaciones

### CSV

* UTF-8 con BOM.
* Separador punto y coma.
* Coma decimal.
* Columnas de señal, ajuste y estimación según el módulo.
* Unidades incluidas en los nombres de columnas cuando están definidas en el motor.

El perfil espacial tiene su propia exportación CSV.

### JSON

Incluye configuración, semilla, versión del modelo, resumen, diagnósticos, señales y perfil. Es adecuado para conservar la trazabilidad de un experimento.

**No hay importación de JSON implementada en la interfaz.** La reproducción requiere introducir los parámetros manualmente o utilizar el código.

### PNG

La base exporta gráficos con título, ejes, unidades y leyenda. El actualizador no transforma los trazos o etiquetas de Canvas en objetos KaTeX. No debe confundirse la mejora de ecuaciones del DOM con una migración del motor de gráficos.

### Resumen imprimible

Abre una ventana con resultados, configuración, supuestos y gráficos. Permite imprimir o guardar mediante las opciones del navegador.

El actualizador añade el renderizado matemático y las fuentes al resumen de la versión compatible. Si el navegador bloquea la ventana, autorícela solo si la política de su organización lo permite.

### Coherencia

Una configuración inválida o un cálculo pendiente no debe exportar resultados anteriores como si fueran actuales. Los fallos pueden exportarse con estimación nula para su análisis.

## 15\. Arquitectura y estructura de archivos

### Paquete base documentado

```text
Q-SENSE-LAB/
├── ABRIR\_APLICACION.html
├── LEEME\_PRIMERO.txt
├── README.md
├── package.json
├── index.html
├── build.mjs
├── server.mjs
├── dist/
│   └── Q-SENSE-LAB.html
├── src/
│   ├── engine.mjs
│   ├── content.mjs
│   ├── app.mjs
│   ├── worker.mjs
│   └── style.css
├── docs/
│   ├── MODELOS.md
│   ├── ESCENARIOS.md
│   ├── REQUISITOS.md
│   ├── VALIDACION.md
│   ├── SEGURIDAD\_Y\_DATOS.md
│   ├── scenarios.json
│   └── manifest-sha256.json
└── tests/
    ├── engine.test.mjs
    ├── browser.test.py
    ├── numeric-results.txt
    ├── browser-results.json
    └── browser-artifacts/
```

El actualizador KaTeX se entregó como archivo separado. No se presupone que exista dentro de este ZIP.

### Responsabilidades

|Componente|Función|
|-|-|
|`engine.mjs`|Constantes, señales, ruido, estimadores, diagnósticos y perfiles|
|`content.mjs`|Explicaciones, controles, rangos, escenarios y referencias|
|`app.mjs`|Estado, navegación, controles, gráficos y exportación|
|`worker.mjs`|Ejecución de cálculos en segundo hilo del navegador|
|`style.css`|Diseño adaptable, temas y accesibilidad básica|
|`build.mjs`|Generación del HTML autónomo|
|`server.mjs`|Servidor local de desarrollo|

El Worker es procesamiento local durante el uso de la aplicación; no es un servicio remoto ni una entrega diferida. Existe un fallback local si no puede crearse el Worker.

## 16\. Desarrollo, compilación y despliegue

### Ejecutar scripts

Desde la carpeta extraída del proyecto:

```bash
npm run build
npm test
npm start
```

* `build`: genera `dist/Q-SENSE-LAB.html` e `index.html`.
* `test`: ejecuta las pruebas numéricas de Node.
* `start`: inicia el servidor local de desarrollo.

No se necesita `npm install` para dependencias de ejecución de la base, porque no se declararon paquetes externos.

### Servidor local

El servidor escucha en 127.0.0.1, puerto 8080 por defecto. Abra la dirección que imprime en la consola. Deténgalo con Ctrl+C.

Para cambiar el puerto en Ubuntu:

```bash
PORT=8090 npm start
```

En PowerShell:

```powershell
$env:PORT = "8090"
npm start
```

Estos comandos configuran la variable `PORT` que lee el servidor incluido. No convierten el servidor en un servicio de producción.

### Despliegue estático

* Para la base, publique el HTML autónomo de `dist`.
* Para la copia actualizada, publique `Q-SENSE-LAB\_KaTeX.html` generado localmente.
* Puede renombrar el HTML publicado a `index.html`.
* No requiere backend ni autenticación implementada por la aplicación.
* El alojamiento y los permisos deben estar autorizados por la organización.

### CSP

La distribución autónoma contiene scripts y estilos inline; el Worker utiliza una URL blob. Una política CSP restrictiva puede bloquearlos. No desactive controles corporativos para resolverlo.

La base modular es una alternativa para despliegues controlados, pero la actualización KaTeX entregada no migra automáticamente esa versión modular. La integración fuente con CSP específica requiere trabajo adicional.

## 17\. Pruebas y validación

### Aplicación base

En la entrega anterior se ejecutaron:

* **30 pruebas numéricas aprobadas.**
* **67 comprobaciones de navegador aprobadas.**
* Verificación adicional de la versión modular mediante HTTP.
* Verificación del ZIP mediante CRC y hashes SHA-256.

Los informes estaban incluidos en el paquete base. Estos resultados corresponden a esa entrega, no a una nueva ejecución completa después del parche KaTeX.

### Actualizador KaTeX

La prueba disponible utilizó una página de ensayo con las cadenas exactas de ecuaciones conservadas en el hilo:

|Comprobación|Resultado|
|-|-|
|Expresiones renderizadas|36|
|Errores de renderizado|0|
|Errores JavaScript en la prueba|0|
|Cambio dinámico de contenido|Probado|
|Resumen imprimible|Probado|
|Solicitudes HTTP/HTTPS durante la prueba|0|
|Versión KaTeX|0.16.27|

**No se probó la aplicación completa original en esa última fase.** No se debe sumar este ensayo a las pruebas base y presentarlo como una regresión integral de la aplicación actualizada.

### Repetir pruebas base

```bash
npm test
```

Para pruebas de navegador, el proyecto documentó Python, Playwright y Chromium:

```bash
python -m pip install playwright
python -m playwright install chromium
python tests/browser.test.py
```

La instalación de herramientas de prueba puede requerir internet y autorización. No es necesaria para utilizar el HTML autónomo. Si se usa un Chromium existente, la prueba acepta `CHROMIUM\_EXECUTABLE`.

### Revisión manual recomendada tras aplicar KaTeX

1. Abra los cuatro módulos y todas sus vistas.
2. Revise ecuaciones de bloque y fórmulas en textos.
3. Cambie nivel básico/técnico/avanzado.
4. Compruebe tema claro y oscuro.
5. Ejecute una medida y cambie parámetros.
6. Revise `QSLMathReport.errors`.
7. Abra el resumen imprimible.
8. Compruebe descargas y legibilidad en tableta.

Esta lista es una recomendación de aceptación, no una prueba ya ejecutada sobre el HTML original actualizado.

## 18\. Seguridad, privacidad y funcionamiento local

* La aplicación base calcula señales sintéticas localmente.
* El actualizador lee el HTML seleccionado en el navegador y genera una descarga local.
* El actualizador no sube el archivo a un servidor.
* KaTeX y sus fuentes están incorporados; no dependen de CDN.
* Los enlaces bibliográficos requieren conexión únicamente cuando se abren.
* El tema de la base se guarda en `localStorage` cuando está permitido.
* No hay importación ni tratamiento de inventarios reales implementados.

No introduzca datos confidenciales de activos reales en modificaciones del demostrador sin una revisión de seguridad y privacidad.

El servidor de desarrollo no está endurecido para producción y no debe exponerse a internet. La ausencia de backend no equivale a una auditoría de seguridad.

## 19\. Resolución de problemas

|Problema|Comprobación o acción|
|-|-|
|Página vacía al abrir `index.html`|Use el servidor local o el HTML autónomo de `dist`|
|No aparece la descarga KaTeX|Seleccione el HTML autónomo original, no el ZIP ni un lanzador|
|El actualizador indica incompatibilidad|No fuerce el parche: compruebe que sea la versión autónoma compatible|
|Se indica que KaTeX ya está incorporado|Use la copia original para regenerar; no aplique el parche dos veces|
|Una fórmula sigue como texto|Puede no estar en el catálogo o estar en Canvas/SVG; requiere revisión específica|
|Aparece un borde de error matemático|Revise `QSLMathReport.errors` y el LaTeX de la expresión|
|Las ecuaciones no se ven bien|Compruebe fuentes, zoom, estilos y políticas CSP|
|No abre el resumen|Revise el bloqueo de ventanas emergentes|
|Resultado vacío o guion|Revise estado, rango, señal y advertencias; puede ser un fallo deliberado|
|OPM muestra aliasing|Aumente muestreo o reduzca el campo residual dentro del modelo|
|NV no estima el campo|Separe resonancias, amplíe barrido o vuelva al dominio axial|
|SQUID pierde bloqueo|Revise salto, ganancia, rango y estado criogénico|
|Átomos muestra ambigüedad|Revise sensibilidad e intervalo previo; no elija una rama sin referencia|
|CSV abre en una sola columna|Importe usando punto y coma como separador y coma decimal|
|Cambiar velocidad no cambia la medida|Es el comportamiento esperado: reproducción y física son independientes|
|Tras recompilar desaparece KaTeX|La compilación base no integra el parche; vuelva a aplicar el actualizador|

No elimine las advertencias ni fuerce una estimación numérica cuando el modelo la rechaza.

## 20\. Limitaciones y requisitos pendientes

|Aspecto|Estado|
|-|-|
|Cuatro tecnologías y dos modalidades de átomos|Implementadas en la base|
|Señales y estimadores|Implementados con simplificaciones|
|Tiempo de integración óptica/ADC independiente|No implementado|
|Cronograma de pulsos|Representación simplificada|
|Mapa NV vectorial/2D|No implementado; perfil 1D|
|NV con cuatro orientaciones|Extensión opcional no implementada|
|3D|No implementado; esquemas 2D|
|Importación JSON|No implementada|
|React/TypeScript/Vite|No utilizados|
|Auditoría formal de accesibilidad|No realizada|
|Validación experimental|No realizada|
|Verificación nueva de referencias externas|No realizada|
|KaTeX en todos los textos posibles|No garantizado por el catálogo actual|
|KaTeX en Canvas/SVG|No incorporado automáticamente|
|Regresión completa tras el parche|Pendiente sobre el HTML original|
|Integración KaTeX en fuentes/build modular|No entregada como migración completa|

Los modelos omiten numerosos efectos instrumentales y ambientales. Las fuentes puntuales no representan toda la geometría del subsuelo. La sensibilidad de laboratorio no se convierte automáticamente en capacidad de detección de un activo.

## 21\. Mantenimiento y ampliaciones propuestas

Las siguientes son **propuestas**, no funciones existentes:

1. Migrar todas las fórmulas fuente a LaTeX explícito y eliminar la dependencia de correspondencias textuales.
2. Integrar KaTeX en el build y en la versión modular con recursos y licencias controlados.
3. Añadir pruebas de todas las vistas del HTML actualizado.
4. Revisar etiquetas matemáticas de gráficos y esquemas.
5. Corregir de forma explícita las convenciones dimensionales del residual SQUID.
6. Modelar tiempo de integración óptica/ADC separado.
7. Añadir importación validada de configuraciones JSON.
8. Desarrollar NV vectorial solo con suficientes proyecciones independientes.
9. Realizar revisión científica, auditoría de accesibilidad y pruebas multinavegador.

### Reglas de mantenimiento

* Mantener unidades y convenciones de signo documentadas.
* Separar generación, estimación y diagnóstico.
* No alimentar el estimador con la verdad para obtener un resultado favorable.
* Actualizar versión del modelo si cambian ecuaciones o criterios.
* Conservar semillas y escenarios de regresión.
* No presentar mejoras propuestas como funciones entregadas.
* Verificar licencias antes de redistribuir dependencias o fuentes.

## 22\. Glosario

|Término|Significado|
|-|-|
|OPM|Magnetómetro atómico bombeado ópticamente|
|NV|Centro nitrógeno-vacante en diamante|
|ODMR|Resonancia magnética detectada ópticamente|
|SQUID|Dispositivo superconductor de interferencia cuántica|
|FLL|Lazo de bloqueo de flujo|
|FFT|Transformada rápida de Fourier|
|FWHM|Anchura a media altura|
|T₂|Relajación transversal del modelo|
|µGal|10⁻⁸ m/s²|
|E|Eötvös: 10⁻⁹ s⁻²|
|Φ₀|Cuanto de flujo magnético|
|Aliasing|Representación de una frecuencia como otra por muestreo insuficiente|
|Rama|Solución dentro de una familia periódica|
|Contraste|Amplitud relativa de franja o resonancia|
|Dispersión|Variabilidad entre repeticiones|
|Inversión|Inferencia de un modelo a partir de observaciones|
|KaTeX|Motor de renderizado matemático utilizado por el actualizador|
|MathML|Representación estructurada de expresiones matemáticas|
|DOM|Estructura de elementos del documento web|
|CSP|Política de seguridad de contenido|
|Worker|Hilo de procesamiento del navegador|
|Datos sintéticos|Datos generados por modelos, no por sensores reales|

## 23\. Referencias, licencias y trazabilidad

### Referencias bibliográficas identificadas en el proyecto

* Stray et al. (2022), *Quantum sensing for gravity cartography*. [Referencia DOI](https://doi.org/10.1038/s41586-021-04315-3).
* Degen, Reinhard y Cappellaro (2017), *Quantum sensing*. [Referencia DOI](https://doi.org/10.1103/RevModPhys.89.035002).
* Budker y Romalis (2007), *Optical magnetometry*. [Referencia DOI](https://doi.org/10.1038/nphys566).
* Doherty et al. (2013), *The nitrogen-vacancy colour centre in diamond*. [Referencia DOI](https://doi.org/10.1016/j.physrep.2013.02.001).
* Clarke y Braginski, editores (2004), *The SQUID Handbook*, Wiley-VCH. Referencia bibliográfica sin enlace verificado en la entrega.

Los enlaces se conservan de la documentación previa. No se ha realizado una nueva verificación web de acceso o contenido. La búsqueda web estaba deshabilitada en el entorno de elaboración; el conocimiento general declarado llega hasta diciembre de 2025.

### Licencias

No se ha definido una licencia de redistribución para el código propio de la aplicación en las entregas documentadas. No presuponga que puede publicarse como software abierto sin una decisión del titular.

KaTeX y sus fuentes son recursos de terceros. Antes de redistribuir una versión pública, incorpore y verifique los avisos y licencias aplicables de la distribución utilizada. Este README no sustituye esos textos legales ni afirma que se hayan incluido todos los avisos en el actualizador.

### Trazabilidad de este README

Este documento se basa en los requisitos y el código descritos en el hilo, en los resultados de pruebas de la entrega base y en la inspección del actualizador KaTeX y su informe de ensayo. Los requisitos iniciales se utilizan como alcance deseado, no como prueba automática de implementación.

La aplicación base no estaba disponible para una nueva inspección integral al redactar este README. Por eso se separan los resultados históricos de la base, las comprobaciones del actualizador y las revisiones pendientes.

\---

**Regla de interpretación:** una presentación matemática mejorada no aumenta la validez física del modelo ni la precisión de una medida. Mantenga siempre visibles los supuestos y el carácter sintético de los resultados.

