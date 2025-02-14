---
author: Verónica Quintana Iglesias
title: Actividad Evaluable - 2 Ejercicio de Git - proyecto labdist
---



# Tarea 2 Git - Proyecto labdist

> Realizado por Verónica Quintana

[TOC]

## Trabajo en local 

### Punto 1

Inicializa un nuevo repositorio Git en una carpeta llamada `"labdist"` y agrega los archivos proporcionados en el aula virtual. Renombra la rama master a main , si es necesario. Realiza el primer commit. Muestra el log del repositorio

```bash
git init
git status
git add .
git status
git branch -M main
git commit -m "Commit de inicio"
git log
```



<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250208121013813.png" alt="image-20250208121013813" style="zoom:67%;" />

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250208121215605.png" alt="image-20250208121215605" style="zoom:67%;" />



### Punto 2

Incluye un fichero `.gitignore` para que los ficheros `README.md` , `LICENCE.txt` y `passwords.txt` sean ignorados por el control de versiones. Realiza el commit y muestra los logs del repositorio en una línea.



Con estos dos primeros comandos, creo el archivo y le indico que abra el bloc de notas para editarlo

```bash
touch .gitignore
notepad .gitignore
```

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250208130040331.png" alt="image-20250208130040331" style="zoom:67%;" />

​		Aqui esta el bloc de notas abierto y con los archivos que se desea incluir para que el control de versiones los ignore

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250208125338303.png" alt="image-20250208125338303" style="zoom:50%;" />



```bash
git status
git add .
git commit -m "Agregado archivo para ignorar en el control de versiones"
git log 
git log --oneline
```

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250208132353035.png" alt="image-20250208132353035" style="zoom:67%;" />



<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250208132713750.png" alt="image-20250208132713750" style="zoom:67%;" />

> [!NOTE]
>
> En este caso te agrego después la captura del log en una línea porque al leer rápido, solo leí log y no me di cuenta que fuese en una línea



### Punto 3

En el repositorio, crea los archivos `README.md` , `LICENCE.txt` y `passwords.txt` con algún contenido. Muestra el estado del repositorio. Muestra el listado de archivos ignorados.

- Archivos creados

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250208135520393.png" alt="image-20250208135520393" style="zoom:50%;" />

- Hacer commit para confirmar los cambios

  ```bash
  git add  .
  git commit -m "Agreagr los archivos README, LICENCE y passwords"
  ```

  

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250208135934745.png" alt="image-20250208135934745" style="zoom:67%;" />

- Mostrar el estado del repositorio

  ```bash
  git status
  ```

  <img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250208140602189.png" alt="image-20250208140602189" style="zoom:67%;" />

- Mostrar los archivos ignorados

  ```
  git ls-files --ignored --exclude-standard --others
  ```

  

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250208140831240.png" alt="image-20250208140831240" style="zoom:67%;" />



### Punto 4

Crea una rama `feature-estilos` . Cámbiate a ella. 



- Modifica el archivo `estilos.css` : 
  - propiedad color del `body` y de `h2` : `#2a2a2a` 
  - propiedad `background-color` de `header` y `footer`: `#2a75ff` 
  
- Comprueba el estado del repositorio. Añade los cambios, realiza un commit con el mensaje "actualizados estilos a azules"

  ```bash
  git branch feature-estilos
  git branch -av
  git checkout feature-estilos
  git branch -av
  ```

  

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250208200137894.png" alt="image-20250208200137894" style="zoom: 50%;" />



​	

> [!NOTE]
>
> En este caso, use el comando `git branch -av` para mostrar las ramas que hay en dos ocasiones, una antes de cambiar y otra después para que se vea el cambio de una a otra



```bash
code css/estilos.css
```



Con este comando, abro el Visual Studio Code y modifico y guardo los cambios solicitados ahí



<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250208202836793.png" alt="image-20250208202836793" style="zoom: 50%;" />





Para comprobar el estado del repositorio

