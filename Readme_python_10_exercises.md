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
movies = []

# Add a new movie to the list
def add_movie():
    title = input("Enter the movie title: ").strip()
    if not title:
        print("Title cannot be empty.")
        return
    for movie in movies:
        if movie['title'].lower() == title.lower():
            print("This movie already exists.")
            return
    movies.append({'title': title, 'ratings': []})
    print(f"Movie '{title}' added successfully.")

# Register a rating for a movie
def rate_movie():
    if not movies:
        print("No movies available.")
        return
    title = input("Enter the movie title to rate: ").strip()
    for movie in movies:
        if movie['title'].lower() == title.lower():
            try:
                rating = int(input("Enter rating (1–5): "))
                if 1 <= rating <= 5:
                    movie['ratings'].append(rating)
                    print("Rating added successfully.")
                else:
                    print("Rating must be between 1 and 5.")
            except ValueError:
                print("Please enter a valid number.")
            return
    print("Movie not found.")

# Show average rating for each movie
def show_ratings():
    if not movies:
        print("No movies registered yet.")
        return
    for movie in movies:
        title = movie['title']
        ratings = movie['ratings']
        if ratings:
            avg = sum(ratings) / len(ratings)
            print(f"{title}: Average rating = {avg:.2f}")
        else:
            print(f"{title}: No ratings yet.")

# User menu
def movie_menu():
    while True:
        print("\n--- Movie Rating System ---")
        print("1. Add movie")
        print("2. Rate a movie")
        print("3. Show average ratings")
        print("4. Exit")
        choice = input("Choose an option: ")
        if choice == "1":
            add_movie()
        elif choice == "2":
            rate_movie()
        elif choice == "3":
            show_ratings()
        elif choice == "4":
            print("Exiting...")
            break
        else:
            print("Invalid option. Try again.")

# Main entry point
if __name__ == "__main__":
    movie_menu()
```
```python 
# course_tracker.py

courses = []

def add_course():
    title = input("Course title: ").strip()
    try:
        duration = int(input("Duration (hours): "))
        enrolled = int(input("Number of students enrolled: "))
        if duration < 0 or enrolled < 0:
            raise ValueError
    except ValueError:
        print("Invalid input.")
        return
    courses.append({'title': title, 'duration': duration, 'enrolled': enrolled})
    print(f"Course '{title}' added.")

def update_enrollment():
    title = input("Course to update: ").strip()
    for course in courses:
        if course['title'].lower() == title.lower():
            try:
                enrolled = int(input("New number of students: "))
                if enrolled < 0:
                    raise ValueError
                course['enrolled'] = enrolled
                print("Enrollment updated.")
            except ValueError:
                print("Invalid number.")
            return
    print("Course not found.")

def filter_by_duration():
    try:
        min_duration = int(input("Minimum duration (hours): "))
        for course in courses:
            if course['duration'] >= min_duration:
                print(f"{course['title']} - {course['duration']} hours")
    except ValueError:
        print("Invalid duration.")

def course_menu():
    while True:
        print("\n--- Course Tracker ---")
        print("1. Add Course")
        print("2. Update Enrollment")
        print("3. Filter by Duration")
        print("4. Exit")
        opt = input("Choose: ")
        if opt == "1":
            add_course()
        elif opt == "2":
            update_enrollment()
        elif opt == "3":
            filter_by_duration()
        elif opt == "4":
            break
        else:
            print("Invalid option.")

if __name__ == "__main__":
    course_menu()
```
```python
# todo_list.py

tasks = []

def add_task():
    desc = input("Task description: ").strip()
    priority = input("Priority (low/medium/high): ").lower()
    tasks.append({'desc': desc, 'priority': priority, 'done': False})
    print("Task added.")

def mark_done():
    desc = input("Task to mark as done: ").strip()
    for task in tasks:
        if task['desc'].lower() == desc.lower():
            task['done'] = True
            print("Marked as completed.")
            return
    print("Task not found.")

def filter_tasks():
    print("1. Filter by priority")
    print("2. Filter by status")
    opt = input("Choose: ")
    if opt == "1":
        level = input("Priority level: ").lower()
        for task in tasks:
            if task['priority'] == level:
                print(task)
    elif opt == "2":
        status = input("Status (done/pending): ").lower()
        for task in tasks:
            if (status == "done" and task['done']) or (status == "pending" and not task['done']):
                print(task)

def todo_menu():
    while True:
        print("\n--- To-Do List ---")
        print("1. Add Task")
        print("2. Mark as Done")
        print("3. Filter Tasks")
        print("4. Exit")
        opt = input("Choose: ")
        if opt == "1":
            add_task()
        elif opt == "2":
            mark_done()
        elif opt == "3":
            filter_tasks()
        elif opt == "4":
            break

if __name__ == "__main__":
    todo_menu()
```
```python
# digital_wallet.py

expenses = []

def add_expense():
    category = input("Category: ").strip()
    try:
        amount = float(input("Amount: "))
        if amount < 0:
            raise ValueError
        expenses.append({'category': category, 'amount': amount})
        print("Expense recorded.")
    except ValueError:
        print("Invalid amount.")

