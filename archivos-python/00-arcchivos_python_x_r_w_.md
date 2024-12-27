# Manejo de archivos en Python

Los tipos de actividades que se pueden realizar en el archivo abierto están controlados por los Modos de Acceso. Estos describen cómo se utilizará el archivo después de haber sido abierto.

Estos Modos de Acceso también especifican dónde debe ubicarse el controlador de archivo dentro del archivo. Similar a un puntero, un controlador de archivo indica dónde se deben leer o colocar los datos en el archivo.

En Python, hay seis métodos o modos de acceso, que son:

1. **Solo lectura (`‘r’`)**: Este modo abre los archivos de texto solo para lectura. El inicio del archivo es donde se encuentra el controlador. Si el archivo no existe, se produce un error de I/O. Este es el modo predeterminado para abrir archivos.
2. **Leer y escribir (`‘r+’`)**: Este método abre el archivo tanto para lectura como para escritura. El inicio del archivo es donde se encuentra el controlador. Si el archivo no existe, se produce un error de I/O.
3. **Solo escritura (`‘w’`)**: Este modo abre el archivo solo para escritura. Los datos en los archivos existentes se modifican y sobrescriben. El inicio del archivo es donde se encuentra el controlador. Si el archivo aún no existe en la carpeta, se crea uno nuevo.
4. **Escribir y leer (`‘w+’`)**: Este modo abre el archivo tanto para lectura como para escritura. El texto se sobrescribe y se elimina de un archivo existente. El inicio del archivo es donde se encuentra el controlador.
5. **Solo agregar (`‘a’`)**: Este modo permite abrir el archivo para escritura. Si el archivo aún no existe, se crea uno nuevo. El controlador se establece al final del archivo. Los datos recién escritos se agregarán al final, siguiendo los datos escritos anteriormente.
6. **Agregar y leer (`‘a+’`)**: Usando este método, puedes leer y escribir en el archivo. Si el archivo aún no existe, se crea uno nuevo. El controlador se establece al final del archivo. El texto recién escrito se agregará al final, siguiendo los datos escritos anteriormente.

## Cómo crear archivos en Python

En Python, se utiliza la función `open()` con una de las siguientes opciones: – "x" o "w" – para crear un archivo nuevo:

- #### **_`"x"` – Crear_**:
  Este comando creará un archivo nuevo solo si no existe ningún archivo con ese nombre, de lo contrario, devolverá un error.

Ejemplo de cómo crear un archivo en Python usando el comando "x":

```python
#crear un archivo de texto con la función de comando "x"

f = open("myfile.txt", "x")
```

¡Hemos creado un nuevo archivo de texto vacío!, Pero si vuelves a intentar el código anterior, por ejemplo, si intentas crear un nuevo archivo con el mismo nombre que usaste anteriormente (si deseas reutilizar el nombre de archivo anterior), recibirás un error que te notificará que el archivo ya existe.

Se verá como la imagen a continuación:

```python
 line 1, in <module>
    f = open('myfile.txt', 'x')
        ^^^^^^^^^^^^^^^^^^^^^^^^
FileExistsError: [Errno 17] File exists: 'myfile.txt'
```

- #### `"w"` – Escribir :
  Este comando creará un nuevo archivo de texto, sin importar si hay un archivo en la memoria con el nuevo nombre especificado. No devuelve un error si encuentra un archivo existente con el mismo nombre, en su lugar, sobrescribirá el archivo existente.

Ejemplo de como crear un archivo con el comando "w":

```python
#creando un un texto con el el comando "w"

f = open("myfile.txt", "w")

#Este comando "w" también se puede utilizar para crear un archivo nuevo, pero a diferencia del comando "x", el comando "w" sobrescribirá cualquier archivo existente que se encuentre con el mismo nombre de archivo.
```

Con el código anterior, ya sea que el archivo exista o no exista en la memoria, aún puede continuar y usar ese código. Solo tenga en cuenta que sobrescribirá el archivo si encuentra un archivo existente con el mismo nombre.

---

## Cómo escribir en un archivo en Python

Existen dos métodos para escribir en un archivo en Python, que son:

### **El método `write()`**:

Esta función inserta la cadena en el archivo de texto en una sola línea.

Según el archivo que hemos creado anteriormente, la siguiente línea de código insertará la cadena en el archivo de texto creado, que es "myfile.txt."

```python
file.write("Hello There\n")
```

#### **El método `writelines()`**:

Esta función inserta varias cadenas al mismo tiempo. Se crea una lista de elementos de cadena y luego cada cadena se agrega al archivo de texto.

Usando el archivo creado anteriormente arriba, la siguiente línea de código insertará la cadena en el archivo de texto creado, que es "myfile.txt."

