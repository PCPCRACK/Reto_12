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

##  LO ADMITO TUVE QUE USAR CHATGPT PARA HACER ESTE PUNTO, NO ENCONTRE UNA FORMA DE HACERLO
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
if __name__ == "__main__":
    
    file = open("12.txt", "r")
    catalogador = {}
    archivados = []
    archivados2 = []
    contador = {}
    contador2 = {}
    for line in file.readlines():
        if line.upper().find('FROM') != -1:
            if line.upper().find('RECEIVED') != -1:
                z = line.split()
                archivados.append(z[2])
            elif line.upper().find('FROM') < 10:
                z = line.split()
                archivados2.append(z[1])

    for j in archivados:
        if j in contador:
            contador[j] += 1
        else:
            contador[j] = 1

    for j in archivados2:
        if j in contador2:
            contador2[j] += 1
        else:
            contador2[j] = 1

    for j,p in contador2.items():
        print(f"El usuario {j} envio {p} mensajes")

    print(" ")
    print(" ")

    for j,p in contador.items():
        print(f"El usuario {j} recibio {p} mensajes")
```
- Cantidad de mensajes enviados por cada día
```python

```
