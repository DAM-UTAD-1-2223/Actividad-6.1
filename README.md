# Actividad-6.1

Alejandro Bonet Otaño

´´´bash
#!/bin/bash

echo "Ingrese un número entero:"
read numero

if [ $numero -gt 0 ]
 then
  echo "El número $numero es positivo."

else
  echo "El número $numero no es positivo."
fi
´´´


´´´bash
#!/bin/bash

echo "Ingrese un número entero:"
read numero

if [ $numero -lt 0 ]; then
  echo "El número $numero es negativo."

else
  echo "El número no es negativo"
fi
´´´


´´´bash
#!/bin/bash

echo "Ingrese un número entero:"
read numero

if [ $numero -eq 0 ]; then
  echo "El número $numero es cero."
else
  echo "El número $numero no es cero."
fi
´´´


´´´bash
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
´´´


´´´bash
#!/bin/bash

if [ $# -ne 3 ]; then
  echo "Error: Debe introducir 3 parámetros."
  exit 1
fi

# Si llega hasta aquí, significa que se han introducido 3 parámetros.
echo "Los parámetros introducidos son: $1, $2 y $3."
´´´


´´´bash
#!/bin/bash

if [ $# -ne 2 ]; then
  echo "Error: Debe introducir 2 parámetros."
  exit 1
fi

# Si llega hasta aquí, significa que se han introducido 2 parámetros.
numero1=$1
numero2=$2
suma=$((numero1 + numero2))

echo "La suma de $numero1 y $numero2 es: $suma."
´´´


´´´bash
#!/bin/bash

if [ $# -ne 3 ]; then
  echo "Error: Debe introducir 3 parámetros."
  exit 1
fi

if ! [[ $1 =~ ^[0-9]+$ ]]; then
  echo "Error: El primer parámetro no es un número."
  exit 1
fi

if ! [[ $2 =~ ^[0-9]+$ ]]; then
  echo "Error: El segundo parámetro no es un número."
  exit 1
fi

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
´´´

´´´bash
#!/bin/bash

if [ $# -ne 1 ]; then
  echo "Error: Debe introducir la ruta al archivo como único parámetro."
  exit 1
fi

if [ -e $1 ]; then
  echo "El archivo $1 existe."
else
  echo "El archivo $1 no existe."
fi
´´´


´´´bash
#!/bin/bash

if [ $# -ne 1 ]; then
  echo "Error: Debe introducir la ruta como único parámetro."
  exit 1
fi

if [ -f $1 ]; then
  echo "La ruta $1 indica un archivo."
elif [ -d $1 ]; then
  echo "La ruta $1 indica un directorio."
else
  echo "Error: La ruta $1 no existe."
  exit 1
fi
´´´


´´´bash
#!/bin/bash

# Verificar que se haya proporcionado la ruta del archivo como argumento
if [ -z "$1" ]; then
  echo "Debe proporcionar la ruta del archivo como argumento."
  exit 1
fi

# Verificar que el archivo exista
if [ ! -f "$1" ]; then
  echo "El archivo no existe."
  exit 1
fi

# Obtener los permisos del archivo
permisos=$(ls -l "$1" | grep -o "^[-rwx]*")

echo "Los permisos del archivo $1 son: $permisos"

´´´bash
#!/bin/bash

for i in {1..50}; do
  echo "hola"
done
´´´


´´´bash
#!/bin/bash

for i in {1..10}; do
  echo "Ingrese una palabra:"
  read palabra
  echo "La palabra ingresada es: $palabra"
done
´´´


´´´bash
#!/bin/bash

# Verificar que se haya proporcionado el número como argumento
if [ -z "$1" ]; then
  echo "Debe proporcionar un número como argumento."
  exit 1
fi

# Imprimir "hola" el número de veces indicado por el argumento
for i in $(seq 1 "$1"); do
  echo "hola"
done
´´´


´´´bash
#!/bin/bash

# Verificar que se haya proporcionado el número como argumento
if [ -z "$1" ]; then
  echo "Debe proporcionar un número como argumento."
  exit 1
fi

# Imprimir los números del 0 al número indicado por el argumento
for i in $(seq 0 "$1"); do
  echo "$i"
done
´´´


´´´bash
#!/bin/bash

# Recibimos el número n como argumento
n=$1

# Inicializamos la suma en cero
suma=0

# Iteramos desde 1 hasta n y sumamos cada número
for ((i=1; i<=$n; i++))
do
  suma=$((suma+i))
done

# Mostramos el resultado de la suma por pantalla
echo "La suma de los números del 1 al $n es: $suma"
´´´

´´´bash
#!/bin/bash

# Recibimos los dos números como argumentos
num1=$1
num2=$2

# Intercambiamos los valores de las variables
temp=$num1
num1=$num2
num2=$temp

# Mostramos los nuevos valores de las variables por pantalla
echo "El valor del primer número ahora es: $num1"
echo "El valor del segundo número ahora es: $num2"
´´´


´´´bash
#!/bin/bash

# Inicializamos una variable para almacenar las palabras
palabras=""

# Leemos palabras hasta que se escriba ":q"
while true
do
  # Leemos una palabra desde la entrada estándar
  read -p "Escribe una palabra (escribe :q para salir): " palabra

  # Si se escribió ":q", salimos del ciclo while
  if [ "$palabra" = ":q" ]
  then
    break
  fi

  # Concatenamos la nueva palabra a las palabras ya ingresadas
  palabras="$palabras $palabra"
done

# Mostramos todas las palabras ingresadas
echo "Las palabras ingresadas son:$palabras"
´´´

´´´bash
#!/bin/bash

# Pedimos al usuario que introduzca el nombre del archivo donde se guardarán las palabras
read -p "Introduce el nombre del archivo donde se guardarán las palabras: " archivo

# Creamos el archivo si no existe y lo vaciamos si ya existe
> "$archivo"

# Leemos palabras hasta que se escriba ":q"
while true
do
  # Leemos una palabra desde la entrada estándar
  read -p "Escribe una palabra (escribe :q para salir): " palabra

  # Si se escribió ":q", salimos del ciclo while
  if [ "$palabra" = ":q" ]
  then
    break
  fi

  # Escribimos la palabra en el archivo
  echo "$palabra" >> "$archivo"
done

# Mostramos todas las palabras guardadas en el archivo
echo "Las palabras guardadas en el archivo $archivo son:"
cat "$archivo"
´´´

´´´bash
#!/bin/bash

# Pedimos al usuario que introduzca el nombre del archivo donde se guardarán las palabras
read -p "Introduce el nombre del archivo donde se guardarán las palabras: " archivo

# Creamos el archivo si no existe y lo vaciamos si ya existe
> "$archivo"

# Leemos palabras hasta que se escriba ":q"
while true
do
  # Leemos una palabra desde la entrada estándar
  read -p "Escribe una palabra (escribe :q para salir): " palabra

  # Si se escribió ":q", salimos del ciclo while
  if [ "$palabra" = ":q" ]
  then
    break
  fi

  # Escribimos la palabra en el archivo de forma ordenada
  echo "$palabra" >> "$archivo"
  sort -o "$archivo" "$archivo"
done

# Mostramos todas las palabras guardadas en el archivo de forma ordenada
echo "Las palabras guardadas en el archivo $archivo son:"
cat "$archivo"
´´´

´´´bash
#!/bin/bash

# Pedimos al usuario que introduzca un número
read -p "Introduce un número: " numero

# Verificamos si el número se encuentra en el archivo numeros.txt
if grep -q "^$numero$" numeros.txt
then
  echo "El número $numero se encuentra en el archivo numeros.txt."
else
  echo "El número $numero NO se encuentra en el archivo numeros.txt."
fi
´´´

