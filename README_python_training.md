# Ejercicios Taller práctico
### 📌1. pedir nombre y edad 
```python
nombe = input("ingrese su nombre ")
edad = input("ingrese su edad ")
print(f"su nombre es {nombre} y su edad es {edad}")
```
### 📌2. Pide dos números enteros y muestra la suma de ambos
```python
num1 =int(input("ingrese el numero 1 "))
num2 =int(input("ingrese el numero 2 "))
suma = num1 + num2
print(f"la suma de los dos numeros es {suma}")
```
### 📌3. Pide dos números decimales (float) y muestra su multiplicación.
```python
num1 =float(input("ingrese el numero 1 "))
num2 =float(input("ingrese el numero 2 "))
multi = num1*num2
print(f"la multiplicacion de los dos numeros es {multi}")
```
### 📌4. Pide un número entero y muestra el doble y el triple de ese número, separados por coma.
```python
num1 =int(input("ingrese el numero "))
doble = num1*2
triple = num1*3
print(f"el doble del numero es {doble}, el triple es {triple}")
```

### 📌5. Pide al usuario una palabra y un número entero. Muestra la palabra repetida ese número de veces.
```python
palabra = input("Ingresa una palabra: ")
repeticiones = int(input("¿Cuántas veces quieres repetirla?: "))
print(palabra * repeticiones)

```
### 📌6. Pide al usuario dos números y muestra el resultado de dividir el primero entre el segundo.
```python
num1 =float(input("ingrese el numero 1 "))
num2 =float(input("ingrese el numero 2 "))
division = num1/num2
print(f"la division de los dos numeros es {division}")
```
### 📌7. Pide al usuario su nombre y muestra cuántas letras tiene su nombre.
```python
nombre = input("Ingresa tu nombre: ")
cantidad_letras = len(nombre.replace(" ", ""))
print(f"Tu nombre tiene {cantidad_letras} letras.")
# el .len se usa para reemplazar
```
### 📌8. Pide al usuario dos números y muestra la división entera (//) y el módulo (%) entre ellos.
```python
num1 =float(input("ingrese el numero 1 "))
num2 =float(input("ingrese el numero 2 "))
division = num1//num2
modulo = num1%num2
print(f"la division entera de los dos numeros es {division} y el modulo es {modulo}")
```
### 📌9. Pide al usuario dos números y muestra la suma, resta, multiplicación y división (separadas por coma).
```python
num1 = float(input("Ingresa el primer número: "))
num2 = float(input("Ingresa el segundo número: "))
suma = num1 + num2
resta = num1 - num2
multiplicacion = num1 * num2
if num2 != 0:
    division = num1 / num2
else:
    division = "infinito (no se puede dividir entre 0)"
print(f"{suma}, {resta}, {multiplicacion}, {division}")
```
### 📌10. Pide un número entero y muestra el número elevado a la 2 (al cuadrado) y a la 3 (al cubo), usando f-strings.
```python
num1 = int(input("ingresa el numero: "))
cuadrado = num1**2
cubo = num1**3
print(f"el numero al cuadrado es {cuadrado}, y al cubo es {cubo}")
```
### 📌11. Pide al usuario un número decimal y muestra solo la parte entera de ese número.
```python
num = float(input("ingrese el numero: "))
entera = int(num)
print(f"la parte entera del numero es {entera}")
#conversion de la variable
```
### 📌12. Pide al usuario su edad y muestra un mensaje que diga si su edad es mayor que 18 (usar operadores de comparación, sin condicionales)
```python
edad = int(input("ingresa tu edad: "))
mayor = edad >= 18
print(f"eres mayor de edad? {mayor}")
```
### 📌13. Pide al usuario dos números enteros y muestra si son iguales (usar operadores de comparación, sin condicionales).
```python
num1 = int(input("Ingresa el primer número: "))
num2 = int(input("Ingresa el segundo número: "))
iguales = num1==num2
print(f"son iguales los numeros? {iguales}")
```
### 📌14. Pide dos números y muestra si el primero es mayor que el segundo (usar operador de comparación).
```python
num1 = int(input("Ingresa el primer número: "))
num2 = int(input("Ingresa el segundo número: "))
mayor = num1>num2
print(f"el primer numero es mayor que el segundo? {mayor}")
```
### 📌15. Pide dos números y muestra si el primero es menor o igual que el segundo (usar operador de comparación).
```python
num1 = int(input("Ingresa el primer número: "))
num2 = int(input("Ingresa el segundo número: "))
menor = num1<=num2
print(f"el primer numero es menor que el segundo? {menor}")
```
### 📌16. Pide al usuario dos números y muestra si ambos son mayores que 10 (usar operador lógico and).
```python
num1 = int(input("Ingresa el primer número: "))
num2 = int(input("Ingresa el segundo número: "))
mayores = num1>=10 and num2>=10
print(f"ambos numeros son mayores a 10? {mayores}")
```
### 📌17. Pide al usuario dos números y muestra si al menos uno es mayor que 10 (usar operador lógico or).
```python
num1 = int(input("Ingresa el primer número: "))
num2 = int(input("Ingresa el segundo número: "))
mayores = num1>=10 or num2>=10
print(f"alguno de los numeros es mayor a 10? {mayores}")
```
### 📌18. Pide al usuario dos números y muestra si el primero NO es igual al segundo (usar operador lógico not combinado con comparación).
```python
num1 = int(input("Ingresa el primer número: "))
num2 = int(input("Ingresa el segundo número: "))
no_iguales = not (num1 == num2)
print(f"alguno de los numeros es mayor a 10? {no_iguales}")
```
### 📌19. Pide al usuario tres números, calcula el promedio y muestra el resultado.
```python
num1 = int(input("Ingresa el primer número: "))
num2 = int(input("Ingresa el segundo número: "))
num3 = int(input("Ingresa el tercer número: "))
promedio = (num1+num2+num3)/3
print(f"el promedio es {promedio}")
```
### 📌20. Pide al usuario un número entero y muestra si el número es divisible entre 5 (usar operador de módulo % y comparación
```python
num1 = int(input("Ingresa el primer número: "))
num2 = int(input("Ingresa el segundo número: "))
num3 = int(input("Ingresa el tercer número: "))
promedio = (num1+num2+num3)/3
print(f"el promedio es {promedio}")
```
