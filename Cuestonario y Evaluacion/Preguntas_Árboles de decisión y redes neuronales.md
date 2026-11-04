# Preguntas - Árboles de decisión y redes neuronales multicapa

# Parte I. Conceptos y definiciones

## Pregunta 1

¿Qué es un árbol de decisión y cuál es su objetivo principal dentro de un problema de clasificación?

> Es un modelo que organiza decisiones mediante una estructura jerárquica de condiciones. Su objetivo principal en clasificación es tomar los datos de entrada de un ejemplo, hacerle preguntas sucesivas sobre sus variables y asignarle la clase o categoría correcta al llegar al final del camino.
> 

## Pregunta 2

Explique con sus propias palabras los siguientes elementos de un árbol de decisión:

- **Nodo raíz.**
- **Nodo interno.**
- **Rama.**
- **Hoja.**

> 
> 
> - **Nodo raíz:** Es el punto de inicio del árbol donde se hace la primera división evaluando la variable más informativa de todo el conjunto.
> - **Nodo interno:** Son las preguntas intermedias que siguen dividiendo los datos en subgrupos más específicos.
> - **Rama:** Es el camino que une un nodo con otro, es el resultado de la condición evaluada.
> - **Hoja:** Es el nodo final donde ya no hay divisiones.

## Pregunta 3

¿Qué es una red neuronal multicapa y qué función cumplen las siguientes capas?

- **Capa de entrada.**
- **Capa oculta.**
- **Capa de salida.**

> Es un modelo de aprendizaje compuesto por capas de neuronas interconectadas que procesan datos aplicando operaciones matemáticas y funciones no lineales para aprender patrones complejos.   
• **Capa de entrada:** Recibe los datos crudos del problema; tiene una neurona por cada característica de entrada.
• **Capa oculta:** Procesa y transforma la información combinando las señales previas para extraer patrones abstractos y no lineales.
• **Capa de salida:** Genera el resultado final del modelo, como una probabilidad, una clase o un valor numérico continuo.
> 

## Pregunta 4

¿Qué representan los pesos y los sesgos dentro de una red neuronal? Explique también por qué sus valores cambian durante el entrenamiento.

> • **Pesos:** Indican la fuerza o importancia que tiene cada entrada al conectarse con una neurona.
• **Sesgos:** Son términos independientes que permiten ajustar el umbral de activación de la neurona, desplazando la función sin importar si las entradas son cero.
Cambian durante el entrenamiento porque al inicio se fijan valores al azar; conforme la red comete errores al predecir, algoritmo como el descenso de gradiente calcula ese error y corrigen los pesos y sesgos paso a paso para que cada vez se equivoque menos.
> 

## Pregunta 5

¿Cuál es la principal diferencia entre la forma en que aprende un árbol de decisión y la forma en que aprende una red neuronal multicapa?

Explique qué elementos aprende cada modelo.

> 
> 
> - El **árbol de decisión** aprende dividiendo el espacio de forma discreta; busca umbrales en las variables mediante medidas de impureza y genera reglas condicionales fijas.
> - La **red neuronal multicapa** aprende optimizando parámetros continuos; ajusta numéricamente matrices de pesos y vectores de sesgo mediante derivadas (cálculo de gradientes) para aproximar una función matemática continua.

# Parte II. Análisis y aplicación

## Pregunta 6

Una institución bancaria desea desarrollar un sistema que detecte posibles compras fraudulentas.

El sistema dispone de información como:

- **Monto de la compra.**
- **Hora de la operación.**
- **Ciudad donde se realizó.**
- **Tipo de establecimiento.**
- **Número de compras realizadas durante el día.**
- **Historial de compras del cliente.**

Analice las ventajas y desventajas de utilizar un árbol de decisión y una red neuronal multicapa.

**¿Cuál utilizaría y por qué?**

> 
> 
> - **Árbol de decisión:**
>     - Ventajas: Es fácil de interpretar y de explicar al cliente o a reguladores financieros; maneja bien variables mixtas (texto y números) y entrena rápido.
>     - Desventajas: Sufre con datos desbalanceados (el fraude suele ser menos del 1%) y le cuesta capturar dependencias temporales complejas del historial.
> - **Red neuronal multicapa:**
>     - Ventajas: Excelente detectando combinaciones no lineales sutiles entre montos, horarios y patrones de gasto a gran escala.
>     - Desventajas: Funciona como caja negra (difícil justificar por qué se bloqueó una tarjeta) y requiere muchos datos y tiempo de cómputo.
> 
> **Elección:** Usaría la **red neuronal** si tengo millones de transacciones porque la prioridad es minimizar pérdidas por fraude no detectado. Si la ley me obliga estrictamente a explicar cada rechazo al usuario, optaría por el árbol o un ensamble basado en árboles.
> 

