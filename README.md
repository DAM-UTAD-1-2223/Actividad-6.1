# Actividad-6.1

Alejandro Bonet Otaño

## Actividad 1
```bash
#!/bin/bash

echo "Ingrese un número entero:"
read numero

if [ $numero -ge 0 ]
 then
  echo "El número $numero es positivo."

else
  echo "El número $numero no es positivo."
fi
```

## Actividad 2
```bash
#!/bin/bash

echo "Ingrese un número entero:"
read numero

if [ $numero -lt 0 ]; then
  echo "El número $numero es negativo."

else
  echo "El número no es negativo"
fi
```

## Actividad 3
```bash
#!/bin/bash

echo "Ingrese un número entero:"
read numero

if [ $numero -eq 0 ]; then
  echo "El número $numero es cero."
else
  echo "El número $numero no es cero."
fi
```

## Actividad 4
```bash
#!/bin/bash

echo "Ingrese un número entero:"
read numero

if [ $numero -gt 0 ]; then
  echo "El número $numero es positivo."
elif [ $numero -lt 0 ]; then
  echo "El número $numero es negativo."
else
  echo "El número $numero es cero."
fi
```
## Actividad 5

```bash
#!/bin/bash

if [ $# -ne 3 ]; 
then
  echo "Error: Debe introducir 3 parámetros."
 else
 echo "Los parámetros introducidos son: $1, $2 y $3."
```
## Actividad 6

```bash
#!/bin/bash

if [ $# -ne 2 ]; then
  echo "Error: Debe introducir 2 parámetros."
else
 numero1=$1
 numero2=$2
 suma=$((numero1 + numero2))

 echo "La suma de $numero1 y $numero2 es: $suma."
 fi
```
## Actividad 7

```bash
#!/bin/bash

if [ $# -ne 3 ]; then
  echo "Error: Debe introducir 3 parámetros."

elif

case $3 in
  "+")
    resultado=$(( $1 + $2 ))
    echo "La suma de $1 y $2 es: $resultado"
    ;;
  "-")
    resultado=$(( $1 - $2 ))
    echo "La resta de $1 y $2 es: $resultado"
    ;;
  "x")
    resultado=$(( $1 * $2 ))
    echo "La multiplicación de $1 y $2 es: $resultado"
    ;;
  "/")
    resultado=$(( $1 / $2 ))
    echo "La división de $1 y $2 es: $resultado"
    ;;
  *)
    echo "Error: El tercer parámetro debe ser uno de los siguientes símbolos: +, -, x, /."
    exit 1
    ;;
esac
fi
```
## Actividad 8

```bash
#!/bin/bash

if [ -e $1 ]; then
  echo "El archivo $1 existe."
else
  echo "El archivo $1 no existe."
fi
```
## Actividad 9

```bash
#!/bin/bash

if [ -f $1 ]; then
  echo "La ruta $1 indica un archivo."
elif [ -d $1 ]; then
  echo "La ruta $1 indica un directorio."
fi
```
## Actividad 10

```bash
#!/bin/bash

permisos=$(ls -l "$1" | grep -o "^[-rwx]*")
echo "Los permisos del archivo $1 son: $permisos"
```

## Actividad 11
```bash
#!/bin/bash
for i in {1..50}; do
  echo "hola"
done
```
## Actividad 12

```bash
#!/bin/bash

for i in {1..10}; do
  echo "Ingrese una palabra:"
  read palabra
  echo "La palabra ingresada es: $palabra"
done
```

## Actividad 13
```bash
#!/bin/bash
for i in $(seq 1 "$1"); do
  echo "hola"
done
```
## Actividad 14

```bash
#!/bin/bash

for i in $(seq 0 "$1"); do
  echo "$i"
done
```
## Actividad 15

```bash
#!/bin/bash

n=$1
suma=0
for ((i=1; i<=$n; i++))
do
  suma=$((suma+i))
done

echo "La suma de los números del 1 al $n es: $suma"
```
## Actividad 16

```bash
#!/bin/bash


num1=$1
num2=$2


temp=$num1
num1=$num2
num2=$temp

echo "El valor del primer número ahora es: $num1"
echo "El valor del segundo número ahora es: $num2"
```
## Actividad 17

```bash
#!/bin/bash

palabra="";

while ["$palabra" != ":q" ]
do
  read -p "Escribe una palabra (escribe :q para salir): " palabra
  fi
```
## Actividad 18
```bash
#!/bin/bash

read -p "Introduce el nombre del archivo donde se guardarán las palabras: " archivo


> "$archivo"

while true
do
  read -p "Escribe una palabra (escribe :q para salir): " palabra


  if [ "$palabra" = ":q" ]
  then
    break
  fi
  echo "$palabra" >> "$archivo"
done

echo "Las palabras guardadas en el archivo $archivo son:"
cat "$archivo"
```
## Actividad 19
```bash
#!/bin/bash

read -p "Introduce el nombre del archivo donde se guardarán las palabras: " archivo

> "$archivo"

while true
do

  read -p "Escribe una palabra (escribe :q para salir): " palabra

  if [ "$palabra" = ":q" ]
  then
    break
  fi

  echo "$palabra" >> "$archivo"
  sort -o "$archivo" "$archivo"
done

echo "Las palabras guardadas en el archivo $archivo son:"
cat "$archivo"
```
## Actividad 20
```bash
#!/bin/bash

read -p "Introduce un número: " numero
if grep -q "^$numero$" numeros.txt
then
  echo "El número $numero se encuentra en el archivo numeros.txt."
else
  echo "El número $numero NO se encuentra en el archivo numeros.txt."
fi
```

