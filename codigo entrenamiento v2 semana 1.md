# Ejercicios Modulo 1 semana 1, validador de descuento
### 📌 ejercicio de entrenamiento 
```python
#Función que solicita al usuario un número decimal (float)
#Repite la solicitud hasta que se ingrese un valor válido
def pedir_float(mensaje):
    while True:
        try:
            return float(input(mensaje))
        except ValueError:
            print("Por favor, ingrese un número decimal válido.")
#Funcion que solicita al usuario un número entero(int)
#Repite la solicitud hasta que se ingrese un valor válido
def pedir_int(mensaje):
    while True:
        try:
            return int(input(mensaje))
        except ValueError:
            print("Por favor, ingrese un número entero válido.")
#Funcion que solicita al usuario una cadena de texto no vacía
#Elimina espacios al principio y al final y se repite hasta obtener un valor no vacío
def pedir_str(mensaje):
    while True:
        dato = input(mensaje).strip()
        if dato:
            return dato
        else:
            print("Este campo no puede estar vacío.")

# Entrada de datos con validación basica
nombre = pedir_str("Ingrese el nombre del producto: ")
prz_unit = pedir_float("Ingrese el precio unitario: ")
cantidad = pedir_int("Ingrese la cantidad de productos: ")
percent = pedir_int("Ingrese el porcentaje de descuento: ")

# Validaciones de los valores ingresados
if cantidad <= 0:
    print("La cantidad del producto debe ser entera y positiva.")
elif prz_unit <= 0:
    print("El precio del producto debe ser válido.")
elif percent < 0 or percent > 100:
    print("El porcentaje de descuento debe estar entre 0 y 100.")
else:
#calculo del costo total sin descuento
    costo = prz_unit * cantidad
#cálculo del monto del descuento
    costo_descuento = (costo * percent) / 100
#cálculo del costo final aplicando el descuento
    costo_final = costo - costo_descuento
#impresión de resultados en una tabla
    print("\n{:<15} {:<10} {:<15} {:<20} {:<20} {:<20}".format(
        "Nombre", "Cantidad", "Precio unitario", "Porcentaje de descuento", "Costo sin descuento", "Costo con descuento"
    ))
    print("-" * 110)
    print("{:<15} {:<10} {:<15.2f} {:<20} ${:<19.2f} ${:<20.2f}".format(
        nombre, cantidad, prz_unit, f"{percent}%", costo, costo_final
    ))
```
