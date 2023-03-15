# Practica-7-Galo
title: "Practica 5 Galo"
author: "Fernando López"
date: "14/3/2023"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

#ejercicio 1

set.seed(1)
z = rnorm (100)
x = rpois (100,10,3)
y = rbinom (100,1,25)
y1 <- 5*z+x*10+rnorm(100,2,1)
y2 <- 5*z+x*12+rnorm(100,2,1)

hist(y1)
hist(y2)

t.test(y1)
t,test(y2)

shapiro.test(y1)
shapiro.test(y2)
#ejercicio 2
La correlación lineal es una prueba de correlación paramétrica porque requiere que los datos que se están analizando cumplan con ciertas suposiciones o parámetros sobre la distribución de la población a partir de la cual se obtuvieron las muestras.
Las pruebas paramétricas se basan en la suposición de que los datos se distribuyen de forma normal en la población a partir de la cual se extrajo la muestra.
Las pruebas no paramétricas no realizan supuestos sobre la distribución de la población y se basan en el ordenamiento de los datos.
Otra diferencia importante entre las pruebas paramétricas y no paramétricas es el tipo de datos que pueden ser analizados.
#ejercicio 3
```{r}
data = as.data.frame(data)
View (data)
cor (data)
```
longitud y ancho = 0.402
grosor y ancho = -0.001
longitud y peso = 0.9555
grosor y peso = -0.58
ancho y peso = 0.508

#ejercicio 4
```{r}
install.packages("corplot")
library(corplot)
with(data, plot(x=longitud, y=peso, pch=20, c0l=blue))

install.packages("correlation")
```


```{r}
library(correlation)
resultados = correlation(data) 
resultados
```


```{r}
library(ggpurb)
```

#ejercicio 5
```{r}
corr_matrix = df.corr()
```
cor.test(data$longitud, data$ancho)
cor.test(data$grosor, data$peso) 




#ejercicio 6

```{r}
plot(data$longitud, data$peso, pch = 19, col = "black")

# Línea de regresión
abline(lm(data$peso ~ data$longitud), col = "red", lwd = 3)

# Correlación de Pearson
text(paste("Correlación:", round(cor(data$peso, data$longitud), 2)), x = 25, y = 95)

```


#ejercicio 7
```{r}
install.packages("corplot")
library(corplot) 
corrplot(cor(data),method = `number`)
```

#ejercicio 8
distancia <- c(1.1,100.2,90.3,5.4,57.5,6.6,34.7,65.8,57.9,86.1)
n_piezas <- c(110,2,6,98,40,94,31,5,8,10)

correlacion <- cor(distancia, n_piezas)
print(correlacion)
El coeficiente de correlacion es [1] -0.5672024.

prueba_correlacion <- cor.test(distancia, n_piezas)
data:  distancia and n_piezas
t = -2.0881, df = 8, p-value = 0.06775
El valor p es de 0.06775, lo que indica que la correlación no es significativa a un nivel de significancia del 5% (nivel de confianza del 95%)

A medida que aumenta la distancia, el número de piezas disminuye en general.

En este caso, el valor p es de 0.06775, lo que indica que la correlación no es significativa a un nivel de significancia del 5%.

En general, cuanto más pequeña sea la muestra, más incierto será el valor de la correlación y más difícil será determinar si la correlación es significativa o no.

En general, cuanto más pequeña sea la muestra, más incierto será el valor de la correlación y más difícil será determinar si la correlación es significativa o no. Nuestramuestra es pequeña


#ejercicio 9
La relación lineal se refiere a una relación en la que la relación entre dos variables se puede representar en una línea recta en un gráfico de dispersión.
La relación monótona se refiere a una relación en la que una variable aumenta o disminuye a medida que la otra variable aumenta o disminuye, pero no necesariamente de manera lineal. 
x <- c(1, 2, 3, 4, 5)
y1 <- c(2, 4, 6, 8, 10)  # relación lineal
y2 <- c(1, 3, 5, 7, 9)   # relación monótona creciente
#ejercicio 10
Para variables que experimentan una relación monótona, se aplica la prueba de correlación de rango de Spearman
cor.test(x, y, method = "spearman")

