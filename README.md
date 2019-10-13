# Aprendiendo R
Los comandos y ejemplos que se presentan corresponden a los ejercicios que se realizan en el tutorial **swirl()**. 

## Comandos para R

#### Ayuda de R

Para consultar acerca de una función:

```r
# ?nombre_de_la_Funcion
?summary
```
### Comandos para trabajar con vectores

```r
# Crear un vector que contenga los números 0, 1 y 2
c(0,1,2)
```

```r
# Asignar el vector a una variable
mi_variable <- c(0,1,2)
```

### Vectores lógicos

El vector lógico contiene valores TRUE, FALSE, y NA (por 'not available'). Estos valores son generados como resultados de una condición lógica.

Los operadores lógicos son los símbolos:
- **<**: menor que
- **>**: mayor que
- **>=**: mayor o igual que
- **<=**: menor o igual que
- **==**: igual que
- **!=**: no igual que

Para comparar expresiones lógicas se utilizan los operadores **|** ("o") y **&** ("y"). Algunos ejemplos de comparación de expresiones lógicas:

```r
(3 > 5) & (4 == 4)
(TRUE == TRUE) | (TRUE == FALSE)
((111 >= 111) | !(TRUE)) & ((4 + 1) == 5)
```

```r
# Ejemplo para crear un vector lógico
num_vect <- c(0.5, 55, -10, 6)
tf <- num_vect < 1

# Imprimiendo el vector
tf
[1]  TRUE FALSE  TRUE FALSE
```

### Vector de caracteres

Para que R reconozca que los caracteres son del tipo string se deben encerrar cada uno con comillas:

```r
# Ejemplo de vector de caracteres
my_char <- c("My", "name", "is")
```

```r
# Unir los elementos del vector separándolos por un espacio
paste(my_char, collapse = " ")
[1] "My name is"
```

```r
# Ejemplo 1 de unir caracteres
paste("Hello", "world!", sep=" ")
[1] "Hello world!"
```
```r
# Ejemplo 2
paste(c(1:3), c("X","Y","Z"), sep = "")
[1] "1X" "2Y" "3Z"
```

```r
# Ejemplo 3: LETTERS es una variable predefinida de R que contiene un vector de las 26 letras del 
# alfabeto inglés
paste(LETTERS, 1:4, sep = "-")
 [1] "A-1" "B-2" "C-3" "D-4" "E-1" "F-2" "G-3" "H-4" "I-1" "J-2" "K-3" "L-4" "M-1" "N-2"
[15] "O-3" "P-4" "Q-1" "R-2" "S-3" "T-4" "U-1" "V-2" "W-3" "X-4" "Y-1" "Z-2"
```

### Comandos para trabajar con directorios y archivos

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

### Crear secuencias de números

```r
# Crear una secuencia con el operador ":"
1:20
[1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20
```

```r
# Crear una secuencia de números reales
pi:10
[1] 3.141593 4.141593 5.141593 6.141593 7.141593 8.141593 9.141593
```

```r
# Crear una secuencia decreciente
15:1
 [1] 15 14 13 12 11 10  9  8  7  6  5  4  3  2  1
 ```
 
 ```r
 # Crear una secuencia con el comando seq()
 seq(1,20)
 [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20
 ```
 
 ```r
 # Crear una secuencia de 0 a 10 con paso de 0.5
 seq(0,10, by=0.5)
 [1]  0.0  0.5  1.0  1.5  2.0  2.5  3.0  3.5  4.0  4.5  5.0  5.5  6.0  6.5  7.0  7.5  8.0
[18]  8.5  9.0  9.5 10.0
```

```r
# Crear una secuencia del 5 hasta el 10 pero que contenga 30 elementos. 
# Almacenarlo en la variable my_seq
my_seq <- seq(5,10, length=30)
```

```r
# Confirmar la longitud del vector
length(my_seq)
[1] 30
```

```r
# Alternativas para crear secuencias según la longitud de otra secuencia
# Alternativa 1 
seq(along.with = my_seq)
[1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29
[30] 30

# Alternativa 2
1:length(my_seq)
 [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29
[30] 30

# Alternativa 3
seq_along(my_seq)
 [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29
[30] 30
```

```r
# Crear un vector con números repetidos
rep(0, times = 40)
 [1] 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0
 ```
 
 ```r
 # Crear un vector que contenga un vector que se repite
 rep(c(0,1,2), times = 10)
 [1] 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2
 ```
 
 ```r
 # Crear un vector que contenga 10 ceros, 10 unos y 10 dos
 rep(c(0,1,2), each = 10)
 [1] 0 0 0 0 0 0 0 0 0 0 1 1 1 1 1 1 1 1 1 1 2 2 2 2 2 2 2 2 2 2
 ```

 ### Para inspeccionar el contenido de una tabla

A modo de ejemplo, se usa la base de datos llamada **iris** que viene cargada en RStudio

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
 
 