```bash
git status
```



<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250208203025923.png" alt="image-20250208203025923" style="zoom:50%;" />



Añadir los cambios y commit



```
git add .
git commit -m "actualizados estilos azules"
```



<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250208203355846.png" alt="image-20250208203355846" style="zoom:50%;" />





### Punto 5

Vuelve a la rama `main` . En el archivo `index.html` añade un comentario donde se indique tu nombre como autor de la página. Comprueba el estado del repositorio. Añade los cambios, realiza un commit con el mensaje **añadido autor en index**. Muestra los logs del repositorio en una línea, gráficamente y con 'decoración'

```bash
git checkout main
code index.html
git add .
git commit -m "añadido autor en index"
git log --oneline --graph --decorate
```



<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209140713785.png" alt="image-20250209140713785" style="zoom:50%;" />



### Punto 6



Fusiona la rama `feature-estilos` en la rama `main` . Muestra los logs del repositorio en una línea, gráficamente y con **'decoración'** 

```bash
git merge feature-estilos
git log --oneline --graph --decorate
```

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209141828463.png" alt="image-20250209141828463" style="zoom: 50%;" />



> [!NOTE]
>
> Al fusionar la rama `feature-estilos` con la rama `main` aparece este mensaje en **Visual Studio Code** (el editor que tengo configurado por defecto)

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209141209070.png" alt="image-20250209141209070" style="zoom:67%;" />







## Trabajo en remoto



### Punto 1

Continúa con el repositorio `labdist` . Añade el repositorio a Sourcetree.

- A través de la opcion de clonar, agregue el repositorio tal y como lo tenia creado y modificado después de haber trabajado con el en local

  <img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209184000138.png" alt="image-20250209184000138" style="zoom:50%;" />



<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209173429484.png" alt="image-20250209173429484" style="zoom:50%;" />

​	

### Punto 2

En tu cuenta de GitHub, crea un repositorio remoto y sube al remoto los ficheros de tu repositorio local. Debes subir todas las ramas. Muestra, además, la captura de pantalla donde se vean en GitHub, algo similar a esto:



- Con esta opcion en git, se crea  un repositorio

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209174024421.png" alt="image-20250209174024421" style="zoom:50%;" />



- Se copia la url que proporciona en Sourcetree



<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209175307049.png" alt="image-20250209175307049" style="zoom:67%;" />



<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209184133847.png" alt="image-20250209184133847" style="zoom:50%;" />





- Con `Push`, se suben las ramas que hay

  

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209184443983.png" alt="image-20250209184443983" style="zoom: 50%;" />





- Esto es lo que me quedaría subido en git, al haber fusionado la rama que había creado en local con la de `main` solo me aparecía para subir la rama `main`

  <img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209184545092.png" alt="image-20250209184545092" style="zoom:50%;" />



### Punto 3

​	En el documento del enunciado de la tarea, no hay punto 3 en remoto



### Punto 4

En el repositorio local, crea una rama `feature-index` . Añade el siguiente código dentro de la `<section class="about">`. Añade los cambios y crea un commit con el mensaje **"Añadido párrafo equipo en index.html"**. Sube los cambios al remoto. (Recuerda que debes usar SourceTree en todo este apartado )

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209185536917.png" alt="image-20250209185536917" style="zoom:50%;" />



​		Se agrega en el archivo `index.html` el código en la sección indicada y se hace el comit

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209185155252.png" alt="image-20250209185155252" style="zoom:50%;" />

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209190029495.png" alt="image-20250209190029495" style="zoom:50%;" />



### Punto 5

En el repositorio local, fusiona la rama feature-index en la rama main .



<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209191607690.png" alt="image-20250209191607690" style="zoom:50%;" />





### Punto 6

Edita el fichero `contacto.html` . Borra unas líneas. Muestra los ficheros con cambios pendientes y las diferencias. Añade los cambios y haz un commit.

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209192550238.png" alt="image-20250209192550238" style="zoom:50%;" />