## Pregunta 7

Una escuela quiere detectar estudiantes que presentan riesgo de reprobar una materia.

Se conocen variables como:

- **Asistencia.**
- **Calificaciones.**
- **Tareas entregadas.**
- **Participación.**
- **Número de materias reprobadas anteriormente.**

Suponga que un árbol de decisión y una red neuronal obtienen prácticamente la misma precisión.

**¿Qué otros factores tomaría en cuenta para elegir uno de los dos modelos?** Justifique su respuesta.

> Elegiría el árbol de decisión. Al tener la misma precisión, los factores decisivos son:   
1. Interpretabilidad: El árbol permite ver exactamente la causa del riesgo, lo que permite a tutores y profesores diseñar una intervención pedagógica clara.
2. Volumen de datos y recursos: Las escuelas manejan registros relativamente pequeños, donde un árbol funciona de forma más estable sin sobreajustarse y sin requerir infraestructura pesada de cómputo.
> 

## Pregunta 8

Un hospital desarrolla un sistema para determinar qué pacientes necesitan atención prioritaria utilizando:

- **Edad.**
- **Temperatura.**
- **Presión arterial.**
- **Frecuencia cardiaca.**
- **Síntomas.**
- **Antecedentes médicos.**

Una red neuronal obtiene mejores resultados que un árbol de decisión, pero resulta más difícil explicar cómo obtuvo su respuesta.

**¿Considera que la mayor precisión es suficiente para elegir la red neuronal?**

Analice las consecuencias que podría tener esta decisión.

> **No considero que la precisión sea suficiente por sí sola.**   
Consecuencias: En medicina un error de clasificación puede costar vidas. Si el médico no entiende por qué el modelo tomó la decisión, no puede contrastarlo clínicamente ni asumir responsabilidad médica o legal en caso de una falla no advertida. En decisiones críticas, la transparencia y la confianza del personal de salud valen tanto o más que unos pocos puntos porcentuales de precisión global.
> 

## Pregunta 9

Una empresa de reparto quiere predecir si un pedido llegará tarde considerando:

- **Distancia.**
- **Tráfico.**
- **Clima.**
- **Hora del día.**
- **Cantidad de pedidos.**
- **Experiencia del repartidor.**

Para determinado pedido, el árbol de decisión indica:

**Llegará a tiempo.**

Mientras que la red neuronal indica:

**Probablemente llegará tarde.**

**¿Cómo determinaría cuál de los dos modelos está realizando una mejor predicción?**

Explique qué información adicional debería analizar.

> Analizaría la predicción en dos niveles:   
1. Probabilidad y calibración: La red entrega un valor continuo mientras que el árbol da una etiqueta dura, revisaría el nivel de certeza de ambos y su historial de error en condiciones similares.
2. Pruebas con datos históricos reales: Compararía cómo se comportaron ambos modelos en el pasado ante situaciones con ese mismo repartidor, ruta y condiciones climáticas, calculando métricas de precisión y recall sobre casos reales cerrados.
> 

## Pregunta 10

Una empresa desarrolla dos sistemas para decidir si una persona puede recibir un crédito.

El primer sistema utiliza un árbol de decisión y permite explicar claramente por qué una solicitud fue rechazada.

El segundo utiliza una red neuronal multicapa y obtiene mejores resultados de predicción, pero es más difícil explicar sus decisiones.

Si usted fuera responsable del proyecto:

- **¿Cuál de los dos modelos utilizaría?**
- **¿Qué ventajas tendría su elección?**
- **¿Qué riesgos tendría?**
- **¿Consideraría posible utilizar ambos modelos dentro del mismo sistema?**

Justifique ampliamente su respuesta.

> 
> 
> 
> Elección: Utilizaría un enfoque combinado (híbrido).
> 
> Ventajas de la elección: Permite aprovechar la alta capacidad predictiva de la red neuronal para evaluar el riesgo financiero real, mientras se apoya en reglas del árbol para garantizar la justificación legal requerida al cliente ante un rechazo.
> 
> Riesgos: La red neuronal puede aprender sesgos ocultos e injustos a partir de variables indirectas y generar problemas regulatorios si no se audita.
> 
> ¿Es posible usar ambos? Sí. La red neuronal puede clasificar los casos difíciles o estimar la probabilidad de impago, mientras que un árbol de decisión se encarga de definir los filtros iniciales de exclusión directa y generar los motivos explícitos de rechazo que exige la normativa.
>