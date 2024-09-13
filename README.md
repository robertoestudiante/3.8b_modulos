# 3.8b_modulos

from datetime import datetime, date   # importo la libreria

# pregunto la fecha de nacimiento del usuario
while True:
    fecha_cumpleaños = input("ingrese la fecha de nacimiento en este formato año, mes, dia: 1956, 10, 09  ")
    print(len(fecha_cumpleaños)) # muestro el largo de la cadena para hacer pruebas
    if len(fecha_cumpleaños) != 12: # reviso algo de formato
        print(" Ingrese la fecha con el formato correcto AAAA, MM, DD  -- incluidos espacios y comas")
        continue
    else: # sino se cumple lo anterior doy formato a la fecha
        d = datetime.strptime(fecha_cumpleaños, '%Y, %m, %d')
        break

def calculo (cumple): # defino una fincion que calcule la edad
    d = datetime.strptime(cumple, '%Y, %m, %d')
    actual = date.today()
    # hago comparaciones con los años, meses y fecha para calcular su edad
    if d.month == actual.month and d.day == actual.day:
        edad_1 = actual.year - d.year
        return edad_1
    elif d.month >= actual.month and d.day > actual.day:
        edad_2 = actual.year - d.year
        edad_2 -= 1
        return edad_2
    else:
        edad_3 = actual.year - d.year
        edad_3 -= 1
        return edad_3

# muestro la edad calculada
print(f" Tu edad es: ", calculo(fecha_cumpleaños), " años.")
