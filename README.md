# tareaconceptos
Lenguajes y paradigmas de la programación

•	Variables estáticas:
Son propias únicamente de la clase y no de los objetos que pueden crearse de la misma, por lo tanto, sus valores son compartidos por todos los objetos de la clase. Van precedidas del modificador static.
Para invocar a una variable estática no se necesita crear un objeto de la clase en la que se define:
Si se invoca desde la clase en la que se encuentra definido, basta con escribir su nombre.
Si se le invoca desde una clase distinta, debe anteponerse a su nombre, el de la clase en la que se encuentra seguido del operador punto (.) <NombreClase>.variableEstatica
Suelen emplearse para definir constantes comunes a todos los objetos de la clase.
•	Tiempo de vida de una variable:
El tiempo de vida se refiere al intervalo de tiempo que trascurre desde que se crea la variable hasta que se destruye. En Java, una variable se crea en el momento que se ejecuta su declaración y se destruye cuando finaliza el bloque de instrucciones en donde fue declarada. Por ejemplo:
    if ( ... ) {
      println( ... );
      int n= 123; // (A)
      ...
      n= ...; // (B)
      ...
    } // (C)
La variable n se crea en el momento de ejecutar la instrucción (A) y se destruye al encontrar el final del bloque de instrucciones en (C). En (B) se asigna un nuevo valor a la variable n, que ya existía.
Un mismo identificador se puede usar para nombrar varias variables distintas. Por ejemplo en el siguiente código:
    {
      int x= a+b;
      ... x ...
    }
    {
      int x= fun(a,b);
      ... x ...
    }
En el código anterior, la variable x del primer bloque no tiene ninguna relación con la variable x del segundo bloque. Se trata de dos variables que se identifican por el mismo nombre. Se podría renombrar la variable x del segundo bloque por y, sin cambiar en nada la ejecución del programa.
Incluso, la declaración de una variable puede aparecer una sola vez en el programa, pero aún así servir para identificar varias variables durante la ejecución del programa. Esto se aprecia en el siguiente ciclo:
    while ( ... ) {
      ...
      double x= 3.14; // (A)
      ...
      x= ...;
      ...
    } // (C)
En cada iteración, en (A) se crea una nueva variable x que se destruye en (C), pero todas se llaman con el mismo nombre (x).
•	Memoria Dinámica 
Cuando trabajamos con variables, el compilador genera código máquina que se encarga de reservar memoria al comienzo de la ejecución y de liberarla al finalizar la misma. Cuando necesitamos trabajar con una serie de datos que no sabemos cuánto van a ocupar, por ejemplo con una estructura que variará con el número de jugadores de nuestro videojuego, no podemos reservar un vector (array o arreglo) para un número indeterminado.
Deberemos declarar un puntero y sobre dicho puntero, pedirle al sistema memoria suficiente conforme a nuestras necesidades. El sistema nos devolverá una dirección de memoria (que se almacenará en el puntero) y junto a la cuál (de forma correlativa) se encontrarán las demás posiciones del vector con el que vamos a trabajar.
•	Objeto
En el paradigma de programación orientada a objetos (POO, o bien OOP en inglés), un objeto es una unidad dentro de un programa de computadora que consta de un estado y de un comportamiento, que a su vez constan respectivamente de datos almacenados y de tareas realizables durante el tiempo de ejecución. Un objeto puede ser creado instanciando una clase, como ocurre en la programación orientada a objetos, o mediante escritura directa de código y la replicación otros objetos, como ocurre en la programación basada en prototipos.
•	Clase
En informática, una clase es una plantilla para la creación de objetos de datos según un modelo predefinido. Las clases se utilizan para representar entidades o conceptos, como los sustantivos en el lenguaje. Cada clase es un modelo que define un conjunto de variables -el estado, y métodos apropiados para operar con dichos datos -el comportamiento. Cada objeto creado a partir de la clase se denomina instancia de la clase.
•	Instancia
En el paradigma de la orientación a objetos, una instancia (en inglés, instance) se refiere a una realización específica de una clase o prototipo determinados.
En general, cuando se ejecuta un programa en un computador, se dice que éste se instancia. En lenguajes que crean objetos a partir de clases, un objeto es una instancia de una clase. Esto es, un miembro de una clase que tiene atributos en lugar de variables. En un contexto del mundo real, podríamos pensar en "Perro" como una clase y en un perro concreto es una instancia de esta clase. En este caso no nos importa la raza del perro. Si fuese de nuestro interés modelarla, y diferenciásemos entre un dóberman y un chihuahua, no solo cada instancia sería diferente, sino que pertenecerían a clases o prototipos diferentes, herencia (informática).
•	Herencia 
En programación orientada a objetos, la herencia es, después de la agregación o composición, el mecanismo más utilizado para alcanzar algunos de los objetivos más preciados en el desarrollo de software como lo son la reutilización y la extensibilidad. A través de ella los diseñadores pueden crear nuevas clases partiendo de una clase o de una jerarquía de clases preexistente (ya comprobadas y verificadas) evitando con ello el rediseño, la modificación y verificación de la parte ya implementada. La herencia facilita la creación de objetos a partir de otros ya existentes e implica que una subclase obtiene todo el comportamiento (métodos) y eventualmente los atributos (variables) de su superclase.
•	Sobrecarga 
Sobrecarga es la capacidad de un lenguaje de programación, que permite nombrar con el mismo identificador diferentes variables u operaciones.
En programación orientada a objetos la sobrecarga se refiere a la posibilidad de tener dos o más funciones con el mismo nombre pero funcionalidad diferente. Es decir, dos o más funciones con el mismo nombre realizan acciones diferentes. El compilador usará una u otra dependiendo de los parámetros usados. A esto se llama también sobrecarga de funciones.
También existe la sobrecarga de operadores que al igual que con la sobrecarga de funciones se le da más de una implementación a un operador.
•	Ensombrecimiento (Shadowing)
Se llama shadowing al hecho de que en una clase una variable miembro y una variable local definida en un método miembro, se llamen igual.












	class Persona{
        
    private String nombre="Elric de Melniboné";
     
    public String getNombre(){
        String nombre = "Mi nombre es ";
        nombre += this.nombre;
        return nombre;
    }
     
    public static void main(String[] args){
        System.out.println(new Persona().getNombre());
                  //Mi nombre es Elric de Melniboné }
}
•	Ciclo de vida de variables 
Variables de instancia (u objeto):
 Se crean cuando se crea el objeto que las contiene.
 Se inicializan por defecto si no se hace de modo explícito:
• 0 para números, "false" para booleano, "null" para objetos.
 Se destruyen cuando el recolector de basura de Java
no encuentra referencias activas para el objeto.
• Variables estáticas (o de clase):
 Se crean cuando la clase se usa por primera vez.
 Se inicializan por defecto si no se hace de modo explícito:
• 0 para números, "false" para booleano, "null" para objetos
– Suelen existir para el resto del programa (salvo que no esté cargado).
• Variables locales (o de bloque):
– Creadas en la sentencia en la que están definidas.
– No se inicializan por defecto. Contienen datos imprevisibles.
– Se destruyen al salir del bloque (en la llave final).
