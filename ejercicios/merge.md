# E5 — Resolución de conflicto de Git

## Objetivo

Practicar la creación y resolución de un conflicto de merge en Git.

## Paso 1: Crear una rama

Partí desde la rama `main` y creé una nueva rama llamada:

```text
conflicto-prueba
```

Comandos utilizados:

```text
git branch conflicto-prueba
git switch conflicto-prueba
```

## Paso 2: Modificar el mismo archivo en la nueva rama

En la rama `conflicto-prueba` modifiqué el título principal de `index.html`:

```html
<h1>Evento Tech Bogotá - Rama de prueba</h1>
```

Después guardé el cambio con el commit:

```text
9832a27 Cambio titulo rama de prueba
```

## Paso 3: Crear otro cambio en main

Volví a la rama `main`:

```text
git switch main
```

Luego modifiqué la misma línea de `index.html`, pero con otro contenido:

```html
<h1>Evento Tech Bogotá - Version principal</h1>
```

Creé el commit:

```text
50c3215 actualizo titulo en main
```

## Paso 4: Provocar el conflicto

Intenté unir la rama `conflicto-prueba` dentro de `main`:

```text
git merge conflicto-prueba
```

Git mostró:

```text
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.
```

El conflicto apareció porque las dos ramas habían modificado la misma parte del mismo archivo.

## Paso 5: Resolver el conflicto

Git colocó marcas especiales en `index.html` para mostrar las dos versiones.

Resolví el conflicto dejando una sola versión del título:

```html
<h1>Evento Tech Bogotá</h1>
```

También eliminé las marcas de conflicto:

```text
<<<<<<<
=======
>>>>>>>
```

## Paso 6: Confirmar la resolución

Después marqué el archivo como resuelto:

```text
git add index.html
```

Finalmente creé el commit que cerró el merge:

```text
5e7f257 resolvi el conflicto de merge
```

## ¿Qué aprendí?

Aprendí que un conflicto de merge ocurre cuando Git no puede combinar automáticamente cambios realizados sobre la misma parte de un archivo.

También aprendí que Git muestra las diferentes versiones mediante marcas de conflicto y que una persona debe decidir cómo debe quedar finalmente el archivo.

## Conclusión

El ejercicio permitió practicar la creación de ramas, modificaciones independientes, merge, identificación de conflictos, resolución manual y creación del commit final del merge.
