# Ejercicios Modulo 1 semana 1, validador de descuento
### 📌 1.alarmaSafe
```python
"""
Un sistema de seguridad para el hogar necesita monitorear posibles intrusiones bajo estas condiciones:

    Se detecta movimiento en el interior de la propiedad (activado por sensores).

    Además, debe cumplirse al menos una de estas situaciones:

        Alguna ventana está abierta o

        Es horario nocturno (entre las 10 PM y 6 AM)

Cuando ambas condiciones principales se cumplen, se activa la alarma; en cualquier otro caso, el sistema permanece en estado seguro.
"""

# Variables
movimiento = True
ventana_abierta = False
hora_noche = False

# Operadores lógicos
if  movimiento and (ventana_abierta or hora_noche):
    print("¡ALARMA! 🚨")
else:
    print("Todo seguro 🔒")
```
### 📌 2.calDescuento
```python
"""
Una tienda ofrece un descuento del 15% bajo estas condiciones:

    El cliente debe gastar más de $100 en su compra.

    Además, debe cumplir al menos una de estas opciones:

        Ser miembro del programa de fidelidad o

        No gastar más de $200 (para evitar combinar descuentos)

Si no se cumplen estas condiciones, no se aplicará ningún descuento.
"""

# Variables
es_miembro = False
total_compra = 300

# Operadores lógicos y not
if total_compra > 100 and (es_miembro or  total_compra < 200):
    print("Descuento del 15% aplicado 🎉")
else:
    print("Sin descuento 😢")
```
### 📌 2.calculadora2
```python
print("1. Suma")
print("2. Resta")
opcion = input("Elige una opción (1/2): ")

num1 = float(input("Primer número: "))
num2 = float(input("Segundo número: "))

if opcion == "1" :
    print(f"Resultado: {num1 + num2}")
elif opcion == "2":
        print(f"Resultado: {num1 - num2}")
else:
        print("Opción inválida.")
```
### 📌 4.calculadora
```python
def calculadora():
    print("1. suma")
    print("2. Resta")
    opcion = input("Elige una opcion (1/2) ")

    num1 = float(input("primer numero "))
    num2 = float (input("Segundo numero "))

    if opcion == "1":
        print(f"Resultado {num1 + num2}")
    elif opcion =="2":
        print(f"Resultado: {num1-num2}")

calculadora()    
```
### 📌 5.aprobacionPres
```python
#Programa 2: Aprobación de préstamo
"""
Un banco evalúa solicitudes de préstamo bajo dos criterios principales: (1) el solicitante debe tener un ingreso mensual mayor a $2000 o una puntuación de crédito de al menos 650, y (2) no debe tener deudas pendientes. Si cumple estas condiciones, el préstamo se aprueba; en caso contrario, se rechaza."
"""

# Variables
ingreso_mensual = 250
deuda = 0
puntuacion_credito = 70

# Operadores lógicos
if (ingreso_mensual >= 2000 or puntuacion_credito >=650 ) and deuda == 0:
    print("Préstamo aprobado 💰")
else:
    print("Préstamo rechazado 🚫")
```
### 📌 6.verificacion
```python
'''
    Verificar si una persona puede acceder a un evento exclusivo. Para ello, debe ser mayor de edad (18 años o más) y contar con un permiso especial. Si cumple ambas condiciones, se le concederá el acceso; de lo contrario, se le denegará."
'''
# Variables
edad = 18
tiene_permiso = True

# Operadores lógicos
if edad>= 18 and tiene_permiso:
    print("Acceso concedido ✅")
else:
    print("Acceso denegado ❌")
```
### 📌 7.esMiembro
```python
"""
Una tienda ofrece un descuento del 15% bajo estas condiciones:

    El cliente debe gastar más de $100 en su compra.

    Además, debe cumplir al menos una de estas opciones:

        Ser miembro del programa de fidelidad o

        No gastar más de $200 (para evitar combinar descuentos)

Si no se cumplen estas condiciones, no se aplicará ningún descuento.
"""

# Variables
es_miembro = True
total_compra = 120

# Operadores lógicos y not
if total_compra < 200 and (es_miembro and total_compra > 100):
    print("Descuento del 15% aplicado 🎉")
else:
    print("Sin descuento 😢")
```
