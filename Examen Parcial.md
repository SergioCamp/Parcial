---
title: "Examen Parcial"
author: "Campos Torres Sergio Junior"
date: "10/12/2021"
output: github_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

## Parte 1

#Ejercicio 01

```{r}
Angulo=function(m1="Pendiente_L1",m2="Pendiente_L2"){
  v1=atan((m2-m1)/(1+m1*m2))
  return(v1)
}
```

#Ejercicio 02

```{r}
Codigo=c("A","B","C","D","E","F")
Este=c(272841.7,272893.6,272892.5,272913.8,272911.2,272837.5)  
Norte=c(8666459.9,8666456.9,8666446.1,8666441.5,8666399.9,8666407.9)
pol=data.frame(Codigo,Este,Norte)

Grafico=function(df){
  este=c(df[,"Este"],df[1,2])
  norte=c(df[,"Norte"],df[1,3])
  return(plot(este,norte,type="l",axes=FALSE, xlab="", ylab=""))
}
Grafico(pol)
```

## Parte 2

#Ejercicio 01

```{r}
casas=read.csv("D:/Parcial Progra/kc_house_data.csv")

casas[casas$prices==max(casas$price)]
casas[casas$prices==min(casas$price)]

plot(casas$price)
```

#Ejercicio 04

```{r}
x=sample(1:100,10)

orden=function(x){
  n<-length(x)
  for(j in 1:(n-1)){
    for(i in 1:(n-j)){
      if(x[i]>x[i+1]){
        temp=x[i]
        x[i]=x[i+1]
        x[i+1]=temp
      }
    }
  }
  return(x)
}
orden(x)
```