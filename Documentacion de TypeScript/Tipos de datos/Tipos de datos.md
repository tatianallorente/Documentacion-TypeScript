
# Tipos de datos
Al crear una variable, le ponemos el tipo:

`let esSuperman:boolean = true;`

Si no inicializamos la variable, el valor será _undefined_:

`let villanos:number;`

Aunque no le digamos el tipo de dato, en el momento que le pongamos un valor, entenderá que ese es su tipo, y si despué  s le cambiamos el valor por otro de otro tipo, dará error:

`let otros = 3;`

Si lo cambiamos por esto, dará error, porque entiende que debería ser un número:

`otros = 'hola';`

Como establecemos el tipo de datos, cuando queremos llamar a una función de javascript, al poner el punto, el vscode nos muestra la lista de funciones posibles para esa variable:

```
let batman:string = "Batman";

batman.funcionesDeString();

también sirve para los arrays, me mostraría las funciones para arrays. Y si llamo a uno de los valores del array que por ejemplo, son strings, me mostrará las funciones de strings.

heroes.funcionesDeArrays

heroes[1].funcionesDeStrings
```

### Any

Existe el tipo `any`, y es el que se usa cuando no declaramos el tipo a una variable. También podemos asignarselo nosotros a una variable.

Si aisgnamos any a un array, no es necesario poner los [];

    let arr:any = [1,2,3,4,5,6,7,8,9,10]; 


### Arrays

Para indicar el tipo de datos que tendrá un array lo hacemos así:

`let miArray:number[] = [1,2,3,4];`

### Varios tipos
También podemos asignar varios tipos a nuestras variables:

`let heroe:[string, number] = ["superman", 100];`

### Void
El tipo void se usa para las funciones que no tienen return.

### Casting
Aserciones de tipo, es como castear:

`let algo:any = "lo que sea";`

`let largoDelString:number = (<string>algo).length;`

`console.log(largoDelString);` // Muestra 10 
