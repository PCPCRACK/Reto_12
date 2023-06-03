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

# Crea un diccionaria
contador = {}

# Crea un bucle para cada palabra en palabras
for j in palabras:

    # Si j esta en el diccionario contador le suma 1 sino la añade
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

    # Abre el archivo
    file = open("12.txt", "r")

    # Crea 3 diccionarios y 2 listas
    archivados = []
    archivados2 = []
    catalogador = {}
    contador = {}
    contador2 = {}

    # Lee el archivo por lineas
    for line in file.readlines():

        # Vuelve mayuscula la linea y busca la palabra("FROM")
        if line.upper().find('FROM') != -1:

            # Vuelve mayuscula la linea y busca la palabra("RECEIVED")
            if line.upper().find('RECEIVED') != -1:

                # Separa la linea por palabras
                z = line.split()

                # Añade la palabra despues del FROM 
                archivados.append(z[2])

            # Vuelve mayuscula la linea y busca la palabra("FROM") y si el resultado de find es menor a 10
            else line.upper().find('FROM') < 10:

                # Separa la linea por palabras
                z = line.split()

                # Añade la palabra despues del FROM 
                archivados2.append(z[1])
    # Cierra el archivo
    file.close()

    # Crea un bucle para cada palabra de archivados
    for j in archivados:

        # Si j esta en el diccionario contador le suma 1 sino la añade
        if j in contador:
            contador[j] += 1
        else:
            contador[j] = 1

    # Crea un bucle para cada palabra de archivados2
    for j in archivados2:

        # Si j esta en el diccionario contador2 le suma 1 sino la añade
        if j in contador2:
            contador2[j] += 1
        else:
            contador2[j] = 1

    # Crea un bucle para j y p para los items del contador2
    for j,p in contador2.items():
        print(f"El usuario {j} envio {p} mensajes")


    # Imprime dos espacios para diferenciar
    print(" ")
    print(" ")

    # Crea un bucle para j y p para los items del contador
    for j,p in contador.items():
        print(f"El usuario {j} recibio {p} mensajes")
```
- Cantidad de mensajes enviados por cada día
```python
if __name__ == "__main__":

    # Abre el archivo
    file = open("12.txt", "r")

    # Crea 3 listas y 1 diccionario
    Separador = []
    juntador = []
    ya = []
    Calendario = {}

    Crea un contador igual a 2
    sum = int(2)

    # Lee el archivo por lineas
    for linea in file.readlines():

        # Vuelve mayuscula la linea y busca la palabra("DATE:") y si el resultado de find es diferente de -1
        if linea.upper().find('DATE:') != -1:

            # Si la division por residuo de sum es igual a 0
            if sum%2 == 0:

                # Separa linea por palabras
                z = linea.split()

                # Remueve la primera palaba
                z.pop(0)

                # Crea un bucle en el tamaño de z -3
                for h in range(len(z)-3):

                    # Remueve la ultima palabra de la lista z
                    z.pop()

                # Ya se vuelve z y ya se vuelve un cadena de caracteres
                ya = z
                ya = str(ya)

                # remplaza ',',"'",']'y'[' por espacios
                ya = ya.replace(',','').replace("'",'').replace('[','').replace(']','')

                # se agrega ya a la lista seoarador
                Separador.append(ya)

            # En cada ciclo suma 1 a sum
            sum += 1

    # Crea un bucle para cada elemento de Separador
    for j in Separador:
        # Si j esta en el diccionario separador suma 1 sino lo añade al diccionario calendario
        if j in Calendario:
            Calendario[j] +=1
        else:
            Calendario[j] =1

    # Crea un bucle para j y p para los items del calendario
    for j,p in Calendario.items():
        print(f"El dia {j} se enviaron {p} mensajes")
```
