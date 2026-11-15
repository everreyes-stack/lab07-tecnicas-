# Tarea: Mi prompt avanzado

## Tarea elegida

Disenar las clases de un sistema de notas en Java para registrar estudiantes, cursos y calcular el promedio de cada estudiante.

## Version 1: prompt basico

```text
Crea un sistema de notas.
```

**Resultado:** la IA empezo a crear una aplicacion web grande y tardo mucho en responder, porque el pedido era muy general.

## Version 2

```text
Actua como programador Java. Crea un sistema de notas en Java para registrar estudiantes, cursos y calcular el promedio de cada estudiante.
```

**Resultado:** agregue un rol porque en la version 1 la IA no sabia que lenguaje usar. Ahora hizo el sistema en Java con clases como Estudiante y Curso, pero entrego todo el codigo junto y sin explicar el diseno.

## Version 3: prompt final

```text
<rol>Actua como programador Java que disena sistemas para institutos.</rol>
<contexto>Necesito un sistema de notas en Java para registrar estudiantes, cursos y calcular el promedio de cada estudiante. Las notas van de 0 a 20 y se aprueba con 11 o mas.</contexto>
<tarea>Hazlo por pasos:
1. Lista las clases necesarias.
2. Para cada clase indica sus atributos con su tipo de dato.
3. Escribe el codigo Java de la clase Estudiante con un metodo calcularPromedio().
4. Revisa tu codigo y corrige lo que falte.</tarea>
<formato>Responde con un titulo por cada paso y una tabla para las clases y sus atributos.</formato>
```

**Resultado:** agregue etiquetas, pasos y una revision final porque en la version 2 todo salia junto. Ahora la IA respondio en orden: clases, tabla de atributos, codigo de Estudiante y revision de su propio codigo.

## Tecnicas usadas en el prompt final

| Tecnica | Parte del prompt final |
|---------|------------------------|
| Role prompting | Actua como programador Java que disena sistemas para institutos. |
| Prompt estructurado | Las etiquetas rol, contexto, tarea y formato |
| Descomposicion | Los pasos 1, 2, 3 y 4 de la tarea |
| Autocritica | 4. Revisa tu codigo y corrige lo que falte. |

## Evaluacion del resultado

| Criterio | Cumple (Si/No) |
|----------|----------------|
| Esta en Java | Si |
| Lista las clases necesarias | Si |
| Muestra los atributos en una tabla | Si |
| Tiene el metodo calcularPromedio() | Si |
| Responde con un titulo por cada paso | Si |
| Revisa y corrige su propio codigo | Si |

## Por que elegi estas tecnicas

Elegi el rol para que la IA respondiera como programador Java y no hiciera una app web. Use etiquetas para separar el rol, el contexto, la tarea y el formato, y asi evitar que se mezclen. La descomposicion me permitio pedir el diseno por partes, y la autocritica sirvio para que la IA revisara su codigo. No use few-shot porque no necesitaba copiar un formato repetido, como en la clasificacion de comentarios.