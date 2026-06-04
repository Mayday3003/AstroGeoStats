# Fase I — Construcción del Modelo Geométrico Espacial del Complejo de Giza

## Introducción

La presente investigación busca evaluar rigurosamente la hipótesis de una posible relación geométrica entre la disposición espacial de las estructuras monumentales del complejo de Giza y determinadas configuraciones astronómicas. Para ello, resulta imprescindible construir un modelo geométrico cuantitativo que permita representar el sistema arqueológico mediante entidades matemáticas susceptibles de análisis estadístico, geométrico y físico.

Desde una perspectiva metodológica, toda hipótesis de alineamiento astronómico requiere inicialmente una descripción espacial objetiva del sistema observado. Las interpretaciones basadas exclusivamente en observaciones visuales o comparaciones gráficas carecen de robustez científica debido a que son altamente sensibles a cambios de escala, orientación, perspectiva y selección subjetiva de puntos de referencia.

Por esta razón, la primera etapa del proyecto consiste en transformar el complejo monumental de Giza en un conjunto formal de coordenadas geoespaciales sobre el cual puedan aplicarse herramientas de geometría computacional, estadística espacial y mecánica celeste.

---

# Obtención de datos geoespaciales

## Selección de la fuente cartográfica

La digitalización de las estructuras fue realizada a partir de imágenes satelitales georreferenciadas obtenidas mediante Google Earth Pro y posteriormente procesadas en QGIS.

La utilización de imágenes satelitales georreferenciadas responde a la necesidad de trabajar sobre observaciones reales de la superficie terrestre y no sobre representaciones esquemáticas o ilustraciones interpretativas. De esta forma, cada estructura arqueológica puede asociarse a coordenadas espaciales medibles y reproducibles.

El uso de una plataforma SIG (Sistema de Información Geográfica) garantiza además la trazabilidad metodológica del proceso, permitiendo que cualquier investigador reproduzca las mediciones empleadas en el estudio.

---

# Sistema de referencia espacial

## Justificación del uso de coordenadas UTM

Uno de los aspectos fundamentales de cualquier análisis geoespacial consiste en la elección adecuada del sistema de referencia.

Inicialmente, las imágenes satelitales se encuentran expresadas en coordenadas geográficas:

$$
(\lambda,\phi)
$$

donde:

* (\lambda) representa la longitud geográfica.
* (\phi) representa la latitud geográfica.

Aunque este sistema es adecuado para navegación y localización global, presenta limitaciones para el análisis geométrico debido a que sus unidades están expresadas en grados angulares y no en distancias físicas.

Por esta razón se adoptó el sistema:

$$
\text{WGS84 / UTM Zone 36N}
$$

correspondiente al código:

$$
EPSG:32636
$$

La elección de este sistema se fundamenta en que el complejo de Giza se encuentra ubicado dentro de la zona UTM 36 Norte, haciendo que las deformaciones cartográficas locales sean mínimas.

En este sistema, cada coordenada se expresa directamente en metros:

$$
P_i=(x_i,y_i)
$$

donde:

* (x_i) corresponde a la componente Este-Oeste.
* (y_i) corresponde a la componente Norte-Sur.

Esta característica permite que cualquier distancia calculada entre estructuras posea una interpretación física directa.

---

# Construcción de las entidades espaciales

## Digitalización de las pirámides

Las pirámides de Khufu, Khafre y Menkaure fueron representadas inicialmente mediante polígonos obtenidos a partir de la digitalización manual de sus contornos observables en imágenes satelitales.

La elección de polígonos en lugar de puntos responde a que una pirámide constituye una entidad espacial extendida y no una localización puntual.

Cada polígono representa una aproximación geométrica de la proyección horizontal de la estructura sobre el terreno.

---

# Obtención de centroides

## Fundamento matemático

Una vez construidos los polígonos, se calculó el centroide de cada uno de ellos.

El centroide constituye una de las herramientas más importantes de la geometría computacional y puede interpretarse como el centro geométrico de una figura.

Formalmente:

$$
C=(x_c,y_c)
$$

donde:

$$
x_c=\frac{1}{A}\int_A x,dA
$$

$$
y_c=\frac{1}{A}\int_A y,dA
$$

siendo (A) el área del polígono.

Desde una perspectiva física, el centroide puede entenderse como el punto donde se concentraría toda la masa de una lámina homogénea con la forma de la estructura.

La utilización de centroides permite transformar entidades espaciales complejas en puntos representativos preservando la localización general de cada monumento.

---

# Identificación de estructuras complementarias

Además de las tres pirámides principales, fueron identificadas otras estructuras relevantes para la hipótesis investigada:

* Gran Esfinge.
* Templo funerario asociado a Kefrén.
* Segunda referencia templaria utilizada en la hipótesis original.

