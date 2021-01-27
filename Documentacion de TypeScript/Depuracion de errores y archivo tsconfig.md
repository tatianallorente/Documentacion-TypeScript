# Depuración de errores y archivo tsconfig.json

- Aunque el compilador muestre un error, el archivo se compila a .js igualmente.

### Archivo tsconfig.json

_https://www.typescriptlang.org/docs/handbook/tsconfig-json.html_

- Se crea cuando en la carpeta del proyecto ejecutamos _tsc -init_

- En target indicamos la versión de javascript a la que queremos convertir nuestro código: es5, es6...

- _noImplicitAny_ Sirve para que cuando no especifiquemos una propiedad, sea de tipo _any_. Si lo ponemos a true, mostrará un error cuando declaremos una variable con el tipo _any_ implícitamente.

- _strictNullChecks_ No te permite asignar valores undefined o null

### Depurar código TypeScript

En el archivo de configuración _tsconfig.json_ en las _compileOptions_ ponemos la propiedad _"SourceMap"_ a _true_.

Ahora, cuando se compilen los archivos, se creará un archivo _.map_

Desde el inspector del navegador, vamos a sources y en el archivo _.js_ veremos que al final hay un comentario como este:

`//# sourceMappingUrl = miArchivo.js.map`

Veremos que aparece nuestro archivo con la extensión _.ts_ y en ese archivco, podemos añadir breakpoints y depurar el código. (Similar que el debugger de php de visual studio)

### Eliminar los comentarios del código javascript final

En el archivo de configuración _tsconfig.json_ en las _compileOptions_ ponemos la propiedad _"removeComments"_ a _true_.

Si hay algún comentario en concreto que sí queremos que aparezca, lo indicamos con una exclamación:

```
/*!
Este es un
comentario
multilinea
*/
```

### Incluir/excluir archivos y carpeta

Por ejemplo, cuando no queremos compilar la carpeta _node-modules_

En el archivo de configuración _tsconfig.json_ ponemos la propiedad _"include"_

(** son todas las carpetas)

(* son todos los archivos)

```
"include": [
    "app/**/*"
],
"exclude": [
    "node_modules",
    "src/"
]
```

### Outfile

Si por ejemplo en nuestro _index.html_ estamos llamando a 3 archivos:

```
<script src="app1.js></script> 
<script src="app2.js></script> 
<script src="app3.js></script> 
```

La página tiene que llamar y descargar cada uno de esos 3 archivos uno por uno, y no es eficiente.

Con typeScript podemos generar un único archivo de salida que combine todos esos archivos.

`tsc --outFile nombreArchivo.js app1 app2 app3`

Ahora, en el _index.html_ sólo tendríamos que incluir:

```
<script src="nombreArchivo.js></script>
```

Si no queremos hacer esto desde la línea de comandos, podemos añadirlo al _tsconfig.js_ en las _compileOptions_ :

```
"outFile": "build/nombreArchivo.js"
```

### Cambiar la versión de javascript al momento de traducir

Si por ejemplo, en el _tsconfig_ tenemos en _target_ _es6_ y por lo que sea queremos compilar un archivo en _es5_, podemos sobreescribirlo desde la terminal:

`tsc app.ts --target es5`


 