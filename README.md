Actividad 1: Relaciones a partir del enunciado

1. ¿Qué relaciones deberían incorporarse al diagrama? Indique las clases involucradas, el tipo de relación y justifique su elección.
Préstamo y Socio — Asociación: Existe una asociación porque cada préstamo está relacionado con un socio. Esta información se guarda en el préstamo y se mantiene en el historial.
Préstamo y Libro — Asociación: También existe una asociación, ya que cada préstamo registra el libro correspondiente y conserva esa información en el historial.
Préstamo e Impresora — Dependencia:** El préstamo utiliza una impresora para generar el comprobante, pero no necesita guardarla como parte de sus atributos. Por eso, se considera una dependencia.

2. Para cada asociación propuesta, indique sus multiplicidades y explique qué significan en el caso.
Préstamo y Socio: Cada préstamo está asociado a un solo socio, mientras que un socio puede tener cero o muchos préstamos registrados a lo largo del tiempo.
Préstamo y Libro: Cada préstamo está asociado a un solo libro, pero un libro puede aparecer en cero o muchos préstamos a lo largo del tiempo, ya que puede ser prestado en distintas ocasiones.

3. ¿Bastaría representar todas las relaciones como dependencias para describir el caso? Justifique con el enunciado.
No, porque no todas las relaciones son temporales. En el caso del socio y el libro, el préstamo mantiene sus referencias y conserva esta información en el historial.
En cambio, la impresora solo se utiliza cuando se necesita imprimir el comprobante, sin que sea necesario guardarla dentro del préstamo.
Por lo tanto, corresponde representar las dos primeras relaciones como asociaciones y la última como una dependencia.

4. ¿Qué objetos debería guardar Préstamo como atributos? Justifique.
La clase Préstamo debería tener como atributos objetos de tipo "Socio" y "Libro", ya que necesita mantener la información del socio y del libro asociado a cada préstamo.
Esto permite conservar ambas referencias en el historial.

5. ¿Qué parámetros y tipos propondría para "devolver"? Explique para qué sirve cada uno.
Propondría los siguientes parámetros para el método "devolver":
"int diasAtraso": indica cuántos días de atraso tiene la devolución. Se utiliza para calcular la multa, considerando el cobro de $500 por cada día de atraso.
"Impresora impresora": corresponde a la impresora que se utilizará para imprimir el comprobante de devolución. Se recibe como parámetro porque solo se necesita durante
la ejecución del método y no es necesario almacenarla como atributo del préstamo.

Actividad 2: Relaciones en el código
1. ¿Dónde se reflejan las asociaciones y dependencias en el código? Señale los atributos o métodos, las clases involucradas y justifique cada relación.
Asociaciones: Se pueden identificar en los atributos "private Socio socio;" y "private Libro libro;" de la clase "Prestamo". Estos atributos mantienen las referencias al socio y
al libro relacionados con el préstamo.
Dependencia: Se observa en el parámetro "Impresora impresora" del método "devolver" y en la llamada al método "imprimir". Esto demuestra que "Prestamo" utiliza a "Impresora"
para generar el comprobante, sin necesidad de mantener una referencia permanente a ella como atributo.

2. ¿Cuántas asociaciones y dependencias hay entre las cuatro clases?
Entre las cuatro clases se identifican dos asociaciones: "Prestamo-Socio" y "Prestamo-Libro". Además, existe una dependencia entre "Prestamo" e "Impresora",
por lo que en total hay dos asociaciones y una dependencia.

3. ¿Existe una relación directa entre Socio y Libro? Justifique con el código.
No existe una relación directa entre "Socio" y "Libro", ya que ninguna de las dos clases mantiene atributos o referencias a la otra. Ambas se relacionan a través de "Prestamo",
que permite vincular a un socio con el libro que solicita.

4. ¿La clase Prestamo aplica SRP? Justifique según sus razones para cambiar y proponga una separación si la considera necesaria.
La clase "Prestamo" no cumple completamente con el Principio de Responsabilidad Única (SRP), porque se encarga de más de una tarea. Por una parte, maneja información y lógica relacionada con el préstamo,
como el cálculo de las multas. Por otra, también participa en la preparación e impresión del comprobante.
Para mejorar esto, se podría crear una clase encargada de generar e imprimir los comprobantes. De esta manera, "Prestamo" se concentraría en la información y las reglas del préstamo,
mientras que la nueva clase se ocuparía de la impresión. Así, cada clase tendría una responsabilidad más clara y sería más fácil mantener el código.
