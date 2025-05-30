# ejercicios-60
# 1. Sumar dos números
a, b = map(int, input("Ingrese dos números: ").split())
print(a + b)

# 2. Celsius a Fahrenheit
c = float(input("Celsius: "))
print((c * 9/5) + 32)

# 3. Par o impar
n = int(input("Número: "))
print("Par" if n % 2 == 0 else "Impar")

# 4. Área de un círculo
import math
r = float(input("Radio: "))
print(math.pi * r**2)

# 5. Intercambiar valores
a, b = input("a y b: ").split()
a, b = b, a
print(a, b)

# 6. Positivo, negativo o cero
n = int(input("Número: "))
print("Positivo" if n > 0 else "Negativo" if n < 0 else "Cero")

# 7. Mayor de tres números
a, b, c = map(int, input("Tres números: ").split())
print(max(a, b, c))

# 8. Tabla de multiplicar
n = int(input("Número: "))
for i in range(1, 11): print(f"{n} x {i} = {n*i}")

# 9. Factorial
n = int(input("Número: "))
f = 1
for i in range(1, n+1): f *= i
print(f)

# 10. Invertir número
n = input("Número: ")
print(n[::-1])

# 11. Contar dígitos
n = input("Número: ")
print(len(n))

# 12. Sumar dígitos
print(sum(int(d) for d in input("Número: ")))

# 13. Verificar primo
n = int(input("Número: "))
print("Primo" if n > 1 and all(n % i for i in range(2, int(n**0.5)+1)) else "No primo")

# 14. Año bisiesto
a = int(input("Año: "))
print("Bisiesto" if a%4==0 and (a%100!=0 or a%400==0) else "No bisiesto")

# 15. Suma primeros N naturales
n = int(input("N: "))
print(sum(range(1, n+1)))

# 16. Mínimo y máximo en lista
l = list(map(int, input("Lista: ").split()))
print(min(l), max(l))

# 17. Promedio lista
print(sum(l)/len(l))

# 18. Pares e impares en lista
pares = sum(1 for x in l if x % 2 == 0)
print(f"Pares: {pares}, Impares: {len(l)-pares}")

# 19. Ordenar lista
print(sorted(l))

# 20. Palíndromo
s = input("Palabra: ")
print("Palíndromo" if s == s[::-1] else "No")

# 21. Decimal a binario
print(bin(int(input("Número: ")))[2:])

# 22. Número aleatorio
import random
print(random.randint(1, 100))

# 23. Suma de pares hasta N
n = int(input("N: "))
print(sum(i for i in range(2, n+1, 2)))

# 24. MCD
import math
a, b = map(int, input("Dos números: ").split())
print(math.gcd(a, b))

# 25. MCM
def mcm(a,b): return abs(a*b)//math.gcd(a,b)
print(mcm(a, b))

# 26. Lanzar dado
print(random.randint(1, 6))

# 27. Frecuencia de letras
from collections import Counter
print(Counter(input("Texto: ").replace(" ", "")))

# 28. Segundo más grande
l = list(set(l))
l.sort()
print(l[-2])

# 29. Rotar lista a la derecha
l = l[-1:] + l[:-1]
print(l)

# 30. Calculadora simple
a, op, b = input("Ejemplo: 3 + 4\n").split()
a, b = int(a), int(b)
print(eval(f"{a}{op}{b}"))

# 31. Contar ocurrencias de un número
x = int(input("Número a contar: "))
print(l.count(x))

# 32. Concatenar sin usar +
l2 = list(map(int, input("Otra lista: ").split()))
for i in l2: l.append(i)
print(l)

# 33. Más repetido
print(max(set(l), key=l.count))

# 34. Anagramas
a, b = input("Dos palabras: ").split()
print("Anagramas" if sorted(a) == sorted(b) else "No")

# 35. Índice primera ocurrencia
x = int(input("Buscar: "))
print(l.index(x) if x in l else -1)

# 36. Pirámide de asteriscos
n = int(input("N: "))
for i in range(1, n+1): print('*' * i)

# 37. Pangrama
import string
s = input("Texto: ").lower()
print("Pangrama" if all(c in s for c in string.ascii_lowercase) else "No")

# 38. Cifrado César
s, k = input("Texto y desplazamiento: ").split()
k = int(k)
print(''.join(chr((ord(c) - 97 + k) % 26 + 97) if c.isalpha() else c for c in s.lower()))

# 39. Torres de Hanói (3 discos)
def hanoi(n, o, a, d):
    if n: hanoi(n-1, o, d, a); print(f"{o} -> {d}"); hanoi(n-1, a, o, d)
hanoi(3, 'A', 'B', 'C')

# 40. Invertir lista sin reverse
print(l[::-1])

# 41. Generador de contraseñas
import string, random
print(''.join(random.choices(string.ascii_letters + string.digits, k=10)))

# 42. Comprimir cadena
s = input("Cadena: ")
res = s[0] + ''.join(s[i] for i in range(1, len(s)) if s[i] != s[i-1])
print(res)

# 43. Número faltante
n = int(input("N: "))
l = list(map(int, input("Lista: ").split()))
print(set(range(1, n+1)).difference(l))

# 44. Piedra, papel o tijeras
opc = ["piedra", "papel", "tijeras"]
j1, j2 = input("Jugador 1 y 2: ").split()
if j1 == j2: print("Empate")
elif (j1, j2) in [("piedra", "tijeras"), ("tijeras", "papel"), ("papel", "piedra")]: print("Gana jugador 1")
else: print("Gana jugador 2")

# 45. Primos hasta N
n = int(input("Hasta: "))
for i in range(2, n+1):
    if all(i % j for j in range(2, int(i**0.5)+1)): print(i, end=' ')

# 46. Reservas cine (simple)
reservas = {}
nombre = input("Nombre: ")
asiento = input("Asiento: ")
reservas[asiento] = nombre
print(reservas)

# 47. Sistema de notas
notas = list(map(float, input("Notas: ").split()))
print("Promedio:", sum(notas)/len(notas))

# 48. Conversor de moneda
valor = float(input("USD: "))
print("COP:", valor * 4000)

# 49. Adivinanza
num = random.randint(1, 10)
while int(input("Adivina (1-10): ")) != num: print("Intenta de nuevo")
print("¡Correcto!")

# 50. Autenticación
users = {"admin": "1234"}
u, p = input("Usuario: "), input("Clave: ")
print("Acceso" if users.get(u) == p else "Denegado")

# 51. Analizador de expresiones
print(eval(input("Expresión matemática: ")))

# 52. Sistema de votación
votos = {}
for _ in range(3): c = input("Voto: "); votos[c] = votos.get(c, 0) + 1
print(votos)

# 53. Sistema de puntuaciones
juegos = list(map(int, input("Puntajes: ").split()))
print("Puntuación máxima:", max(juegos))

# 54. Calculadora calorías
cal = {"manzana": 52, "pan": 265}
print(sum(cal[i] for i in input("Alimentos: ").split()))

# 55. IMC
p, a = map(float, input("Peso (kg) y Altura (m): ").split())
print("IMC:", p/a**2)

# 56. Mayor número lista
print(max(l))

# 57. Menor número lista
print(min(l))

# 58. Quitar primer elemento
print(l[1:])

# 59. Promedio de lista
print(sum(l)/len(l))

# 60. Soluciones ecuación cuadrática
import cmath
a, b, c = map(float, input("a b c: ").split())
d = b**2 - 4*a*c
r1 = (-b + cmath.sqrt(d)) / (2*a)
r2 = (-b - cmath.sqrt(d)) / (2*a)
print("Raíces:", r1, r2)
