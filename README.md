# Reto_12

1. Consulte que hacen los siguientes métodos de strings en python: endswith, startswith, isalpha, isalnum, isdigit, isspace, istitle, islower, isupper.

2. Procesar el <a href="https://drive.google.com/file/d/1lGmlAz157fIDp2zk95KInTSJguZusI91/view?usp=sharing">archivo</a> y extraer:
 - Cantidad de vocales
```python
if __name__ == "__main__":

# Abre el archivo de texto, lo guarda en text y cierra el archivo
x = open("12.txt")
text = x.read()
x.close()

# Coloca text en minusculas
text = text.lower()

# Crea una lista con las vocales
y = ['a','e','i','o','u']

# Establece un contador
sum = int(0)

# Crea un bucle del tamaño de la cadena
for  j in text:

    # Comprueba que j sea un valor alfanumerico
    if j.isalpha():

        # compruba que j este en la lista y
        if j in y:

            # suma 1
            sum += 1
            
# imprime sum    
print(sum)
```
- Cantidad de consonantes
```python
if __name__ == "__main__":

# Abre el archivo de texto, lo guarda en text y cierra el archivo
x = open("12.txt")
text = x.read()
x.close()

# Coloca text en minusculas
text = text.lower()

# Crea una lista con las vocales
y = ['a','e','i','o','u']

# Establece un contador
sum = int(0)

# Crea un bucle del tamaño de la cadena
for  j in text:

    # Comprueba que j sea un valor alfanumerico
    if j.isalpha():

        # compruba que j no este en la lista y
        if j not in y:

            # suma 1
            sum += 1

# imprime sum    
print(sum)
```

##  LO ADMITO TUVE QUE USAR CHATGPT PARA HACER ESTO, NO ENCONTRE UNA FORMA DE HACERLO
![lv_0_20230530101004.gif](https://github.com/PCPCRACK/Reto_12/assets/127131700/1488757a-4b11-4cfd-9599-9f0fee3c9d81)
- Listado de las 50 palabras que más se repiten
```python
# Abre el archivo de texto, lo guarda en text y cierra el archivo
x = open("12.txt")
text = x.read()
x.close()

# Coloca text en minusculas y elimina la puntuacion
text = text.lower()
text = text.replace('.',' ').replace('?',' ').replace('!',' ').replace(',',' ')

# Divide el texto en palabras individuales
palabras = text.split()

# Crea un diccionaria para contar la frecuencia de cada palabra
contador = {}
for j in palabras:
    if j in contador:
        contador[j] += 1
    else:
        contador[j] = 1

# Obtener las palbras mas comunes, ordenando el diccionario en funcion de los valores y se toman las 50 palabras
PLC = sorted(contador.items(), key=lambda x: x[1], reverse = True)[:50]

# Crea un bucle con rango PLC en j, p
for j, p in PLC:
    print(f"{j}: {p}")
```
- Listado de destinatarios con cantidad de mensajes recibidos
```python
def encontrar_palabra(texto, palabra):
    palabras = texto.split()
    indice = None

    for i, p in enumerate(palabras):
        if p == palabra:
            indice = i
            break

    if indice is not None and indice + 1 < len(palabras):
        siguiente_palabra = palabras[indice + 1]
        return siguiente_palabra
    else:
        return None

texto = "Este es un ejemplo de texto. Quiero encontrar la palabra necesito y guardar la siguiente palabra después de ella."

palabra_buscada = "necesito"
siguiente_palabra = encontrar_palabra(texto, palabra_buscada)

if siguiente_palabra is not None:
    print(f"La siguiente palabra después de '{palabra_buscada}' es: {siguiente_palabra}")
else:
    print(f"No se encontró la palabra '{palabra_buscada}' en el texto.")

```
- Cantidad de mensajes enviados por cada día
```python

```