def total_expenses():
    total = sum(e['amount'] for e in expenses)
    print(f"Total spent: ${total:.2f}")

def category_percentages():
    total = sum(e['amount'] for e in expenses)
    if total == 0:
        print("No expenses.")
        return
    categories = {}
    for e in expenses:
        categories[e['category']] = categories.get(e['category'], 0) + e['amount']
    for cat, amt in categories.items():
        print(f"{cat}: {amt / total * 100:.2f}%")

def wallet_menu():
    while True:
        print("\n--- Digital Wallet ---")
        print("1. Add Expense")
        print("2. Total Expenses")
        print("3. Category Percentages")
        print("4. Exit")
        opt = input("Choose: ")
        if opt == "1":
            add_expense()
        elif opt == "2":
            total_expenses()
        elif opt == "3":
            category_percentages()
        elif opt == "4":
            break

if __name__ == "__main__":
    wallet_menu()
```
```python
# pet_center.py

pets = []

def add_pet():
    name = input("Name: ").strip()
    species = input("Species: ").strip()
    try:
        age = int(input("Age: "))
        if age < 0:
            raise ValueError
        pets.append({'name': name, 'species': species, 'age': age})
        print("Pet added.")
    except ValueError:
        print("Invalid age.")

def search_species():
    specie = input("Species to search: ").strip()
    for pet in pets:
        if pet['species'].lower() == specie.lower():
            print(pet)

def filter_by_age():
    try:
        max_age = int(input("Max age: "))
        for pet in pets:
            if pet['age'] <= max_age:
                print(pet)
    except ValueError:
        print("Invalid age.")

def pet_menu():
    while True:
        print("\n--- Pet Adoption Center ---")
        print("1. Add Pet")
        print("2. Search by Species")
        print("3. Filter by Age")
        print("4. Exit")
        opt = input("Choose: ")
        if opt == "1":
            add_pet()
        elif opt == "2":
            search_species()
        elif opt == "3":
            filter_by_age()
        elif opt == "4":
            break

if __name__ == "__main__":
    pet_menu()
```
```python
# gym_membership.py

members = []

# Register new member
def register_member(name, plan):
    if not name.strip():
        raise ValueError("Name cannot be empty.")
    if plan.lower() not in ["monthly", "quarterly", "yearly"]:
        raise ValueError("Invalid plan. Use: monthly, quarterly, or yearly.")
    
    members.append({
        "name": name.strip(),
        "plan": plan.lower(),
        "is_up_to_date": True
    })
    print(f"Member '{name}' registered with plan '{plan}'.")

# Change membership plan
def change_plan(name, new_plan):
    for member in members:
        if member["name"].lower() == name.lower():
            if new_plan.lower() not in ["monthly", "quarterly", "yearly"]:
                raise ValueError("Invalid plan. Use: monthly, quarterly, or yearly.")
            member["plan"] = new_plan.lower()
            print(f"Plan for '{name}' updated to '{new_plan}'.")
            return
    raise ValueError("Member not found.")

# Mark payment as overdue
def mark_as_overdue(name):
    for member in members:
        if member["name"].lower() == name.lower():
            member["is_up_to_date"] = False
            print(f"Member '{name}' marked as overdue.")
            return
    raise ValueError("Member not found.")

# Mark payment as up to date (remove overdue status)
def mark_as_up_to_date(name):
    for member in members:
        if member["name"].lower() == name.lower():
            member["is_up_to_date"] = True
            print(f"Member '{name}' is now up-to-date with payment.")
            return
    raise ValueError("Member not found.")

# List members with overdue payments
def list_overdue_members():
    overdue = [m for m in members if not m["is_up_to_date"]]
    if overdue:
        print("\n--- Members with overdue payments ---")
        for m in overdue:
            print(f"{m['name']} ({m['plan']})")
    else:
        print("All members are up-to-date.")

# Main menu
def gym_menu():
    while True:
        print("\n--- Gym Membership System ---")
        print("1. Register new member")
        print("2. Change membership plan")
        print("3. Mark payment as overdue")
        print("4. Mark payment as up-to-date")
        print("5. List members with overdue payments")
        print("6. Exit")
        
        choice = input("Choose an option: ")
        
        try:
            if choice == "1":
                name = input("Member name: ")
                plan = input("Plan (monthly/quarterly/yearly): ")
                register_member(name, plan)
            elif choice == "2":
                name = input("Member name: ")
                new_plan = input("New plan (monthly/quarterly/yearly): ")
                change_plan(name, new_plan)
            elif choice == "3":
                name = input("Member name to mark as overdue: ")
                mark_as_overdue(name)
            elif choice == "4":
                name = input("Member name to mark as up-to-date: ")
                mark_as_up_to_date(name)
            elif choice == "5":
                list_overdue_members()
            elif choice == "6":
                print("Exiting the system...")
                break
            else:
                print("Invalid option.")
        except ValueError as e:
            print(f"Error: {e}")

# Main entry point
if __name__ == "__main__":
    gym_menu()

```
