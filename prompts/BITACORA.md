# Bitacora de tecnicas avanzadas

Laboratorio 07: Tecnicas Avanzadas de Prompting.

Herramienta de IA usada: ChatGPT

## Ejercicio 2: Zero-shot, one-shot y few-shot

| Tipo | Aciertos (de 5) | Formato de la respuesta | Todas con el mismo formato (Si/No) |
|------|-----------------|-------------------------|-----------------------------------|
| Zero-shot |NO |DESIGUAL |SI PERO NO ERA EL FORMATO |
| One-shot |SI |ESTRUCTURAL |SI |
| Few-shot |SI |ESTRUCTURAL |SI |

## Ejercicio 3: Chain of Thought

| Pedido | Respuesta de la IA | Muestra los pasos (Si/No) | Correcta (Si/No) |
|--------|--------------------|---------------------------|------------------|
| Directo |CORRECTO |NO |SI |
| Paso a paso |CORRECTO |SI | SI|

## Ejercicio 4: Role prompting

| Version | Vocabulario (sencillo/tecnico) | Usa ejemplos o codigo | A quien le sirve mas |
|---------|-------------------------------|-----------------------|---------------------|
| A. Sin rol | Intermedio | Ejemplos sencillos | Estudiantes en general |
| B. Rol docente | Sencillo | Ejemplos de la vida diaria (una caja con etiqueta) | Principiantes que nunca programaron |
| C. Rol senior | Tecnico | Codigo Java | Programadores con experiencia |
## Ejercicio 5: Descomposicion

**Paso 1:** la IA listo 5 requisitos del sistema: registrar productos, actualizar el stock, buscar productos, registrar entradas y salidas, y mostrar un reporte del inventario.

**Paso 2:** la IA diseno las clases necesarias, como Producto, Categoria e Inventario, cada una con sus atributos y tipos de dato.

**Paso 3:** la IA escribio el codigo de la clase Producto con sus atributos, un constructor y los metodos get y set.

**Paso 4:** la IA propuso 3 mejoras para la clase Producto, como validar que el precio y el stock no sean negativos y agregar un metodo toString().


## Ejercicio 6: Prompt estructurado y autocritica

## Ejercicio 6: Prompt estructurado y autocritica

Prompt basico:

```text
Dame casos de prueba para un login.
```

Prompt estructurado:

```text
<rol>Actua como analista de pruebas de software.</rol>
<contexto>Login web con correo y contrasena. La cuenta se bloquea despues de 3 intentos fallidos.</contexto>
<tarea>Piensa paso a paso que puede fallar y escribe 6 casos de prueba.</tarea>
<formato>Tabla con las columnas: ID, escenario, datos de entrada, resultado esperado.</formato>
```

Tabla generada con el prompt estructurado:

| ID | Escenario | Datos de entrada | Resultado esperado |
|---|---|---|---|
| CP-01 | Inicio de sesion con credenciales validas | Correo registrado y contrasena correcta; cuenta sin bloqueo | Se permite el acceso a la cuenta. |
| CP-02 | Campos obligatorios vacios | Correo vacio y/o contrasena vacia | Se solicita completar los campos obligatorios y no se permite el acceso. No se contabiliza un fallo de autenticacion. |
| CP-03 | Formato de correo invalido | Correo: usuario@; contrasena cualquiera | Se indica que el formato del correo es invalido y no se permite el acceso. No se contabiliza un fallo de autenticacion. |
| CP-04 | Primer y segundo intento fallidos | Correo registrado; contrasena incorrecta en dos intentos consecutivos | Ambos intentos se rechazan. La cuenta permanece desbloqueada y acumula dos fallos. |
| CP-05 | Bloqueo en el tercer intento fallido | Cuenta con dos fallos consecutivos; correo registrado y contrasena incorrecta | Se rechaza el acceso y la cuenta queda bloqueada al alcanzar el tercer fallo. |
| CP-06 | Acceso con contrasena correcta despues del bloqueo | Cuenta bloqueada tras tres fallos; correo registrado y contrasena correcta | Se rechaza el acceso y la cuenta permanece bloqueada hasta cumplir el mecanismo de desbloqueo definido. |

Mensaje de autocritica:

```text
Revisa tu tabla: faltan casos limite como campos vacios, correo sin @ o contrasena con espacios? Agrega los que falten e indica cuales agregaste.
```

Tabla despues de la autocritica (casos agregados):

| ID | Escenario | Datos de entrada | Resultado esperado |
|---|---|---|---|
| CP-07 (nuevo) | Correo sin @ | Correo: usuariodominio.com; contrasena cualquiera | Se informa que el formato del correo es invalido y no se permite el acceso. |
| CP-08 (nuevo) | Contrasena compuesta solo por espacios | Correo registrado; contrasena: "   " | Se rechaza el acceso. La validacion y el conteo del fallo deben ajustarse a la politica definida. |
| CP-09 (nuevo) | Contrasena correcta con espacios adicionales | Correo registrado; contrasena valida Clave123! escrita como " Clave123! " | Si los espacios se consideran caracteres, se rechaza el acceso y se cuenta un fallo. Debe confirmarse si el sistema elimina espacios antes de autenticar. |

