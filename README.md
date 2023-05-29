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
```python
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
 - Listado de las 50 palabras que más se repiten
 - Listado de destinatarios con cantidad de mensajes recibidos
 - Cantidad de mensajes enviados por cada día
