# Funciones y objetos
### Parámetros obligatorios

```
function nombreCompleto (nombre:string, apellido:string):string {
    return nombre + apellido;
}

console.log(nombreCompleto("clark", "kent"));

```

### Parámetros opcionales

En javascript por defecto, todos los parámetros son opcionales.

En typeScript, para que los parámetros sean opcionales, ponemos una ?

```
function nombreCompleto (nombre:string, apellido?:string):string {
    return nombre + apellido;
}

console.log(nombreCompleto("clark", "kent"));

```

### Parámetros por defecto

Esto es nuevo de EcmaScript6

```
function nombreCompleto (nombre:string, apellido:string, capitalizado:boolean = false):string {
    return nombre + apellido;
}

console.log(nombreCompleto("clark", "kent"));
console.log(nombreCompleto("clark", "kent", true));

```

### Parámetros REST

Cuando no sabemos cuántos parámetros vamos a recibir, usamos el operador ...

```
function nombreCompleto(nombre:string, ...losDemasParametros:string[]):string {
    return nombre + " " + losDemasParametros.join(" ");
}

console.log("Clark", "Kent");
console.log("Clark", "Joseph", "Kent");
```