```python
f.writelines(["Hello World ", "You are welcome to Fcc\n"])
```

Ejemplo:

```python
#Este programa muestra cómo escribir datos en un archivo de texto.This

file = open("myfile.txt","w")
L = ["This is Lagos \n","This is Python \n","This is Fcc \n"]

#Asignando ["This is Lagos \n","This is Python \n","This is Fcc \n"] a
#la variable L, se puede usar cualquier letra o palabra de tu elección.
#Las variables son contenedores en los que se pueden almacenar valores.
#El \n se coloca para indicar el final de la línea.

file.write("Hello There \n")
file.writelines(L)
file.close()

# Usar close() para cambiar los modos de acceso a archivos
```

## Cómo leer desde un archivo de texto en Python

Hay tres métodos para leer datos de un archivo de texto en Python. Ellos son:

#### **El método `read()`**:

Esta función devuelve los bytes leídos como una cadena. Si no se especifica ninguna n, lee el archivo completo.
Ejemplo:

```python
f = open("myfiles.txt", "r")
#('r’) opens the text files for reading only
print(f.read())
#El "f.read" imprime los datos en el archivo de texto en la consola cuando se ejecuta.
```

#### **El método `readline()`**:

Esta función lee una línea de un archivo y la devuelve como una cadena. Lee como máximo n bytes para el n especificado. Pero incluso si n es mayor que la longitud de la línea, no lee más de una línea.

```python
f = open("myfiles.txt", "r")
print(f.readline())
```

#### **El método `readlines()`**:

Esta función lee todas las líneas y las devuelve como elementos de cadena en una lista, uno para cada línea.

Puedes leer las dos primeras líneas llamando readline() dos veces, leyendo las dos primeras líneas del archivo:

```python
f = open("myfiles.txt", "r")
print(f.readline())
print(f.readline())
```

## Cómo cerrar un archivo de texto en Python

Es una buena práctica cerrar siempre el archivo cuando se ha terminado con él.

#### Ejemplo para cerrar un archivo de texto:

Esta función cierra el archivo de texto cuando haya terminado de modificarlo:

```python
f = open("myfiles.txt", "r")
print(f.readline())
f.close()
```

La función `close()` al final del código le dice a Python, ya terminé con esta sección de creación o lectura, es como decir Fin.

##### Ejemplo:

El siguiente programa muestra más ejemplos de formas de leer y escribir datos en un archivo de texto. Cada línea de código tiene comentarios para ayudar a comprender lo que está sucediendo:

```python
# Programa para mostrar varias formas de leer y

# escribir datos en un archivo de texto.

file = open("myfile.txt","w")
L = ["This is Lagos \n","This is Python \n","This is Fcc \n"]

# Asignar ["This is Lagos \n","This is Python \n","This is Fcc \n"]

# a la variable L

#El \n se coloca para indicar fin de línea

file.write("Hello There \n")
file.writelines(L)
file.close()

# Usar close() para cambiar los modos de acceso a archivos

file = open("myfile.txt","r+")
print("Output of the Read function is ")
print(file.read())
print()

# La función seek(n) Mueve el puntero hacia el byte indicado,

# el byte desde el principio.

file.seek(0)

print( "The output of the Readline function is ")
print(file.readline())
print()

file.seek(0)

# Mostrar la diferencia entre lectura y línea de lectura

print("Output of Read(12) function is ")
print(file.read(12))
print()

file.seek(0)

print("Output of Readline(8) function is ")
print(file.readline(8))

file.seek(0)

# Función de lectura de líneas

print("Output of Readlines function is ")
print(file.readlines())
print()
file.close()
```

Este es el resultado del código anterior cuando se ejecuta en la consola. Se asignó "This is Lagos", "This is Python", y "This is Fcc" a "L" y luego se pidió que imprima, usando la función ''file.read''.

El código anterior muestra que la función `"readline()"` devuelve la letra según el número especificado, mientras que la función `"readlines()"` devuelve cada cadena asignada a "L", incluido \n. Es decir, la función "readlines()" imprimirá todos los datos del archivo.

```python
Output of the Read function is
Hello There
This is Lagos
This is Python
This is Fcc


The output of the Readline function is
Hello There


Output of Read(12) function is
Hello There

Output of Readline(8) function is
Hello Th
Output of Readlines function is
['Hello There \n', 'This is Lagos \n', 'This is Python \n', 'This is Fcc \n']

```

###### Conclusión

Con suerte, después de leer este tutorial, deberías comprender qué es el manejo de archivos en Python. También aprendimos los modos/métodos necesarios para crear, escribir, leer, y cerrar un archivo de texto usando algunos ejemplos básicos de Python.
