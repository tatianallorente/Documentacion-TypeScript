
# Tipos personalizados

### Objetos con tipos específicos

Da igual el orden de las propiedades, pero el tipo y el nombre tiene que coincidir.

```
let flash: { nombre:string, edad:number, poderes:string[] } = {
    nombre: "Barry Allen",
    edad: 24,
    poderes: ["Puede correr muy rápido]
};
```

### Métodos dentro de los objetos

```
let flash: { nombre:string, edad:number, poderes:string[], getNombre:()=>string } = {
    nombre: "Barry Allen",
    edad: 24,
    poderes: ["Puede correr muy rápido],
    getNombre() {
        return this.nombre;
    }
};
```

### Tipos personalizados

Si queremos cambiar el tipo de alguna propiedad, por ejemplo, tendríamos que cambiarlo uno a uno en todos los objetos.

```
let flash: { nombre:string, edad:number, poderes:string[], getNombre:()=>string } = {
    nombre: "Barry Allen",
    edad: 24,
    poderes: ["Puede correr muy rápido],
    getNombre() {
        return this.nombre;
    }
};

let superman: { nombre:string, edad:number, poderes:string[], getNombre:()=>string } = {
    nombre: "Clark Kent",
    edad: 500,
    poderes: ["Puede volar],
    getNombre() {
        return this.nombre;
    }
};
```

Para solucionar esto, existen los tipos personalizados.

Podemos hacer un "molde" usando la palabra _type_ y el nombre suele ser con la primera letra en mayúscula para saber que es una clase, no una variable.

```
type Heroe = {
    nombre:string, 
    edad:number, 
    poderes:string[], 
    getNombre:()=>string
}

let flash:Heroe = {
    nombre: "Barry Allen",
    edad: 24,
    poderes: ["Puede correr muy rápido],
    getNombre() {
        return this.nombre;
    }
};

let superman:Heroe = {
    nombre: "Clark Kent",
    edad: 500,
    poderes: ["Puede volar],
    getNombre() {
        return this.nombre;
    }
};
```

### Permitir varios tipos

`let a: string | number | Heroe = "hola";`

`a = 10;`

### Saber el tipo

```
let cosa:any = 123;
console.log(typeof cosa);
```

