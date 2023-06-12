PRUEBA TECNICA
Este documento es para hacer referencia a los errores encontrados en el código del proyecto ADIVINA EL NUMERO, a continuación, se detalla lo encontrado y realizado.
1.	La lógica y funciones del SCRIPT no se comunica con el HTML
Descripción	La clase lowOrHi No esta siendo tomada correctamente en el script, es por esa razón que el HTML no se comunica con el SCRIPT, en el SCRIPT al tomar la clase en el backend no se coloco de la forma correcta “.lowOrHi”

Criticidad del error	ALTA (no funciona la parte lógica del código en la aplicación)
Acción realizada	Se agrego el “.lowOrHi”, anteriormente solo estaba “lowOrHi”
Resultado del cambio	Exitoso
Descripción del resultado	La parte lógica del sistema ya es funcional en la aplicación

2.	Se permitían solo enteros de 0 a 10
Descripción	En la función let randomNumber = Math.random() * 10;
Solo se permitían enteros del 0 a 10
Criticidad del error	ALTA (la aplicación no cumplirá con especificaciones que se tenían)
Acción realizada	Se agrega var randomNumber = Math.floor(Math.random() * 100) + 1;
Que permitirá que la variable tome números enteros de 0 a 100
Resultado del cambio	exitoso
Descripción del resultado	El usuario ya puede ingresar números de 0 a 100

3.	Se tenia permitido 5 intentos para el usuario
Descripción	En la variable ATTEMPS se permitían solo 5 intentos para el usuario
Criticidad del error	ALTA (la aplicación no cumplirá con especificaciones que se tenían)
Acción realizada	Se cambio el valor de la variable a 10 intentos, const ATTEMPS = 10;

Resultado del cambio	exitoso
Descripción del resultado	El usuario ya tiene 10 intentos para adiviar el numero


4.	No se tenia declarado correctamente el Metodo addEventListener()
Descripción	El método estaba declarado de la siguiente manera, con error de sintaxis addeventListener()
Criticidad del error	ALTA (el backend de la aplicación no funcionaba correctamente)
Acción realizada	Se cambio la sintaxis del método, quedando asi: addEventListener()
Resultado del cambio	exitoso
Descripción del resultado	El programa tiene todas las funcionalidades solicitadas

5.	Los mensajes del evento ejecutado estaban cruzados
Descripción	La condición if (userGuess === randomNumber) {
            lastResult.textContent = '!!!Pérdistes!!!';
es incorrecta, pues la condición debe indicar que cuando el valor ingresado por el usuario es igual al número random del sistema, debe felicitar en el mensaje de respuesta
Criticidad del error	ALTA (El usuario no entendera el resultado y objetivo de la aplicación)
Acción realizada	Se cambia el mensaje para que la condición quede asi: if (userGuess === randomNumber) {
                    lastResult.textContent = '!!!ADIVINASTE!!!';

Resultado del cambio	exitoso
Descripción del resultado	El cliente entiendo cuando alcanzo lo esperado o cuando fracaso










6.	No esta condicionado para que el usuario ingrese solo números enteros
Descripción	En el codigo no se especifica que el usuario ingrese solo números enteros, por lo que el cliente puede ingresar cualquier tipo de dato, esta es la variable y parámetros: let userGuess = guessField.value;

Criticidad del error	ALTA (El usuario puede ingresar datos que puedan dar un resultado no esperado debido a que no esta parametrizado la data que ingresa)
Acción realizada	Se crea una condición y se parametriza la variable que toma el dato que el usuario ingresa, quedando asi: var userGuess = Number(guessField.value);

        if (typeof userGuess == "number" && !isNaN(userGuess)) {

            if (Number.isInteger(userGuess))

Resultado del cambio	exitoso
Descripción del resultado	Aunque el usuario ingrese una letra, se condiciona a que la aplicación opere solo Numeros enteros

