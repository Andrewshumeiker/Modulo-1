```python
estudiantes = {}

def añadir_estudiante():
    nombre = input("Nombre del estudiante: ").strip()
    if nombre:
        estudiantes[nombre] = []
        print("Estudiante añadido.")
    else:
        print("Nombre inválido.")

def registrar_calificaciones():
    nombre = input("Nombre del estudiante: ").strip()
    if nombre in estudiantes:
        try:
            calificacion = float(input("Calificación: "))
            estudiantes[nombre].append(calificacion)
            print("Calificación registrada.")
        except ValueError:
            print("Calificación inválida.")
    else:
        print("Estudiante no encontrado.")

def calcular_promedio():
    nombre = input("Nombre del estudiante: ").strip()
    if nombre in estudiantes and estudiantes[nombre]:
        promedio = sum(estudiantes[nombre]) / len(estudiantes[nombre])
        print(f"Promedio de {nombre}: {promedio:.2f}")
    else:
        print("Estudiante no encontrado o sin calificaciones.")

def menu_calificaciones():
    while True:
        print("\n--- GESTOR DE CALIFICACIONES ---")
        print("1. Añadir estudiante")
        print("2. Registrar calificación")
        print("3. Calcular promedio")
        print("0. Salir")

        opcion = input("Elige una opción: ").strip()
        if opcion == "1":
            añadir_estudiante()
        elif opcion == "2":
            registrar_calificaciones()
        elif opcion == "3":
            calcular_promedio()
        elif opcion == "0":
            break
        else:
            print("Opción inválida.")

if __name__ == "__main__":
    menu_calificaciones()
```

```python
menu = []

def añadir_plato():
    nombre = input("Nombre del plato: ").strip()
    try:
        precio = float(input("Precio: "))
        disponible = input("¿Está disponible? (s/n): ").lower() == 's'
        menu.append({"nombre": nombre, "precio": precio, "disponible": disponible})
        print("Plato añadido.")
    except ValueError:
        print("Datos inválidos.")

def cambiar_disponibilidad():
    nombre = input("Nombre del plato a cambiar: ").strip().lower()
    for plato in menu:
        if plato["nombre"].lower() == nombre:
            plato["disponible"] = not plato["disponible"]
            estado = "disponible" if plato["disponible"] else "no disponible"
            print(f"Estado cambiado a: {estado}")
            return
    print("Plato no encontrado.")

def contar_disponibles():
    total = sum(1 for plato in menu if plato["disponible"])
    print(f"Platos disponibles: {total}")

def menu_restaurante():
    while True:
        print("\n--- MENÚ DEL RESTAURANTE ---")
        print("1. Añadir plato")
        print("2. Cambiar disponibilidad")
        print("3. Contar disponibles")
        print("0. Salir")

        opcion = input("Elige una opción: ").strip()
        if opcion == "1":
            añadir_plato()
        elif opcion == "2":
            cambiar_disponibilidad()
        elif opcion == "3":
            contar_disponibles()
        elif opcion == "0":
            break
        else:
            print("Opción inválida.")

if __name__ == "__main__":
    menu_restaurante()
```

```python
almacen = {}

def añadir_caja():
    tipo = input("Tipo de caja: ").strip()
    try:
        cantidad = int(input("Cantidad inicial: "))
        almacen[tipo] = cantidad
        print("Caja añadida.")
    except ValueError:
        print("Cantidad inválida.")

def actualizar_cantidad():
    tipo = input("Tipo de caja: ").strip()
    if tipo in almacen:
        try:
            cambio = int(input("Cantidad a añadir (+) o quitar (-): "))
            nueva = almacen[tipo] + cambio
            if nueva < 0:
                print("Cantidad insuficiente.")
            else:
                almacen[tipo] = nueva
                print(f"Nueva cantidad: {almacen[tipo]}")
        except ValueError:
            print("Cantidad inválida.")
    else:
        print("Caja no encontrada.")

def verificar_cantidad():
    tipo = input("Tipo de caja: ").strip()
    try:
        requerida = int(input("Cantidad requerida: "))
        if almacen.get(tipo, 0) >= requerida:
            print("Cantidad suficiente.")
        else:
            print("No hay suficiente cantidad.")
    except ValueError:
        print("Cantidad inválida.")

def menu_almacen():
    while True:
        print("\n--- GESTOR DE ALMACÉN ---")
        print("1. Añadir tipo de caja")
        print("2. Actualizar cantidad")
        print("3. Verificar cantidad")
        print("0. Salir")

        opcion = input("Elige una opción: ").strip()
        if opcion == "1":
            añadir_caja()
        elif opcion == "2":
            actualizar_cantidad()
        elif opcion == "3":
            verificar_cantidad()
        elif opcion == "0":
            break
        else:
            print("Opción inválida.")

if __name__ == "__main__":
    menu_almacen()
```



```python
biblioteca = []

def añadir_libro():
    titulo = input("Título del libro: ").strip()
    autor = input("Autor: ").strip()
    try:
        paginas = int(input("Número de páginas: "))
        biblioteca.append({"titulo": titulo, "autor": autor, "paginas": paginas})
        print("Libro añadido.")
    except ValueError:
        print("Número de páginas inválido.")

def buscar_libro():
    consulta = input("Buscar por título: ").strip().lower()
    resultados = [libro for libro in biblioteca if consulta in libro["titulo"].lower()]
    if resultados:
        print("\n--- Resultados ---")
        for libro in resultados:
            print(f"{libro['titulo']} - {libro['autor']} ({libro['paginas']} páginas)")
    else:
        print("No se encontraron libros.")

def mostrar_todos():
    if biblioteca:
        print("\n--- LIBROS EN LA BIBLIOTECA ---")
        for libro in biblioteca:
            print(f"{libro['titulo']} - {libro['autor']} ({libro['paginas']} páginas)")
    else:
        print("La biblioteca está vacía.")

def menu_libreria():
    while True:
        print("\n--- BIBLIOTECA VIRTUAL ---")
        print("1. Añadir libro")
        print("2. Buscar libro")
        print("3. Mostrar todos")
        print("0. Salir")

        opcion = input("Elige una opción: ").strip()
        if opcion == "1":
            añadir_libro()
        elif opcion == "2":
            buscar_libro()
        elif opcion == "3":
            mostrar_todos()
        elif opcion == "0":
            break
        else:
            print("Opción inválida.")

if __name__ == "__main__":
    menu_libreria()
```
```python
