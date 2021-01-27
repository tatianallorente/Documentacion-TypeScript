### TypeScript

Instalar TypeScript (primero es necesario npm):

`sudo npm install -g typescript`

<br>
Comprobar la versión instalada:

`tsc -version`

<br>
Compilar archivo (posicionados en la carpeta donde está)
Esto convierte nuestro archivo .ts en un archivo .js por lo que le tendriamos dos veces:

`tsc nombreArdchivo`

<br>
Entrar en el modo observador/watcher para que esté pendiente de cada vez que hacemos un cambio y lo compile automáticamente:

`tsc nombreArchivo.ts --w`

### Watcher para todos los archivos:

Este comando crea el archivo tsconfig.json:

`tsc -init`

Para hacer watcher a todos los archivos con extension ts:

`tsc *.ts -w` _// En Windos no funciona_

`tsc  -w`

<br>

Las opciones que ponemos en el archivo de configuración _tsconfig.json_ también se pueden poner en el comando de compilación.

Por ejemplo, la propiedad _"removeComments"_, también podriamos hacerlo:

`tsc app.js --removeComments`

### Concatenar texto
En vez de hacer como antes:

`console.log("Los héroes son " + batman + " y " + superman);`

Ahora usamos el string literal:

```console.log(`Los héroes son ${batman} y ${superman}`);```

Este código será convertido al antiguo, y además reemplaza las tildes por su caracter html.

`Los h\u00E9eroes`





