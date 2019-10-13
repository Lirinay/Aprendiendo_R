# Aprendiendo R
Datos, shortcuts y comandos que he ido aprendiendo

## Comandos para R

A modo de ejemplo, uso la base de datos llamada **iris** que viene cargada en RStudio

#### Ayuda de R

Para consultar acerca de una función

```r
# ?nombre_de_la_Funcion
?summary
```

#### Para inspeccionar el contenido de una tabla


```r
# Representación gráfica
plot(iris)
```
![Gráfica_1](/img/Rplot_iris.png)

```r
# Resumen de principales estadísticos
summary(iris)
```
![Gráfica_2](/img/summary_iris.png)

```r
# Representación del objeto
str(iris)
```

```r
# Encabezado y final de la tabla
head(iris)
tail(iris)
```
![Gráfica_4](/img/head_iris.png)

![Gráfica_5](/img/tail_iris.png)

```r
# Encabezado y final de la tabla indicando el número de filas a mostrar
head(iris,13)
tail(iris, 8)
```
![Gráfica_6](/img/head_iris_13.png)

![Gráfica_7](/img/tail_iris_8.png)

```r
# Dimensión de la tabla
dim(iris)
```

```r
# Cantidad de filas de la tabla
nrow(iris)
```

```r
# Cantidad de columnas de la tabla
ncol(iris)
```

```r
# Nombre de las columnas de la tabla
colnames(iris)
```

## Comandos para trabajar con directorios y archivos

```r
# Directorio actual de trabajo
getwd()
```

```r
# Listado de los objetos en tu espacio de trabajo local
ls()
[1] "x"
```

```r
# Listar los archivos del directorio actual  
list.files()

# Alternativamente 
dir()
```

```r
# Crear un nuevo directorio llamado testdir
dir.create("testdir")
```

```r
# Cambiar al directorio testdir
setwd("testdir")
```

```r
# Crear un archivo llamado mytest.R en el directorio actual
file.create("mytest.R")
```

```r
# Verificar si existe el archivo mytest.R
file.exists("mytest.R")
[1] TRUE
```

```r
# Acceder a la información del archivo mytest.R
> file.info("mytest.R")
         size isdir mode               mtime               ctime               atime uid
mytest.R    0 FALSE  644 2019-10-13 12:10:07 2019-10-13 12:10:07 2019-10-13 12:10:07 501
         gid   uname grname
mytest.R  20 Natalia  staff
```

```r
# Cambiar el nombre del archivo de mytest.R a mytest2.R
file.rename("mytest.R","mytest2.R")
[1] TRUE
```

```r
# Crear una copia del archivo mytest2.R llamada mytest3.R
file.copy("mytest2.R","mytest3.R")
[1] TRUE
```

```r
# Proporcionar la ruta relativa al archivo mytest3.R
file.path("mytest3.R")
[1] "mytest3.R"
```

```r
# Puede usar file.path para construir rutas de archivos y directorios que sean independientes del
# sistema operativo en el que se ejecuta su código R. Pase 'folder1' y 'folder2' como argumentos al
# file.path para crear un nombre de ruta independiente de la plataforma.
file.path("folder1","folder2")
[1] "folder1/folder2"
```


```r
# Crear un directorio en el directorio de trabajo actual llamado "testdir2" y un subdirectorio llamado 
# "testdir3", todo en un comando usando dir.create () y file.path ().
dir.create(file.path("testdir2","testdir3"), recursive = TRUE)
```











