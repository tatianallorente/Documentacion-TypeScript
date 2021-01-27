# EcmaScript6

### let

Para declarar variables. A diferencia de *var*, let mantiene su valor dentro de su scope o bloque de código.

    let a = 10;
    console.log(a);  // output 10
    if(true){
        let a = 20;
        console.log(a); // output 20
    }
    console.log(a);  // output 10

### const

Para declarar constantes. No podemos reasignar su valor.

### Templates literales

    ```
    let mensaje = `${nombre1} ${nombre2};`

    let mensajeCompleto = `Puede ser
    multilinea
    y podemos poner variables ${nombre1}
    junto con el texto 
    sin tener que concatenar ${nombre2}
    `;
    ```

### Funciones de flecha

    ```
    function sumar(a,b) {
        return a + b;
    }
    console.log(sumar(2,3));
    ```

    Podemos convertirlo en:

    ```
    let sumar = (a,b) => a+b;
    console.log(sumar(2,3));
    ```
### Destructuración de objetos

Si tenemos este objeto:

    ```
    let avengers = {
        nick: "Samuel Jackson",
        ironman: "Robert Dowey Jr",
        vision: "Paul Bettany"
    };
    ``` 

Para obtener cada valor por separado en variables, tendríamos que hacer:

    ```
    let nick = avenges.nick;
    let ironman = avenges.ironman;
    let vision = avenges.vision;

    console.log(ironman);
    ```

Para evitar tener que escribir todo esto, hacemos destructuring:

    ```
    let { nick, ironman, vision } = avengers;
    console.log(ironman);
    ```

Además si después queremos cambiar el nombre de alguna de esas variables:

    ```
    let { nick, ironman:warmachine, vision } = avengers;

    console.log(warmachine);
    ```

### Destructuración de arrays

Si tenemos este array:

    ```
    let avengers = [
        "Samuel Jackson",
        "Robert Dowey Jr",
        "Paul Bettany"
    ];
    ``` 
Podemos hacer:

     ``` 
    let [avenger1, avenger2, avenger3] = avengers;
    console.log(avenger2);
     ``` 

Pero siempre tenemos que indicar todos los elementos del array (en este caso 3).

Si por ejemplo, solo queremos el tercer elemento del array, podemos hacer esto:

     ``` 
    let [ , , avenger3] = avengers;
    console.log(avenger3);
     ``` 


### Nuevo bucle - For OF

El bucle _for in_ es útil para iterar sobre las propiedades de los objetos, pero para iterar sobre objetos iterables como arrays, podemos usar mejor el _for of_.

    ```
    let thor = {
        nombre: "Thor",
        arma: "Mjolnir"
    }

    let capitan = {
        nombre: "Capitan America",
        arma: "Escuro"
    }

Bucle _for_ normal:

    for (let i = 0; i <= avengers.length; i++) {
        let avenger = avengers[i];
        console.log(avenger.nombre);
    }

Bucle _for of_:

    for ( let avenger of avengers) {
        console.log(avenger.nombre);
    }

    ```

### Clases 

    ```
    class Avenger {
        constructor(nombre, poder) {
            this.nombre = nombre;
            this.poder = poder;
        }
    }

    // Esta clase hereda de la clase Avenger
    class AvengerVolador extends Avenger {
        constructor(nombre, poder) {
            super(nombre, poder);
            this.vuela = true;
        }
    }

    let hulk = new Avenger("Hulk", "Super fuerza");
    let falcon = new AvengerVolador("Falcon", "Volar!!");

    console.log(hulk);
    console.log(falcon);
    ```