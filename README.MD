# 🚀 Trabajar con Ramas en Git y GitHub

Este proyecto muestra cómo trabajar con ramas en GitHub y Git mediante la creación de un proyecto e-commerce paso a paso.

## 📌 1. Creación del proyecto inicial

- Creamos un repositorio en GitHub llamado e-commerce.

- En el escritorio local, creamos una carpeta llamada e-commerce y la abrimos con Visual Studio Code.

- Creamos el archivo index.html.

Agregamos el siguiente código:

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width,
    initial-scale=1.0">
    <title>
     E-Commer
    </title>
  </head>
  <body>

  </body>
</html>

```
1. Inicializamos Git y movemos los cambios al área de preparación.
```sh
git init
git add .
```
2- Realizamos el primer commit.
```sh
git commit -m "Primer commit index.html"
```
3- Conectamos el repositorio local con el remoto usando origin.
```sh
git remote add origin git@github.com:kenkairon/CursoDeGithubRamasEcommerce.git
git remote -v
```
4-Subimos los cambios con git push.
```sh
git branch -M main
git push -u origin main
```
!Nota solo en el caso que hayas escrito mal el remoto de origen No lo debes escribir si no paso
```sh
git remote remove origin
```
# 📌 2. Creación de ramas y nuevas funcionalidades
## 🔹 Rama home

1. Checamos las ramas existentes.
```sh
git branch 
```
2. Creamos la rama home.
```sh
git branch home
```
3. Confirmamos que la rama fue creada y nos situamos en la rama home
```sh
git branch
git checkout home
```

4. En home, creamos un menú de navegación en index.html:

```html
<script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.1/jquery.min.js"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
<link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" rel="stylesheet"/>
<nav class="navbar navbar-inverse">
  <div class="container-fluid">
    <div class="navbar-header">
      <a class="navbar-brand" href="#">Home</a>
      <a class="navbar-brand nv1" href="#">Productos</a>
      <a class="navbar-brand nv1" href="#">Contacto</a>
    </div>
  </div>
</nav>

```
5. Movemos el cambio al área de preparación y confirmamos en el repositorio local.
```sh
git add .
git commit -m "Agregamos el menu a home"
git push origin home
```
6. Integramos los cambios a main y eliminamos la rama home.
```sh 
git checkout main
git merge home
git branch -D home
```

#🔹 Rama productos

1. Creamos la rama productos desde maim.
```sh
git checkout main
git branch productos
```
2.Checamos las ramas.
```sh
git branch
git branch productos
git checkout productos
```
En productos, creamos un archivo productos.html con el siguiente código:

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width,
    initial-scale=1.0">
    <title>
      ¡Hola, Marines!
    </title>
  </head>
  <body>
<h1>Productos</h1>
<table>
    <tr>
      <th>
         <img src="https://i.ibb.co/Cs9PzmQ2/71cy1db-Mh5-L-AC-SX695.jpg" width="300" height="150"  /><br>
         <font size="5">Nike Revolution </font><br>
        <font size="3">$1,660</font>
      </th>
      <th>
         <img src="https://i.ibb.co/YFXs6w3D/411-Fy-KQqn-SL-AC-SY695.jpg" width="300" height="150" /><br>
         <font size="5">Adidas Herren VL Court</font><br>
        <font size="3">$2,660</font>
      </th>
    </tr>
</table>
  </body>
</html>

```
1- En index.html modificamos el menú agregando el link a productos Pero estaba en la rama home Pero lo eliminanos
Vamos a volver a restaurarlo pero vamos a revisar el número del commit
```sh 
git reflow
```
2- Revisamos el numero del commit y volvemos a restablecer la rama home 
```sh
git branch home b7d9e21
```
3- en la restauracion vamos a agregar el link del producto 
```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width,
    initial-scale=1.0">
    <title>
     E-Commer
    </title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.1/jquery.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" rel="stylesheet"/>
  </head>
  <body>
<nav class="navbar navbar-inverse">
  <div class="container-fluid">
    <div class="navbar-header">
      <a class="navbar-brand" href="#">Home</a>
      <a class="navbar-brand nv1" href="productos.html">Productos</a>
      <a class="navbar-brand nv1" href="#">Contacto</a>
    </div>
  </div>
</nav>
  </body>
</html>
```
4- Movemos los cambios al área de preparación y confirmamos.
```sh
git add .
git commit -m "agregamos el link productos"
git push origin home
```
5-Integramos los cambios a main y nos situamos a la rama main y volvemos a eliminar la rama home
```sh
git checkout main
git merge home
git branch -d home
```

6. Me situo en productos y agrego los cambios en la rama productos
```sh
git checkout productos
git add .
git commit -m "Agrego productos a la rama productos"
git push origin productos
```

7. Me situo a la rama main y hago el merge y elimino la rama productos
```sh 
git checkout main
git merge productos
git branch -d productos
```
8. Si me genera conflicto al agregar productos
```sh
git add .
git commit -m "resolviendo conflictos"
git push origin main
```

9. Elimino rama productos
```sh
git branch -d productos
```

# 📌 3. Ejercicio con GitHub Flow

1- Creamos la rama develop.
```sh
git branch develop
```
2- Creamos la rama feature/footer y accedemos a ella.
```sh
git branch feature/footer 
git checkout feature/footer 
```
3- Creamos una carpeta css y dentro un archivo main.css con el siguiente código:

```css
#page-container {
  position: relative;
  min-height: 100vh;
}

#content-wrap {
  padding-bottom: 2.5rem;    /* altura de pie de página */
}

#footer {
  position: absolute;
  bottom: 0;
  width: 100%;
  height: 2.5rem;            /* altura de pie de página */
}

```
4- En el archivo index.html, agregamos en <head>:

```html
<link rel="stylesheet" type="text/css" href="css/main.css" />

```
En <body> agregamos el footer:
```html
<h1>Testear footer</h1>
<div id="page-container">
  <div id="content-wrap">
      Copyright © 2023 Football History Archives.
      All Rights Reserved.
  </div>
  <footer id="footer"></footer>
</div>
```
5- Subimos los cambios al repositorio remoto.
```sh
git add .
git commit -m "Subimos los css a la rama feature/footer"
git push feature/footer 
```
6- Desde develop creamos otra rama llamada feature/boton.
```sh
git checkout develop
git branch feature/boton
git checkout feature/boton
```
7- Agregamos el siguiente código en index.html:

```html

<input type="button" value="Click me" />

```
8-Agregamos lo cambios 
```sh 
git add .
git commit -m "agregamos los cambios a la rama feature/boton"
git push origin feature/boton
```

8- Desde develop integramos feature/boton y feature/footer.
```sh
git checkout develop
git merge feature/boton
git merge feature/footer
```
9- Subimos los cambios al remoto.
```sh
git push origin develop
```
10 -Creamos la rama release desde develop.
```sh
git branch release
```
10- Verificamos que todo funcione correctamente.

11- Integramos release a main.
```sh
git checkout main
git merge release
```

# 📌 4. Hotfix (corrección rápida)

## ⚠️ Se detectó un error: dejamos la línea de testeo en el código.

```html
<h1>Testear footer</h1>

```
1- ➡️ Solución:

1- Creamos la rama hotfix.
```sh
git branch hotfix
```
2- Eliminamos la línea de testeo.
```sh
git add .
git commit -m "eliminamos la linea del testeo"
git push origin hotfix
```
3- Subimos el cambio directamente a main.
```sh
git checkout main
git merge hotfix
```