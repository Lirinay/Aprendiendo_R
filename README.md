# Productividad
Datos, shortcuts y comandos para que he ido aprendiendo

## Comandos para R

A modo de ejemplo, uso la base de datos llamada **iris** que viene cargada en RStudio

### Para inspeccionar el contenido de una tabla


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