En verde se ve unas lineas que se han agreagado

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209193007906.png" alt="image-20250209193007906" style="zoom:50%;" />

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209193155014.png" alt="image-20250209193155014" style="zoom:50%;" />





### Punto 7

Te das cuenta del error. Deshaz TOTALMENTE el commit anterior. Captura el estado actual del repositorio. (Asegúrate de que el fichero contacto.html ha recuperado todas las líneas borradas y no hay cambios pendientes en el repositorio.)

- Este es el registro del commit, antes de deshacerlo

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209193422352.png" alt="image-20250209193422352" style="zoom:50%;" />



- Registro de des hacer el commit 

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209193526846.png" alt="image-20250209193526846" style="zoom:50%;" />





### Punto 8

Crea una rama `feature-mapa` y cámbiate a ella. Incluye este código en el archivo contacto.html . Añade los cambios. Realiza un commit.

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209194400790.png" alt="image-20250209194400790" style="zoom:50%;" />

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209194642241.png" alt="image-20250209194642241" style="zoom:50%;" />



### Punto 9

Sube los cambios al remoto - los de todas las ramas. Muestra en el remoto los cambios del archivo `contacto.html` en la rama `feature-mapa` .

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209194913381.png" alt="image-20250209194913381" style="zoom:50%;" />





### Punto 10

En GitHub, en la rama `main` , fusiona la rama `feature-mapa` . Baja los cambios del remoto a local. Deja los dos repositorios sincronizados. Muestra una captura de pantalla donde se vea la página principal de tu repositorio remoto

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209195436648.png" alt="image-20250209195436648" style="zoom:50%;" />

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209195547286.png" alt="image-20250209195547286" style="zoom:50%;" />

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209195619716.png" alt="image-20250209195619716" style="zoom:50%;" />



- Así descargo lo que esta en remoto hacia local

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250209195755762.png" alt="image-20250209195755762" style="zoom:50%;" />



## Conflictos



### Punto 1

Crea una rama `hotfix-js` . Cámbiate a ella. Añade este código en el fichero `script.js` . Confirma el cambio y haz un commit con el mensaje "**corregido problema en script.js**". (Fíjate en los números de línea de tu editor ...)



<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250210133602311.png" alt="image-20250210133602311" style="zoom:50%;" />

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250210133841735.png" alt="image-20250210133841735" style="zoom:50%;" />

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250210140625131.png" alt="image-20250210140625131" style="zoom:50%;" />





### Punto 2

Vuelve a la rama `main` . En el fichero `script.js` en las mismas líneas que en la cuestión anterior, añade el código siguiente. Confirma el cambio y haz un commit con el mensaje "corregido problema en script.js rama main".

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250210141702206.png" alt="image-20250210141702206" style="zoom:50%;" />



<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250210142049817.png" alt="image-20250210142049817" style="zoom:33%;" />



### Punto 3

Fusiona la rama `hotfix-js` en `main` . Debe producirse un conflicto. Resuélvelo como consideres oportuno. Cuando termines la resolución del conflicto sube los cambios al remoto.

- Al intentar fusionar la rama, me sale este mensaje

  <img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250214105940067.png" alt="image-20250214105940067" style="zoom:67%;" />

- Corregir el error manualmente dejandolo asi

  <img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250214110328231.png" alt="image-20250214110328231" style="zoom:67%;" />



-  Subo todas las ramas al remoto

  <img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250214110748030.png" alt="image-20250214110748030" style="zoom:50%;" />





## Github



- Url: https://github.com/VeronicaQuintanaIglesias/labdist.git



<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250214115259732.png" alt="image-20250214115259732" style="zoom:50%;" />

- Ramas

<img src="./Actividad-Evaluable---2-Ejercicio-de-Git---proyecto-labdist.assets/image-20250214115516247.png" alt="image-20250214115516247" style="zoom:50%;" />



# Videoclip



**Url:** 
