# Taller-8
# EJERCICIO 1:
ventas = [
[12, 15, 10, 18],
[8, 14, 16, 12],
[20, 18, 15, 22]
]

# 1. Mostrar la matriz completa
print("===== MATRIZ DE VENTAS =====")
for i in range(len(ventas)):
print(f"Vendedor {i + 1}: {ventas[i]}")

# 2. Total de ventas por vendedor
print("\n===== TOTAL POR VENDEDOR =====")
totales_vendedores = []
for i in range(len(ventas)):
total = sum(ventas[i])
totales_vendedores.append(total)
print(f"Vendedor {i + 1}: {total} millones")

# 3. Total de ventas por semana
print("\n===== TOTAL POR SEMANA =====")
totales_semanas = []
for j in range(len(ventas[0])):
total = sum(fila[j] for fila in ventas)
totales_semanas.append(total)
print(f"Semana {j + 1}: {total} millones")

# 4. Vendedor con mayores ventas
mayor_vendedor = totales_vendedores.index(max(totales_vendedores))
print("\n===== MAYOR VENDEDOR =====")
print(f"Vendedor {mayor_vendedor + 1} con {max(totales_vendedores)} millones")

# 5. Semana con mayor volumen de ventas
mayor_semana = totales_semanas.index(max(totales_semanas))
print("\n===== MAYOR SEMANA =====")
print(f"Semana {mayor_semana + 1} con {max(totales_semanas)} millones")

# 6. Promedio general
suma_general = sum(valor for fila in ventas for valor in fila)
cantidad = sum(len(fila) for fila in ventas)
promedio = suma_general / cantidad
print("\n===== PROMEDIO GENERAL =====")
print(f"Promedio: {round(promedio, 2)} millones")

# 7. Modificar una venta
print("\n===== MODIFICAR UNA VENTA =====")
vendedor = int(input("Ingrese el vendedor (1, 2 o 3): "))
semana = int(input("Ingrese la semana (1, 2, 3 o 4): "))
nuevo_valor = float(input("Ingrese el nuevo valor: "))

if 1 <= vendedor <= 3 and 1 <= semana <= 4 and nuevo_valor >= 0:
ventas[vendedor - 1][semana - 1] = nuevo_valor

print("\nMatriz actualizada:")
for fila in ventas:
print(fila)

print("\nNuevos totales por vendedor:")
for i in range(len(ventas)):
total = sum(ventas[i])
print(f"Vendedor {i + 1}: {total}")

print("\nNuevos totales por semana:")
for j in range(len(ventas[0])):
total = sum(fila[j] for fila in ventas)
print(f"Semana {j + 1}: {total}")

suma_general = sum(valor for fila in ventas for valor in fila)
cantidad = sum(len(fila) for fila in ventas)
print(f"\nNuevo promedio general: {round(suma_general / cantidad, 2)}")
else:
print("Datos ingresados incorrectamente.")

# EJERCICIO 2:
curso_A = {
"Ana", "Carlos", "Laura", "Pedro",
"Sofia", "Andres", "Camila"
}

curso_B = {
"Laura", "Pedro", "Daniel", "Sofia",
"Mateo", "Valentina"
}

# 1. Mostrar estudiantes de cada curso
print("===== ESTUDIANTES POR CURSO =====")
print("Curso A:", curso_A)
print("Curso B:", curso_B)

# 2. Cantidad de estudiantes diferentes
todos = curso_A | curso_B
print("\n===== TOTAL DE ESTUDIANTES =====")
print("Cantidad de estudiantes diferentes:", len(todos))

# 3. Estudiantes inscritos en ambos cursos
ambos = curso_A & curso_B
print("\n===== ESTUDIANTES EN AMBOS CURSOS =====")
print(ambos)

# 4. Estudiantes únicamente del curso A
solo_A = curso_A - curso_B
print("\n===== SOLO CURSO A =====")
print(solo_A)

# 5. Estudiantes únicamente del curso B
solo_B = curso_B - curso_A
print("\n===== SOLO CURSO B =====")
print(solo_B)

# 6. Estudiantes inscritos exactamente en uno
exactamente_uno = curso_A ^ curso_B
print("\n===== ESTUDIANTES EN EXACTAMENTE UN CURSO =====")
print(exactamente_uno)

# 7. Determinar si todos los estudiantes de A están en B
print("\n===== COMPROBACION =====")
if curso_A.issubset(curso_B):
print("Todos los estudiantes del curso A están en el curso B.")
else:
print("No todos los estudiantes del curso A están en el curso B.")

# 8. Agregar un nuevo estudiante
print("\n===== AGREGAR ESTUDIANTE =====")
nombre = input("Ingrese el nombre del estudiante: ")
curso = input("¿A qué curso desea agregarlo? (A/B): ").upper()

if curso == "A":
curso_A.add(nombre)
print("Estudiante agregado al curso A.")
elif curso == "B":
curso_B.add(nombre)
print("Estudiante agregado al curso B.")
else:
print("Curso no válido.")

# Mostrar resultados actualizados
print("\n===== RESULTADOS ACTUALIZADOS =====")
print("Curso A:", curso_A)
print("Curso B:", curso_B)
print("Total de estudiantes:", len(curso_A | curso_B))
print("Estudiantes en ambos cursos:", curso_A & curso_B)
print("Solo curso A:", curso_A - curso_B)
print("Solo curso B:", curso_B - curso_A)
print("Exactamente un curso:", curso_A ^ curso_B)

if curso_A.issubset(curso_B):
print("Todos los estudiantes de A están en B.")
else:
print("No todos los estudiantes de A están en B.")
