[![Open in MATLAB Online](https://www.mathworks.com/images/responsive/global/open-in-matlab-online.svg)](https://matlab.mathworks.com/open/github/v1?repo=l21211891-bit/MSFP5)

# Práctica 5.5: Modelo y control del sistema endócrino

## Información del estudiante

Africa Montserrat Rodriguez Garcia [C21211891]; [L21211891@tectijuana.edu.mx](mailto\:L21211891@tectijuana.edu.mx)

**Modelado de Sistemas Fisiológicos**

Ingeniería Biomédica

## Docente

Dr. Paul Antonio Valle Trujillo; [paul.valle@tectijuana.edu.mx](mailto\:paul.valle@tectijuana.edu.mx)

Departamento de Ingeniería Eléctrica y Electrónica, Tecnológico Nacional de México / Instituto Tecnológico de Tijuana, Blvd. Alberto Limón Padilla s/n, Tijuana, C.P. 22454, B.C., México.

---

## Descripción de la asignatura

El modelado de sistemas fisiológicos es una herramienta importante en Ingeniería Biomédica, ya que permite comprender el funcionamiento de diferentes procesos del cuerpo humano mediante modelos matemáticos y computacionales. A través de estos modelos es posible analizar el comportamiento de los sistemas biológicos, estudiar su respuesta ante distintos estímulos y diseñar estrategias de control que permitan mejorar su funcionamiento.

La asignatura de Modelado de Sistemas Fisiológicos tiene como propósito integrar conocimientos de fisiología, circuitos eléctricos, matemáticas y teoría de control para representar sistemas biológicos mediante modelos equivalentes. Estos modelos permiten realizar simulaciones numéricas, analizar la estabilidad de los sistemas y evaluar su comportamiento tanto en lazo abierto como en lazo cerrado.

Durante el curso se utilizan herramientas como MATLAB, Simulink y Python para desarrollar modelos matemáticos, obtener funciones de transferencia y diseñar controladores que permitan regular las respuestas de los sistemas fisiológicos.

## Objetivos

- Representar el funcionamiento del sistema endócrino mediante un circuito eléctrico equivalente RLC.
- Determinar el modelo de ecuaciones integro-diferenciales que describe el comportamiento del sistema.
- Obtener la función de transferencia a partir de las ecuaciones del circuito.
- Calcular el error en estado estacionario ante una entrada escalón unitario.
- Analizar el comportamiento del sistema en condiciones de control y caso.
- Simular la respuesta del sistema en lazo abierto utilizando MATLAB, Simulink o Python.
- Diseñar un controlador PID que permita reducir o eliminar el error en estado estacionario.
- Comparar las respuestas del sistema en lazo abierto y en lazo cerrado durante un tiempo de simulación de 10 segundos.

## Descripción detallada del sistema

El sistema endócrino es el encargado de regular diferentes funciones fisiológicas del organismo mediante la producción y liberación de hormonas. Estas sustancias son secretadas por glándulas endócrinas y transportadas a través del torrente sanguíneo hasta llegar a órganos o tejidos específicos, donde generan una respuesta biológica.

Entre las funciones reguladas por este sistema se encuentran el metabolismo, el crecimiento, la reproducción, la respuesta al estrés y el mantenimiento de la homeostasis.

En esta práctica se representa de manera simplificada la dinámica hormonal mediante un circuito eléctrico RLC de segundo orden. La analogía eléctrica permite estudiar los procesos de secreción, transporte, acumulación y respuesta hormonal utilizando componentes eléctricos que representan distintas características fisiológicas.

La fuente de voltaje Ve(t) representa el estímulo inicial que provoca la secreción hormonal. La resistencia R1 modela las pérdidas y la oposición al transporte hormonal a través del torrente sanguíneo. El capacitor C representa la acumulación temporal de hormonas en los tejidos o compartimentos intermedios.

Por otra parte, la resistencia R2 representa la oposición del órgano diana a la respuesta hormonal, mientras que la inductancia L modela la inercia biológica, es decir, la resistencia a cambios rápidos en la respuesta del tejido.

La señal de salida Vs(t) representa la respuesta hormonal efectiva del sistema. También se consideran dos flujos principales: Fe(t), correspondiente a la secreción hormonal, y Fs(t), que representa la absorción hormonal por el órgano diana.

El circuito se analiza utilizando una entrada escalón unitario, que representa un estímulo sostenido aplicado al sistema. A partir de esta entrada se estudian las características dinámicas de la respuesta, como el tiempo de establecimiento, el amortiguamiento, la estabilidad y el error en estado estacionario.

Para evaluar el comportamiento del modelo se consideran dos condiciones de funcionamiento: control y caso. Ambas mantienen la misma estructura del circuito, pero presentan diferentes valores de resistencia y capacitancia, lo que permite observar cómo estos parámetros modifican la dinámica hormonal.

### Parámetros del sistema

| Componente | Control | Caso   |
| ---------- | ------- | ------ |
| R1         | 1 kΩ    | 1 kΩ   |
| L          | 100 mH  | 100 mH |
| R2         | 100 kΩ  | 1 kΩ   |
| C          | 1 F     | 1000 F |

Los valores de R2 y C permiten estudiar cómo las modificaciones en la resistencia y en la capacidad de almacenamiento afectan la respuesta del sistema endócrino.

## Modelo matemático

El modelo matemático se obtiene aplicando las leyes de Kirchhoff al circuito eléctrico equivalente.

La corriente de entrada Fe(t) se divide entre la rama capacitiva y la rama formada por la resistencia R2 y la inductancia L.

La ecuación de corriente en el nodo principal es:

Fe(t) = C · dVs(t)/dt + Fs(t)

La relación entre el voltaje de entrada y el voltaje de salida es:

Ve(t) = R1 · Fe(t) + Vs(t)

Para la rama formada por R2 y L:

Vs(t) = R2 · Fs(t) + L · dFs(t)/dt

Estas expresiones permiten describir el comportamiento dinámico del circuito y establecer el sistema de ecuaciones diferenciales correspondiente.

### Función de transferencia

Aplicando la transformada de Laplace a las ecuaciones del circuito, considerando condiciones iniciales nulas, se obtiene la relación entre el voltaje de salida y el voltaje de entrada:

G(s) = Vs(s) / Ve(s)

La función de transferencia del sistema es:

**G(s) = (Ls + R2) / [R1LCs² + (L + R1R2C)s + (R1 + R2)]**

Esta expresión representa un sistema de segundo orden, cuya dinámica depende de los valores de las resistencias, la inductancia y la capacitancia.

A partir de esta función se pueden analizar los polos del sistema, determinar su estabilidad y evaluar la respuesta ante diferentes estímulos.

### Error en estado estacionario

El error en estado estacionario permite determinar la diferencia entre la entrada de referencia y la respuesta final del sistema.

Para una entrada escalón unitario y considerando el error de seguimiento:

e(t) = 1 - Vs(t)

El error en estado estacionario se calcula mediante:

ess = 1 - G(0)

Sustituyendo la función de transferencia:

**ess = R1 / (R1 + R2)**

Para la condición control:

ess = 1000 / (1000 + 100000)

**ess = 0.009901**

Para la condición caso:

ess = 1000 / (1000 + 1000)

**ess = 0.5**

Estos resultados indican que la condición control presenta un error final menor, mientras que la condición caso presenta una diferencia más significativa entre la referencia y la salida.

Por esta razón se considera la implementación de un controlador en lazo cerrado para mejorar el seguimiento de la referencia en la condición caso.

## Simulación y control del sistema

Las simulaciones se realizan durante un intervalo de 10 segundos utilizando una entrada escalón unitario.

En primer lugar, se analiza la respuesta en lazo abierto para las condiciones control y caso, utilizando las funciones de transferencia correspondientes.

Posteriormente, se implementa un controlador PID en lazo cerrado para mejorar la respuesta del sistema en la condición caso.

El controlador utiliza el error entre la señal de referencia y la salida del sistema para generar una acción de control.

Su expresión general es:

u(t) = Kp·e(t) + Ki·∫e(t)dt + Kd·de(t)/dt

Donde Kp representa la ganancia proporcional, Ki la ganancia integral y Kd la ganancia derivativa.

La acción proporcional responde al error presente, la integral permite eliminar el error constante en condiciones adecuadas de estabilidad y la derivativa ayuda a anticipar los cambios en la respuesta.

El objetivo es obtener una respuesta estable que siga la señal de referencia, reduciendo el error en estado estacionario del sistema.

## Palabras clave

Sistema endócrino; Circuito RLC; Modelo matemático; HAZ ; Ecuaciones diferenciales; Controlador PID; Lazo abierto; Lazo cerrado; Simulaciones numéricas; Ingeniería Biomédica.

## Lista de archivos incluidos en el repositorio

- Cuaderno computacional de MATLAB [.mlx].
- Modelo de Simulink [.slx].
- Archivos de simulación en Python [.py].
- Diagrama del circuito eléctrico equivalente.
- Imagen del modelo fisiológico realizado en BioRender.
- Imagen con los parámetros del controlador PID.
- Gráficas de las simulaciones en lazo abierto y lazo cerrado [.pdf y .png].

## Referencias

[1] P. A. Valle, *Syllabus para Modelado de Sistemas Fisiológicos*, Tecnológico Nacional de México / Instituto Tecnológico de Tijuana, Tijuana, B.C., México, 2025. Permalink: [https://biomath.xyz/course/](https://biomath.xyz/course/)

[2] M. C. Khoo, *Physiological Control Systems: Analysis, Simulation, and Estimation*, 2nd ed. Piscataway, New Jersey, USA: IEEE Press, 2018.

[3] N. S. Nise, *Control Systems Engineering*, 8th ed. Hoboken, New Jersey, USA: John Wiley & Sons, 2020.
