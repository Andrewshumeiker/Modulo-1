# Ejercicios Modulo 1 semana 1, validador de descuento
### 📌 ejercicio de entrenamiento 
```python
def pedir_float(mensaje):
    while True:
        try:
            return float(input(mensaje))
        except ValueError:
            print("Por favor, ingrese un número decimal válido.")
#numero y precio deben ser positivos y descuento dentro del rango 0 a 100%
def pedir_int(mensaje):
    while True:
        try:
            return int(input(mensaje))
        except ValueError:
            print("Por favor, ingrese un número entero válido.")

def pedir_str(mensaje):
    while True:
        dato = input(mensaje).strip()
        if dato:
            return dato
        else:
            print("Este campo no puede estar vacío.")

# Entrada de datos con validación
nombre = pedir_str("Ingrese el nombre del producto: ")
prz_unit = pedir_float("Ingrese el precio unitario: ")
cantidad = pedir_int("Ingrese la cantidad de productos: ")
percent = pedir_int("Ingrese el porcentaje de descuento: ")

# Validaciones
if cantidad <= 0:
    print("La cantidad del producto debe ser entera y positiva.")
elif prz_unit <= 0:
    print("El precio del producto debe ser válido.")
elif percent < 0 or percent > 100:
    print("El porcentaje de descuento debe estar entre 0 y 100.")
else:
    costo = prz_unit * cantidad
    costo_descuento = (costo * percent) / 100
    costo_final = costo - costo_descuento

    print("\n{:<15} {:<10} {:<15} {:<20} {:<20} {:<20}".format(
        "Nombre", "Cantidad", "Precio unitario", "Porcentaje de descuento", "Costo sin descuento", "Costo con descuento"
    ))
    print("-" * 110)
    print("{:<15} {:<10} {:<15.2f} {:<20} ${:<19.2f} ${:<20.2f}".format(
        nombre, cantidad, prz_unit, f"{percent}%", costo, costo_final
    ))
```
