# proyecto-UTEC-2018-01


# Abriendo el archivo
fileText = open( "d:\prueba.txt", "r" )
# Leyendo las palabras en un lista
listWord = fileText.read().split()
# Imprimiendo la lista
print(listWord)
# Cierra el archivo

texto = input("Ingrese un texto : ")
texto=texto.split(' ')
print(texto)

listaPosibles=[]
midiccionario={}
contador = 0
for palabra in texto:
    listaPosibles=[]
    if palabra not in listWord:
        for palabrax in listWord:
            if len(palabra) == len(palabrax):
                contador=0
                for i in range(len(palabra)):
                    if palabra[i] != palabrax[i]:
                        contador+=1
                if contador<2 and contador>0:
                    listaPosibles.append(palabrax)
                    midiccionario[palabra]=sorted(listaPosibles)


            elif len(palabra)<len(palabrax):
                diferencia=len(palabra) - len(palabrax)
                contador = (diferencia**(2))**(0.5)
                for i in range(len(palabra)):
                    if palabra[i] != palabrax[i]:
                        contador+=1
                if contador<3 and contador>0:
                    listaPosibles.append(palabrax)
                    midiccionario[palabra]=sorted(listaPosibles)
            elif len(palabra)>len(palabrax):
                diferencia=len(palabra) - len(palabrax)
                contador = (diferencia**(2))**(0.5)
                for i in range(len(palabrax)):
                    if palabra[i] != palabrax[i]:
                        contador+=1
                if contador<3 and contador>0:
                    listaPosibles.append(palabrax)
                    midiccionario[palabra]=sorted(listaPosibles)
print(midiccionario)