Estas entidades fueron incorporadas como objetos puntuales debido a que la hipótesis inicial hace referencia explícita a posiciones específicas y no a superficies completas.

---

# Tratamiento de la incertidumbre espacial

## Caso de Mercurio

Uno de los aspectos metodológicamente más importantes del estudio surge de la identificación de la posición asociada al supuesto "Mercurio".

La referencia original no define una ubicación única, sino dos posibles localizaciones dentro del complejo funerario.

Por esta razón se definieron inicialmente dos puntos independientes:

$$
M_A
$$

$$
M_B
$$

preservando explícitamente la incertidumbre observacional.

Posteriormente se definirá un estimador inicial:

$$
M=\frac{M_A+M_B}{2}
$$

que corresponde al punto medio geométrico entre ambas localizaciones.

Sin embargo, las posiciones originales serán conservadas para futuros análisis de sensibilidad y simulaciones Monte Carlo.

---

# Construcción del conjunto espacial de estudio

Una vez identificadas todas las estructuras relevantes, el complejo arqueológico queda representado por el conjunto:

$$
\mathcal P=
{
Khufu,
Khafre,
Menkaure,
Sphinx,
Mercury
}
$$

Cada elemento posee coordenadas cartesianas definidas en metros dentro del sistema UTM.

Esta colección constituye la representación matemática fundamental del complejo de Giza para los análisis posteriores.

---

# Necesidad de un sistema de referencia interno

## Centroide global del complejo

Para estudiar relaciones espaciales es necesario definir un origen interno del sistema.

Con este propósito se calculará el centroide global:

$$
G_0
$$

definido como:

$$
G_0=
\left(
\frac{1}{N}\sum_{i=1}^{N}x_i,
\frac{1}{N}\sum_{i=1}^{N}y_i
\right)
$$

Este punto representa el centro geométrico del conjunto monumental.

Su importancia radica en que proporciona una referencia objetiva desde la cual medir:

* Distancias radiales.
* Orientaciones angulares.
* Simetrías espaciales.
* Configuraciones orbitales hipotéticas.

Desde una analogía física, (G_0) desempeña un papel similar al baricentro utilizado en mecánica celeste.

---

# Distancias espaciales

Una vez definido el sistema de referencia, se calculan las distancias euclidianas entre pares de estructuras:

$$
d_{ij}
=

\sqrt{
(x_i-x_j)^2
+
(y_i-y_j)^2
}
$$

Estas distancias constituyen magnitudes invariantes frente a rotaciones y traslaciones del sistema, razón por la cual representan uno de los descriptores geométricos más robustos disponibles.

La matriz de distancias obtenida contendrá toda la información métrica interna del complejo.

---

# Transformación a coordenadas polares

Con el objetivo de preparar el análisis astronómico posterior, cada estructura será representada respecto al centroide global mediante coordenadas polares:

$$
(r_i,\theta_i)
$$

donde:

$$
r_i
=

\sqrt{
(x_i-x_G)^2
+
(y_i-y_G)^2
}
$$

corresponde a la distancia radial.

Y:

$$
\theta_i
=

\arctan\left(
\frac{y_i-y_G}{x_i-x_G}
\right)
$$

representa la orientación angular.

Este sistema resulta especialmente adecuado para comparar configuraciones espaciales con modelos orbitales y distribuciones astronómicas.

---

# Importancia para los análisis estadísticos posteriores

La construcción del modelo geométrico constituye el fundamento de toda la investigación.

A partir de este sistema será posible:

1. Construir matrices de distancias y similitud espacial.
2. Evaluar relaciones de proporcionalidad geométrica.
3. Implementar simulaciones Monte Carlo.
4. Cuantificar incertidumbres observacionales.
5. Comparar configuraciones observadas con configuraciones aleatorias.
6. Estimar niveles de significancia estadística.
7. Desarrollar modelos de alineamiento astronómico.
8. Incorporar correcciones por precesión terrestre en etapas posteriores.

En consecuencia, esta fase transforma una hipótesis cualitativa basada en observaciones visuales en un problema cuantitativo susceptible de evaluación científica mediante herramientas de geometría computacional, estadística espacial y física matemática.

---

# Estado actual del proyecto

Al finalizar esta etapa se dispone de:

* Polígonos georreferenciados de las pirámides principales.
* Centroides espaciales de Khufu, Khafre y Menkaure.
* Localización georreferenciada de la Esfinge.
* Identificación de las posiciones candidatas para Mercurio.
* Sistema de coordenadas homogéneo en UTM (EPSG:32636).
* Base de datos espacial reproducible en QGIS.
* Archivos CSV exportables para análisis computacional.
* Infraestructura metodológica necesaria para iniciar la Fase II correspondiente a la reconstrucción astronómica y análisis estadístico avanzado.
