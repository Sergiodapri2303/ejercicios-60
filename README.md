# ejercicios-60

                    EJERCICIOS DE PENSAMIENTO ALGORÍTMICO                   (Del 1 al 60 - Estructura básica de Python)

# Ejercicio 1: Sumar dos números ingresados por el usuario.
print("--- Ejercicio 1: Suma de dos números ---")
try:
    # Pedimos al usuario el primer número. input() lee como texto.
    # int() convierte ese texto a un número entero.
    numero1 = int(input("Ingresa el primer número: "))
    numero2 = int(input("Ingresa el segundo número: "))

    # Realizamos la suma
    suma = numero1 + numero2

    # Mostramos el resultado. Usamos f-strings (f"...") para que el mensaje sea más claro.
    print(f"La suma de {numero1} y {numero2} es: {suma}")
except ValueError:
    # Capturamos errores si el usuario no ingresa un número
    print("¡Ups! Parece que no ingresaste un número entero válido. Inténtalo de nuevo.")
print("-" * 60) # Para separar los ejercicios visualmente

# Ejercicio 2: Convertir grados Celsius a Fahrenheit.
print("--- Ejercicio 2: Conversor de Celsius a Fahrenheit ---")
try:
    # Usamos float() por si la temperatura tiene decimales
    celsius = float(input("Ingresa la temperatura en grados Celsius: "))

    # La fórmula para convertir Celsius a Fahrenheit es (C * 9/5) + 32
    fahrenheit = (celsius * 9/5) + 32

    # Mostramos el resultado con un formato más amigable
    print(f"{celsius}°C equivalen a {fahrenheit}°F.")
except ValueError:
    print("¡Eso no parece una temperatura! Por favor, ingresa un número.")
print("-" * 60)

# Ejercicio 3: Determinar si un número es par o impar.
print("--- Ejercicio 3: Par o Impar ---")
try:
    numero = int(input("Ingresa un número entero para saber si es par o impar: "))

    # El operador módulo (%) nos da el residuo de una división.
    # Si un número dividido por 2 tiene un residuo de 0, es par.
    if numero % 2 == 0:
        print(f"El número {numero} es PAR.")
    else:
        print(f"El número {numero} es IMPAR.")
except ValueError:
    print("Por favor, ingresa un número entero válido.")
print("-" * 60)

# Ejercicio 4: Calcular el área de un círculo con un radio dado.
print("--- Ejercicio 4: Área de un Círculo ---")
# Necesitamos el valor de pi (π), que está en el módulo 'math' de Python.
import math
try:
    radio = float(input("Ingresa el radio del círculo: "))

    # La fórmula del área del círculo es pi * radio al cuadrado
    area = math.pi * (radio ** 2) # '**' es el operador de potencia (radio elevado a la 2)

    # Mostramos el resultado, limitando a 2 decimales con ":.2f"
    print(f"El área del círculo con radio {radio} es: {area:.2f}")
except ValueError:
    print("Debes ingresar un número para el radio.")
print("-" * 60)

# Ejercicio 5: Intercambiar los valores de dos variables.
print("--- Ejercicio 5: Intercambiar valores de variables ---")
# Aquí no pedimos al usuario, simplemente demostramos el intercambio con valores predefinidos.
var1 = 10
var2 = 5
print(f"Valores iniciales: var1 = {var1}, var2 = {var2}")

# En Python, ¡es súper fácil! Puedes hacerlo en una sola línea.
# Es como decir: "lo que antes era 'var1' ahora es el valor de 'var2',
# y lo que antes era 'var2' ahora es el valor de 'var1'."
var1, var2 = var2, var1
print(f"Valores después del intercambio: var1 = {var1}, var2 = {var2}")
print("-" * 60)

# Ejercicio 6: Determinar si un número es positivo, negativo o cero.
print("--- Ejercicio 6: Positivo, Negativo o Cero ---")
try:
    numero = float(input("Ingresa un número: "))

    if numero > 0:
        print(f"El número {numero} es POSITIVO.")
    elif numero < 0: # 'elif' es la abreviatura de "else if", para otra condición
        print(f"El número {numero} es NEGATIVO.")
    else: # Si no es mayor que 0 y no es menor que 0, entonces debe ser 0
        print(f"El número {numero} es CERO.")
except ValueError:
    print("Por favor, ingresa un número válido.")
print("-" * 60)

# Ejercicio 7: Encontrar el mayor de tres números ingresados.
print("--- Ejercicio 7: Mayor de tres números ---")
try:
    num1 = float(input("Ingresa el primer número: "))
    num2 = float(input("Ingresa el segundo número: "))
    num3 = float(input("Ingresa el tercer número: "))

    # Podemos usar una serie de 'if/elif/else' para comparar
    if num1 >= num2 and num1 >= num3: # Si num1 es mayor o igual que num2 Y mayor o igual que num3
        mayor = num1
    elif num2 >= num1 and num2 >= num3: # Si num2 es mayor o igual que num1 Y mayor o igual que num3
        mayor = num2
    else: # Si no fue num1 ni num2 el mayor, entonces el mayor debe ser num3
        mayor = num3

    print(f"El mayor de los tres números es: {mayor}")
    # ¡Un truco! Python tiene una función max() que lo hace más corto:
    # mayor_con_max = max(num1, num2, num3)
    # print(f"El mayor (usando max()) es: {mayor_con_max}")
except ValueError:
    print("Asegúrate de ingresar solo números.")
print("-" * 60)

# Ejercicio 8: Mostrar la tabla de multiplicar de un número.
print("--- Ejercicio 8: Tabla de Multiplicar ---")
try:
    numero_tabla = int(input("Ingresa el número del cual quieres la tabla de multiplicar: "))

    print(f"Tabla de multiplicar del {numero_tabla}:")
    # Usamos un bucle 'for' para repetir 10 veces (del 1 al 10)
    # range(1, 11) genera números enteros desde 1 hasta 10 (el 11 es exclusivo)
    for i in range(1, 11):
        resultado = numero_tabla * i
        print(f"{numero_tabla} x {i} = {resultado}")
except ValueError:
    print("Por favor, ingresa un número entero.")
print("-" * 60)

# Ejercicio 9: Calcular el factorial de un número.
print("--- Ejercicio 9: Factorial de un número ---")
try:
    numero_factorial = int(input("Ingresa un número entero no negativo para calcular su factorial: "))

    if numero_factorial < 0:
        print("El factorial no está definido para números negativos.")
    elif numero_factorial == 0:
        print("El factorial de 0 es 1.")
    else:
        factorial = 1 # Empezamos con 1 porque cualquier número multiplicado por 1 es el mismo
        # Multiplicamos 'factorial' por cada número desde 1 hasta 'numero_factorial'
        for i in range(1, numero_factorial + 1):
            factorial *= i # Esto es una forma corta de decir: factorial = factorial * i
        print(f"El factorial de {numero_factorial} es: {factorial}")
except ValueError:
    print("Por favor, ingresa un número entero válido.")
print("-" * 60)

# Ejercicio 10: Invertir un número entero.
print("--- Ejercicio 10: Invertir un número entero ---")
try:
    numero_original = int(input("Ingresa un número entero para invertirlo: "))
    # Usamos abs() (valor absoluto) para trabajar sin preocuparnos por el signo negativo inicialmente
    numero_temporal = abs(numero_original)
    numero_invertido = 0

    # Usamos un bucle 'while' que se ejecuta mientras el número temporal sea mayor que 0
    while numero_temporal > 0:
        digito = numero_temporal % 10 # Obtenemos el último dígito (ej: 123 % 10 = 3)
        numero_invertido = numero_invertido * 10 + digito # Agregamos el dígito al número invertido (ej: 0*10+3=3, luego 3*10+2=32)
        numero_temporal //= 10 # Eliminamos el último dígito (división entera, ej: 123 // 10 = 12)

    # Si el número original era negativo, el invertido también debe serlo
    if numero_original < 0:
        numero_invertido *= -1

    print(f"El número invertido de {numero_original} es: {numero_invertido}")
except ValueError:
    print("Por favor, ingresa un número entero.")
print("-" * 60)

# --- Bloque 2: Operaciones con Dígitos y Propiedades de Números ---

# Ejercicio 11: Contar los dígitos de un número.
print("--- Ejercicio 11: Contar dígitos ---")
try:
    numero = int(input("Ingresa un número entero para contar sus dígitos: "))
    # Convertimos el número a string (texto) y luego usamos len() para saber su longitud.
    # Usamos abs() para que funcione bien con números negativos (ej: -123 tiene 3 dígitos).
    num_str = str(abs(numero))
    cantidad_digitos = len(num_str)
    print(f"El número {numero} tiene {cantidad_digitos} dígitos.")
except ValueError:
    print("Por favor, ingresa un número entero válido.")
print("-" * 60)

# Ejercicio 12: Sumar los dígitos de un número.
print("--- Ejercicio 12: Sumar dígitos ---")
try:
    numero_original = int(input("Ingresa un número entero para sumar sus dígitos: "))
    numero_temporal = abs(numero_original) # Trabajamos con el valor absoluto para la suma
    suma_digitos = 0

    while numero_temporal > 0:
        digito = numero_temporal % 10 # Obtenemos el último dígito
        suma_digitos += digito # Sumamos el dígito al total
        numero_temporal //= 10 # Eliminamos el último dígito
    print(f"La suma de los dígitos de {numero_original} es: {suma_digitos}")
except ValueError:
    print("Por favor, ingresa un número entero válido.")
print("-" * 60)

# Ejercicio 13: Verificar si un número es primo.
print("--- Ejercicio 13: Verificar si es Primo ---")
try:
    numero = int(input("Ingresa un número entero para verificar si es primo: "))

    if numero <= 1:
        es_primo = False # Números menores o iguales a 1 no son primos
    else:
        es_primo = True # Asumimos que es primo hasta que encontremos un divisor
        # Solo necesitamos verificar divisores desde 2 hasta la raíz cuadrada del número.
        # Si un número tiene un divisor, tendrá uno menor o igual a su raíz cuadrada.
        import math # Aseguramos que math esté importado para sqrt()
        for i in range(2, int(math.sqrt(numero)) + 1):
            if numero % i == 0:
                es_primo = False # Si encontramos un divisor, no es primo
                break # Salimos del bucle, ya no necesitamos seguir revisando
    if es_primo:
        print(f"El número {numero} SÍ es primo.")
    else:
        print(f"El número {numero} NO es primo.")
except ValueError:
    print("Por favor, ingresa un número entero válido.")
print("-" * 60)

# Ejercicio 14: Determinar si un año es bisiesto.
print("--- Ejercicio 14: Año Bisiesto ---")
try:
    año = int(input("Ingresa un año para determinar si es bisiesto: "))

    # Reglas para un año bisiesto:
    # 1. Es divisible por 4, EXCEPTO...
    # 2. Si es divisible por 100, entonces NO es bisiesto, EXCEPTO...
    # 3. Si es divisible por 400, entonces SÍ es bisiesto.
    if (año % 400 == 0) or (año % 4 == 0 and año % 100 != 0):
        print(f"El año {año} SÍ es bisiesto.")
    else:
        print(f"El año {año} NO es bisiesto.")
except ValueError:
    print("Por favor, ingresa un año válido (un número entero).")
print("-" * 60)

# Ejercicio 15: Calcular la suma de los primeros N números naturales.
print("--- Ejercicio 15: Suma de N números naturales ---")
try:
    n = int(input("Ingresa un número N para sumar los primeros N números naturales: "))

    if n < 0:
        print("N debe ser un número entero positivo para esta suma.")
    else:
        # Una forma es usando un bucle 'for':
        # suma_naturales_bucle = 0
        # for i in range(1, n + 1):
        #     suma_naturales_bucle += i
        # print(f"La suma de los primeros {n} números naturales es (bucle): {suma_naturales_bucle}")

        # Otra forma (más eficiente para números grandes) es usando la fórmula de Gauss: n * (n + 1) / 2
        # Usamos // para división entera para asegurarnos de que el resultado sea entero.
        suma_naturales_formula = n * (n + 1) // 2
        print(f"La suma de los primeros {n} números naturales es: {suma_naturales_formula}")
except ValueError:
    print("Por favor, ingresa un número entero válido para N.")
print("-" * 60)

# Ejercicio 16: Encontrar el mínimo y máximo en una lista de números.
print("--- Ejercicio 16: Mínimo y Máximo en una lista ---")
print("Ingresa números separados por espacios (ej: 10 5 23 7.5 1):")
entrada = input("Números: ")
numeros_str = entrada.split() # Separa la cadena por espacios en blanco en una lista de textos
lista_numeros = []
for num_str in numeros_str:
    try:
        lista_numeros.append(float(num_str)) # Intenta convertir cada texto a número (float para decimales)
    except ValueError:
        print(f"'{num_str}' no parece un número válido y será ignorado.")

if not lista_numeros: # Si la lista termina vacía (no se ingresaron números válidos)
    print("No se ingresaron números válidos para analizar.")
else:
    # Python tiene funciones integradas muy prácticas para esto: min() y max()
    minimo = min(lista_numeros)
    maximo = max(lista_numeros)
    print(f"La lista de números es: {lista_numeros}")
    print(f"El número más pequeño es: {minimo}")
    print(f"El número más grande es: {maximo}")
print("-" * 60)

# Ejercicio 17: Calcular el promedio de una lista de números.
print("--- Ejercicio 17: Promedio de una lista ---")
print("Ingresa números separados por espacios (ej: 15 20 25 30):")
entrada = input("Números: ")
numeros_str = entrada.split()
lista_numeros = []
for num_str in numeros_str:
    try:
        lista_numeros.append(float(num_str))
    except ValueError:
        print(f"'{num_str}' no es un número válido y será ignorado.")

if not lista_numeros:
    print("No se ingresaron números válidos para calcular el promedio.")
else:
    suma_total = sum(lista_numeros) # sum() es una función de Python que suma todos los elementos de una lista
    cantidad_numeros = len(lista_numeros) # len() nos da la cantidad de elementos en la lista
    promedio = suma_total / cantidad_numeros
    print(f"La lista de números es: {lista_numeros}")
    print(f"El promedio de los números es: {promedio:.2f}") # Formateamos a 2 decimales
print("-" * 60)

# Ejercicio 18: Contar cuántos números pares e impares hay en una lista.
print("--- Ejercicio 18: Contar Pares e Impares en una lista ---")
print("Ingresa números enteros separados por espacios (ej: 1 2 3 4 5 6 7):")
entrada = input("Números: ")
numeros_str = entrada.split()
lista_numeros = []
for num_str in numeros_str:
    try:
        lista_numeros.append(int(num_str)) # Convertimos a int porque buscamos par/impar
    except ValueError:
        print(f"'{num_str}' no es un número entero válido y será ignorado.")

pares = 0
impares = 0

if not lista_numeros:
    print("No se ingresaron números válidos para contar.")
else:
    for numero in lista_numeros: # Recorremos cada número en la lista
        if numero % 2 == 0:
            pares += 1 # Si es par, incrementamos el contador de pares
        else:
            impares += 1 # Si es impar, incrementamos el contador de impares
    print(f"En la lista {lista_numeros}:")
    print(f"Hay {pares} números pares.")
    print(f"Hay {impares} números impares.")
print("-" * 60)

# Ejercicio 19: Ordenar una lista de números de menor a mayor.
print("--- Ejercicio 19: Ordenar una lista ---")
print("Ingresa números separados por espacios (ej: 5 2 8 1 9 3):")
entrada = input("Números: ")
numeros_str = entrada.split()
lista_numeros = []
for num_str in numeros_str:
    try:
        lista_numeros.append(float(num_str))
    except ValueError:
        print(f"'{num_str}' no es un número válido y será ignorado.")

if not lista_numeros:
    print("No se ingresaron números para ordenar.")
else:
    print(f"Lista original: {lista_numeros}")
    # Python tiene una función muy sencilla para ordenar listas: el método .sort()
    # Este método modifica la lista "en su lugar" (es decir, cambia la lista original)
    lista_numeros.sort()
    print(f"Lista ordenada (menor a mayor): {lista_numeros}")

    # Si quisieras una *nueva* lista ordenada sin modificar la original, usarías sorted():
    # lista_ordenada_nueva = sorted(otra_lista_para_ordenar)
print("-" * 60)

# Ejercicio 20: Verificar si una palabra es un palíndromo.
print("--- Ejercicio 20: Palíndromo ---")
palabra = input("Ingresa una palabra para saber si es un palíndromo: ").lower() # Convertimos a minúsculas para ignorar mayúsculas/minúsculas

# Un palíndromo se lee igual de izquierda a derecha que de derecha a izquierda.
# Podemos invertir la palabra y compararla con la original.
# La técnica [::-1] es un truco de slicing en Python para invertir cadenas (o listas).
palabra_invertida = palabra[::-1]

if palabra == palabra_invertida:
    print(f"La palabra '{palabra}' SÍ es un palíndromo.")
else:
    print(f"La palabra '{palabra}' NO es un palíndromo.")
print("-" * 60)

# --- Bloque 3: Conversiones y Funciones Matemáticas Especiales ---

# Ejercicio 21: Convertir un número decimal a binario.
print("--- Ejercicio 21: Decimal a Binario ---")
try:
    decimal = int(input("Ingresa un número decimal entero para convertir a binario: "))

    if decimal < 0:
        print("Este programa convierte números enteros no negativos a binario.")
    elif decimal == 0:
        print("El número 0 en binario es: 0")
    else:
        binario = "" # Empezamos con una cadena vacía para construir el binario
        temp_decimal = decimal
        while temp_decimal > 0:
            # El residuo de la división por 2 es el bit (0 o 1)
            binario = str(temp_decimal % 2) + binario # Agregamos el bit al principio de la cadena
            temp_decimal //= 2 # Dividimos el número entre 2 (división entera)
        print(f"El número {decimal} en binario es: {binario}")

    # ¡Sabías que Python tiene una función bin() para esto?
    # print(f"Con la función bin() de Python (incluye '0b'): {bin(decimal)}")
except ValueError:
    print("Por favor, ingresa un número entero válido.")
print("-" * 60)

# Ejercicio 22: Generar un número aleatorio entre 1 y 100.
print("--- Ejercicio 22: Generar Número Aleatorio ---")
# Necesitamos el módulo 'random' para generar números aleatorios.
import random

# randint(a, b) genera un número entero aleatorio entre 'a' y 'b' (ambos incluidos).
numero_aleatorio = random.randint(1, 100)
print(f"Se ha generado un número aleatorio entre 1 y 100: {numero_aleatorio}")
print("-" * 60)

# Ejercicio 23: Calcular la suma de los números pares hasta N.
print("--- Ejercicio 23: Suma de Pares hasta N ---")
try:
    n_limite = int(input("Ingresa un número N (límite) para sumar todos los pares hasta N: "))
    suma_pares = 0

    if n_limite < 0:
        print("N debe ser un número entero positivo para esta suma.")
    else:
        # range(inicio, fin_exclusivo, paso)
        # Empezamos en 2, vamos hasta N (inclusive, por eso n_limite + 1), y de 2 en 2.
        for i in range(2, n_limite + 1, 2):
            suma_pares += i
        print(f"La suma de los números pares hasta {n_limite} es: {suma_pares}")
except ValueError:
    print("Por favor, ingresa un número entero válido para N.")
print("-" * 60)

# Ejercicio 24: Hallar el MCD (Máximo Común Divisor) de dos números.
print("--- Ejercicio 24: MCD de dos números ---")
# Usaremos el famoso algoritmo de Euclides, que es muy eficiente.
def calcular_mcd(a, b):
    # El algoritmo de Euclides dice que MCD(a, b) = MCD(b, a % b)
    # y que MCD(a, 0) = a.
    # El bucle continúa mientras 'b' no sea 0.
    while b != 0:
        # Una forma compacta de intercambiar valores en Python:
        a, b = b, a % b # 'a' toma el valor actual de 'b', y 'b' toma el residuo de 'a' dividido por 'b'
    return a

try:
    num1 = int(input("Ingresa el primer número entero: "))
    num2 = int(input("Ingresa el segundo número entero: "))

    mcd_resultado = calcular_mcd(num1, num2)
    print(f"El Máximo Común Divisor (MCD) de {num1} y {num2} es: {mcd_resultado}")
except ValueError:
    print("Por favor, ingresa números enteros válidos.")
print("-" * 60)

# Ejercicio 25: Hallar el MCM (Mínimo Común Múltiplo) de dos números.
print("--- Ejercicio 25: MCM de dos números ---")
# Una propiedad matemática útil es: MCM(a, b) * MCD(a, b) = |a * b|
# Así que podemos calcular el MCM usando el MCD que ya implementamos: MCM(a, b) = (|a * b|) / MCD(a, b)
# Necesitamos la función calcular_mcd que definimos justo antes.

def calcular_mcm(a, b):
    if a == 0 or b == 0:
        return 0 # El MCM de 0 con cualquier número es 0
    # Usamos abs() para el valor absoluto en caso de que los números sean negativos
    # y '//' para división entera para que el resultado sea entero.
    return abs(a * b) // calcular_mcd(a, b)

try:
    num1 = int(input("Ingresa el primer número entero: "))
    num2 = int(input("Ingresa el segundo número entero: "))

    mcm_resultado = calcular_mcm(num1, num2)
    print(f"El Mínimo Común Múltiplo (MCM) de {num1} y {num2} es: {mcm_resultado}")
except ValueError:
    print("Por favor, ingresa números enteros válidos.")
print("-" * 60)

# Ejercicio 26: Simular el lanzamiento de un dado.
print("--- Ejercicio 26: Lanzamiento de Dado ---")
# Volvemos a usar el módulo random.
import random

# Un dado estándar tiene 6 caras, numeradas del 1 al 6.
resultado_dado = random.randint(1, 6) # Genera un entero aleatorio entre 1 y 6.
print(f"¡Has lanzado el dado! El resultado es: {resultado_dado}")
print("-" * 60)

# Ejercicio 27: Contar la frecuencia de cada letra en una cadena.
print("--- Ejercicio 27: Frecuencia de letras ---")
cadena = input("Ingresa una frase o palabra para contar sus letras: ").lower() # Convertimos a minúsculas para unificar

frecuencia_letras = {} # Creamos un diccionario vacío para guardar las frecuencias.
                       # Las claves serán las letras y los valores serán sus conteos.

for caracter in cadena:
    # Solo contamos letras del abecedario (ignoramos espacios, números, símbolos, etc.)
    if 'a' <= caracter <= 'z': # Verifica si el caracter es una letra minúscula
        # Si la letra ya está en el diccionario, incrementamos su contador.
        if caracter in frecuencia_letras:
            frecuencia_letras[caracter] += 1
        else:
            # Si la letra no está, la agregamos al diccionario con un contador de 1.
            frecuencia_letras[caracter] = 1

print("Frecuencia de letras:")
# Iteramos sobre las claves (letras) del diccionario, pero las ordenamos primero para una mejor visualización.
for letra in sorted(frecuencia_letras.keys()):
    print(f"'{letra}': {frecuencia_letras[letra]}")
print("-" * 60)

# Ejercicio 28: Encontrar el segundo número más grande en una lista.
print("--- Ejercicio 28: Segundo número más grande ---")
print("Ingresa números separados por espacios (ej: 10 5 23 7 18 23):")
entrada = input("Números: ")
numeros_str = entrada.split()
lista_numeros = []
for num_str in numeros_str:
    try:
        lista_numeros.append(float(num_str))
    except ValueError:
        print(f"'{num_str}' no es un número válido y será ignorado.")

if len(lista_numeros) < 2:
    print("Necesitas al menos dos números únicos en la lista para encontrar el segundo más grande.")
else:
    # Una buena estrategia es:
    # 1. Eliminar duplicados (para que si el número más grande se repite, no lo cuente como segundo).
    # 2. Ordenar la lista.
    # 3. El segundo elemento más grande será el penúltimo.
    lista_sin_duplicados = sorted(list(set(lista_numeros))) # set() elimina duplicados, list() lo convierte de nuevo a lista, sorted() la ordena
    if len(lista_sin_duplicados) < 2:
        print("No hay suficientes números únicos en la lista (o todos son iguales).")
    else:
        # El penúltimo elemento de una lista se accede con el índice -2
        segundo_mas_grande = lista_sin_duplicados[-2]
        print(f"La lista (sin duplicados y ordenada) es: {lista_sin_duplicados}")
        print(f"El segundo número más grande es: {segundo_mas_grande}")
print("-" * 60)

# Ejercicio 29: Rotar una lista a la derecha una posición.
print("--- Ejercicio 29: Rotar lista a la derecha ---")
print("Ingresa elementos separados por espacios (ej: a b c d e):")
entrada = input("Elementos de la lista: ")
lista_original = entrada.split() # Convierte la entrada en una lista de cadenas

if not lista_original: # Si la lista está vacía
    print("La lista está vacía. No se puede rotar.")
else:
    print(f"Lista original: {lista_original}")
    # Para rotar a la derecha:
    # 1. Tomamos el último elemento.
    # 2. Creamos una nueva lista con el último elemento al principio, seguido del resto de la lista.
    ultimo_elemento = lista_original[-1] # Obtiene el último elemento
    # lista_original[:-1] crea una nueva lista con todos los elementos EXCEPTO el último
    lista_rotada = [ultimo_elemento] + lista_original[:-1]
    print(f"Lista rotada a la derecha: {lista_rotada}")

    # Otra forma, "manual" para entender el proceso sin slicing avanzado:
    # if lista_original: # Asegurarse de que no esté vacía
    #     temp = lista_original[-1] # Guardar el último elemento
    #     # Recorrer la lista de atrás hacia adelante (desde el penúltimo hasta el primero)
    #     for i in range(len(lista_original) - 1, 0, -1):
    #         lista_original[i] = lista_original[i-1] # Mover cada elemento una posición a la derecha
    #     lista_original[0] = temp # Poner el elemento que guardamos al principio
    #     print(f"Lista rotada (manual): {lista_original}")
print("-" * 60)

# Ejercicio 30: Implementar una calculadora simple con +, −, *, /.
print("--- Ejercicio 30: Calculadora Simple ---")
try:
    num1 = float(input("Ingresa el primer número: "))
    operador = input("Ingresa el operador (+, -, *, /): ")
    num2 = float(input("Ingresa el segundo número: "))

    resultado = None # Inicializamos el resultado como nulo
    mensaje_error = None # Para guardar mensajes de error específicos

    if operador == '+':
        resultado = num1 + num2
    elif operador == '-':
        resultado = num1 - num2
    elif operador == '*':
        resultado = num1 * num2
    elif operador == '/':
        if num2 != 0: # ¡Importante! No se puede dividir por cero en matemáticas.
            resultado = num1 / num2
        else:
            mensaje_error = "Error: No se puede dividir por cero."
    else:
        mensaje_error = "Operador no válido. Por favor, usa +, -, * o /."

    if mensaje_error:
        print(mensaje_error)
    elif resultado is not None:
        print(f"El resultado de {num1} {operador} {num2} es: {resultado}")
except ValueError:
    print("Asegúrate de ingresar números válidos para las operaciones.")
print("-" * 60)

# --- Bloque 4: Operaciones con Listas y Cadenas Avanzadas ---

# Ejercicio 31: Contar cuántas veces aparece un número en una lista.
print("--- Ejercicio 31: Contar ocurrencias en lista ---")
print("Ingresa números separados por espacios (ej: 1 2 2 3 4 2 5):")
entrada = input("Lista de números: ")
numeros_str = entrada.split()
lista_numeros = []
for num_str in numeros_str:
    try:
        lista_numeros.append(float(num_str))
    except ValueError:
        print(f"'{num_str}' no es un número válido y será ignorado.")

if not lista_numeros:
    print("La lista está vacía. No hay números para contar.")
else:
    try:
        numero_buscar = float(input("¿Qué número quieres contar en la lista? "))
        # ¡Python nos facilita la vida! El método .count() de las listas es perfecto para esto.
        cantidad = lista_numeros.count(numero_buscar)
        print(f"El número {numero_buscar} aparece {cantidad} veces en la lista.")
    except ValueError:
        print("Por favor, ingresa un número válido para buscar.")
print("-" * 60)

# Ejercicio 32: Concatenar dos listas sin usar el operador '+'.
print("--- Ejercicio 32: Concatenar listas sin '+' ---")
print("Ingresa elementos para la primera lista (separados por espacios):")
lista1 = input("Lista 1: ").split() # Convertimos la entrada a una lista de cadenas
print("Ingresa elementos para la segunda lista (separados por espacios):")
lista2 = input("Lista 2: ").split()

lista_concatenada = []
# Recorremos la primera lista y añadimos sus elementos uno por uno a la nueva lista
for elemento in lista1:
    lista_concatenada.append(elemento)
# Luego, recorremos la segunda lista y añadimos sus elementos a la misma nueva lista
for elemento in lista2:
    lista_concatenada.append(elemento)

print(f"Lista 1: {lista1}")
print(f"Lista 2: {lista2}")
print(f"Listas concatenadas (sin usar '+'): {lista_concatenada}")

# Para tu información, también podrías usar el método .extend() de las listas:
# lista_concatenada_extend = []
# lista_concatenada_extend.extend(lista1)
# lista_concatenada_extend.extend(lista2)
# print(f"Listas concatenadas (con extend): {lista_concatenada_extend}")
print("-" * 60)

# Ejercicio 33: Encontrar el número que más se repite en una lista.
print("--- Ejercicio 33: Número que más se repite ---")
print("Ingresa números separados por espacios (ej: 1 2 2 3 1 4 2):")
entrada = input("Lista de números: ")
numeros_str = entrada.split()
lista_numeros = []
for num_str in numeros_str:
    try:
        lista_numeros.append(float(num_str))
    except ValueError:
        print(f"'{num_str}' no es un número válido y será ignorado.")

if not lista_numeros:
    print("La lista está vacía.")
else:
    # Usaremos un diccionario para guardar el conteo (frecuencia) de cada número.
    # Las claves serán los números y los valores serán cuántas veces aparecen.
    conteo_numeros = {}
    for numero in lista_numeros:
        # .get(clave, valor_por_defecto) obtiene el valor de una clave,
        # si no existe, devuelve el valor por defecto (en este caso, 0).
        conteo_numeros[numero] = conteo_numeros.get(numero, 0) + 1

    numero_mas_repetido = None
    max_frecuencia = -1 # Empezamos con una frecuencia imposiblemente baja

    # Recorremos el diccionario para encontrar cuál número tiene la mayor frecuencia
    for numero, frecuencia in conteo_numeros.items(): # .items() nos da pares (clave, valor)
        if frecuencia > max_frecuencia:
            max_frecuencia = frecuencia
            numero_mas_repetido = numero

    print(f"La lista es: {lista_numeros}")
    print(f"El número que más se repite es: {numero_mas_repetido} (aparece {max_frecuencia} veces).")
print("-" * 60)

# Ejercicio 34: Comprobar si dos palabras son anagramas.
print("--- Ejercicio 34: Anagramas ---")
# .lower() para convertir a minúsculas, .replace(" ", "") para quitar espacios.
palabra1 = input("Ingresa la primera palabra: ").lower().replace(" ", "")
palabra2 = input("Ingresa la segunda palabra: ").lower().replace(" ", "")

# Dos palabras son anagramas si tienen las mismas letras en la misma cantidad,
# solo que en diferente orden. Si las ordenamos alfabéticamente, deberían ser iguales.
if len(palabra1) != len(palabra2): # Si tienen diferente longitud, no pueden ser anagramas.
    print("Las palabras no pueden ser anagramas si tienen diferente longitud.")
else:
    # sorted() convierte la cadena en una lista de caracteres y la ordena.
    # Luego, comparamos las listas ordenadas.
    if sorted(palabra1) == sorted(palabra2):
        print(f"'{palabra1}' y '{palabra2}' SÍ son anagramas.")
    else:
        print(f"'{palabra1}' y '{palabra2}' NO son anagramas.")
print("-" * 60)

# Ejercicio 35: Encontrar el índice de la primera ocurrencia de un elemento en una lista.
print("--- Ejercicio 35: Índice de primera ocurrencia ---")
print("Ingresa elementos de la lista separados por espacios (ej: manzana banana naranja manzana):")
entrada = input("Elementos de la lista: ")
lista_elementos = entrada.split() # Crea una lista de cadenas

if not lista_elementos:
    print("La lista está vacía.")
else:
    elemento_buscar = input("¿Qué elemento quieres buscar en la lista? ")

    # El método .index() de las listas encuentra la primera ocurrencia de un elemento.
    # Si el elemento no se encuentra, .index() lanza un error (ValueError).
    try:
        indice = lista_elementos.index(elemento_buscar)
        print(f"El elemento '{elemento_buscar}' se encuentra por primera vez en el índice: {indice}")
    except ValueError:
        print(f"El elemento '{elemento_buscar}' no se encontró en la lista.")
print("-" * 60)

# Ejercicio 36: Imprimir un patrón de pirámide con asteriscos (*).
print("--- Ejercicio 36: Patrón de Pirámide ---")
try:
    altura = int(input("Ingresa la altura de la pirámide (número entero positivo): "))

    if altura <= 0:
        print("La altura debe ser un número positivo.")
    else:
        for i in range(1, altura + 1): # 'i' representa la fila actual, desde 1 hasta la 'altura'
            # Para centrar la pirámide, imprimimos espacios en blanco antes de los asteriscos.
            # La cantidad de espacios disminuye con cada fila.
            espacios = " " * (altura - i)
            # La cantidad de asteriscos en cada fila es impar: 1, 3, 5, ... (2*i - 1)
            asteriscos = "*" * (2 * i - 1)
            print(espacios + asteriscos)
except ValueError:
    print("Por favor, ingresa un número entero para la altura.")
print("-" * 60)

# Ejercicio 37: Verificar si una cadena es un pangrama (contiene todas las letras del abecedario).
print("--- Ejercicio 37: Verificar Pangrama ---")
cadena = input("Ingresa una frase para verificar si es un pangrama: ").lower() # Convertimos a minúsculas

# Un pangrama es una frase que contiene al menos una vez cada letra del abecedario.
# Usaremos conjuntos (sets) porque son ideales para comprobar si un elemento está presente y para operaciones de diferencia.
alfabeto = set("abcdefghijklmnopqrstuvwxyz") # Creamos un conjunto con todas las letras del alfabeto
letras_en_cadena = set() # Creamos un conjunto vacío para guardar las letras únicas de la frase

for caracter in cadena:
    if 'a' <= caracter <= 'z': # Si el caracter es una letra del alfabeto
        letras_en_cadena.add(caracter) # Agregamos la letra al conjunto (los conjuntos solo guardan elementos únicos)

# Si el conjunto de letras de la cadena es igual al conjunto del alfabeto, es un pangrama.
if letras_en_cadena == alfabeto:
    print(f"La frase SÍ es un pangrama: '{cadena}'")
else:
    print(f"La frase NO es un pangrama: '{cadena}'")
    # Opcional: para saber qué letras faltan
    # letras_faltantes = alfabeto - letras_en_cadena # Resta de conjuntos
    # print(f"Le faltan las letras: {', '.join(sorted(list(letras_faltantes)))}")
print("-" * 60)

# Ejercicio 38: Implementar el cifrado César.
print("--- Ejercicio 38: Cifrado César ---")
mensaje = input("Ingresa el mensaje a cifrar: ").lower() # Convertimos a minúsculas para simplificar
try:
    desplazamiento = int(input("Ingresa el número de desplazamiento (ej: 3 para mover 3 posiciones): "))
except ValueError:
    print("El desplazamiento debe ser un número entero. Usando 0 por defecto.")
    desplazamiento = 0 # Valor por defecto si hay un error en la entrada

mensaje_cifrado = ""
for caracter in mensaje:
    if 'a' <= caracter <= 'z': # Si el caracter es una letra
        # ord(caracter) nos da el valor ASCII/Unicode de la letra (ej: ord('a') es 97)
        posicion = ord(caracter) - ord('a') # Obtenemos la posición de la letra en el alfabeto (a=0, b=1, ...)
        # Aplicamos el desplazamiento. El '% 26' asegura que "dé la vuelta" al alfabeto si se pasa del 'z'.
        nueva_posicion = (posicion + desplazamiento) % 26
        # chr(numero) nos da el caracter correspondiente al valor ASCII/Unicode
        nuevo_caracter = chr(ord('a') + nueva_posicion)
        mensaje_cifrado += nuevo_caracter
    else:
        # Si no es una letra (espacios, números, símbolos), lo dejamos tal cual
        mensaje_cifrado += caracter

print(f"Mensaje original: {mensaje}")
print(f"Mensaje cifrado: {mensaje_cifrado}")
print("-" * 60)

# Ejercicio 39: Resolver el problema de las torres de Hanói.
print("--- Ejercicio 39: Torres de Hanói ---")
# Este problema se resuelve de forma elegante usando la recursión (una función que se llama a sí misma).
# Para principiantes, lo importante es entender el concepto y la lógica de los pasos.
def torres_hanoi(n, origen, destino, auxiliar):
    # n: número de discos
    # origen: la torre de donde movemos el disco
    # destino: la torre a donde queremos llevar el disco
    # auxiliar: la torre temporal que usamos para mover los discos

    if n == 1: # Caso base: Si solo hay un disco, simplemente lo movemos.
        print(f"Mover disco 1 de {origen} a {destino}")
        return

    # Paso 1: Mover n-1 discos de la torre de origen a la torre auxiliar,
    # usando la torre de destino como temporal.
    torres_hanoi(n - 1, origen, auxiliar, destino)

    # Paso 2: Mover el disco más grande (el disco 'n') de la torre de origen a la torre de destino.
    print(f"Mover disco {n} de {origen} a {destino}")

    # Paso 3: Mover los n-1 discos que estaban en la torre auxiliar a la torre de destino,
    # usando la torre de origen como temporal.
    torres_hanoi(n - 1, auxiliar, destino, origen)

try:
    num_discos = int(input("Ingresa el número de discos para las Torres de Hanói: "))
    if num_discos <= 0:
        print("El número de discos debe ser positivo.")
    else:
        print("\nPasos para resolver las Torres de Hanói:")
        # Por convención, las torres se suelen llamar A, B y C.
        torres_hanoi(num_discos, 'A', 'C', 'B')
except ValueError:
    print("Por favor, ingresa un número entero para los discos.")
print("-" * 60)

# Ejercicio 40: Crear una función que invierta una lista sin usar el método .reverse().
print("--- Ejercicio 40: Invertir lista sin .reverse() ---")
print("Ingresa elementos de la lista separados por espacios (ej: hola 123 mundo python):")
entrada = input("Lista de elementos: ")
lista_original = entrada.split()

def invertir_lista_manual(lista):
    lista_invertida = []
    # Recorremos la lista original de atrás hacia adelante.
    # range(inicio, fin_exclusivo, paso)
    # len(lista) - 1 es el índice del último elemento.
    # -1 es el fin exclusivo (para incluir el índice 0).
    # -1 como paso significa ir hacia atrás.
    for i in range(len(lista) - 1, -1, -1):
        lista_invertida.append(lista[i]) # Añadimos el elemento a la nueva lista
    return lista_invertida

print(f"Lista original: {lista_original}")
lista_invertida = invertir_lista_manual(lista_original)
print(f"Lista invertida (manualmente): {lista_invertida}")

# Recordatorio: También se puede invertir usando slicing de forma muy concisa:
# lista_invertida_con_slicing = lista_original[::-1]
# print(f"Lista invertida (con slicing): {lista_invertida_con_slicing}")
print("-" * 60)

# --- Bloque 5: Generadores, Simulación y Manipulación de Cadenas ---

# Ejercicio 41: Implementar un generador de contraseñas.
print("--- Ejercicio 41: Generador de Contraseñas ---")
import random
import string # Este módulo nos proporciona cadenas con tipos de caracteres (letras, dígitos, etc.)

def generar_contraseña(longitud, incluir_mayus=True, incluir_minus=True, incluir_digitos=True, incluir_simbolos=True):
    # Creamos una cadena vacía que contendrá todos los caracteres posibles para la contraseña.
    caracteres_disponibles = ""
    if incluir_mayus:
        caracteres_disponibles += string.ascii_uppercase # Añade 'ABC...XYZ'
    if incluir_minus:
        caracteres_disponibles += string.ascii_lowercase # Añade 'abc...xyz'
    if incluir_digitos:
        caracteres_disponibles += string.digits # Añade '0123...9'
    if incluir_simbolos:
        caracteres_disponibles += string.punctuation # Añade '!@#$%^&*...'

    if not caracteres_disponibles: # Si el usuario no seleccionó ningún tipo de caracter válido
        return "Error: Debes seleccionar al menos un tipo de caracter para generar la contraseña."

    contraseña_generada = ""
    # random.choice(secuencia) elige un elemento aleatorio de la secuencia.
    # ''.join(...) une todos los caracteres elegidos en una sola cadena.
    for _ in range(longitud): # El '_' se usa cuando la variable del bucle no se va a usar dentro del bucle
        contraseña_generada += random.choice(caracteres_disponibles)
    return contraseña_generada

try:
    longitud_contra = int(input("Longitud de la contraseña deseada: "))
    if longitud_contra <= 0:
        print("La longitud debe ser un número entero positivo.")
    else:
        # Por simplicidad, generamos con todos los tipos de caracteres por defecto.
        # Podrías añadir preguntas al usuario si quiere incluir mayúsculas, etc.
        # Por ejemplo:
        # incl_mayus = input("¿Incluir mayúsculas? (s/n): ").lower() == 's'
        # contra = generar_contraseña(longitud_contra, incluir_mayus=incl_mayus, ...)
        contra = generar_contraseña(longitud_contra)
        print(f"Contraseña generada: {contra}")
except ValueError:
    print("Por favor, ingresa un número entero para la longitud.")
print("-" * 60)

# Ejercicio 42: Comprimir una cadena eliminando caracteres repetidos consecutivos.
print("--- Ejercicio 42: Comprimir cadena (repetidos consecutivos) ---")
cadena_original = input("Ingresa una cadena (ej: aaabbcdddd): ")
cadena_comprimida = ""

if not cadena_original:
    print("La cadena está vacía. No hay nada que comprimir.")
else:
    cadena_comprimida += cadena_original[0] # Siempre agregamos el primer caracter
    # Recorremos la cadena desde el segundo caracter
    for i in range(1, len(cadena_original)):
        # Si el caracter actual es diferente al caracter anterior, lo agregamos a la cadena comprimida
        if cadena_original[i] != cadena_original[i-1]:
            cadena_comprimida += cadena_original[i]

    print(f"Cadena original: '{cadena_original}'")
    print(f"Cadena comprimida: '{cadena_comprimida}'")
print("-" * 60)

# Ejercicio 43: Encontrar el número que falta en una secuencia del 1 al N.
print("--- Ejercicio 43: Número faltante en secuencia ---")
print("Ingresa una secuencia de números del 1 al N (separados por espacios), faltando exactamente uno. Ej: 1 2 4 5")
entrada = input("Secuencia: ")
numeros_str = entrada.split()
lista_numeros = []
for num_str in numeros_str:
    try:
        lista_numeros.append(int(num_str)) # Convertimos a enteros
    except ValueError:
        print(f"'{num_str}' no es un número entero válido y será ignorado.")

if len(lista_numeros) < 1: # Si no se ingresaron números
    print("No se ingresaron números válidos en la secuencia.")
elif not lista_numeros: # Si la lista está vacía después de filtrar inválidos
    print("La lista está vacía después de procesar la entrada.")
else:
    # La clave está en que la suma de los primeros N números naturales es N*(N+1)/2.
    # Si falta un número, la suma de la lista será menor que la suma esperada.
    # El número 'N' (el número total de elementos si no faltara ninguno)
    # será la longitud actual de la lista MÁS uno (el que falta).
    n_total = len(lista_numeros) + 1
    suma_esperada = n_total * (n_total + 1) // 2 # Usamos // para división entera
    suma_actual = sum(lista_numeros) # sum() suma todos los elementos de la lista

    numero_faltante = suma_esperada - suma_actual
    print(f"En la secuencia {lista_numeros}, asumiendo que iba del 1 al {n_total}, el número que falta es: {numero_faltante}")
print("-" * 60)

# Ejercicio 44: Simular el juego de piedra, papel o tijeras.
print("--- Ejercicio 44: Juego de Piedra, Papel o Tijeras ---")
import random

opciones_validas = ["piedra", "papel", "tijeras"]

print("¡Vamos a jugar Piedra, Papel o Tijeras!")
print("Tus opciones son: piedra, papel o tijeras (escribe una de ellas).")

eleccion_usuario = input("Tu elección: ").lower() # Convertimos a minúsculas

if eleccion_usuario not in opciones_validas:
    print("Esa no es una opción válida. Por favor, elige 'piedra', 'papel' o 'tijeras'.")
else:
    # La computadora elige una opción aleatoriamente de la lista de opciones válidas
    eleccion_computadora = random.choice(opciones_validas)
    print(f"Tú elegiste: {eleccion_usuario}")
    print(f"La computadora eligió: {eleccion_computadora}")

    # Definimos las reglas del juego
    if eleccion_usuario == eleccion_computadora:
        print("¡Es un EMPATE!")
    elif (eleccion_usuario == "piedra" and eleccion_computadora == "tijeras") or \
         (eleccion_usuario == "papel" and eleccion_computadora == "piedra") or \
         (eleccion_usuario == "tijeras" and eleccion_computadora == "papel"):
        print("¡Tú GANAS!")
    else:
        print("¡La computadora GANA esta ronda!")
print("-" * 60)

# Ejercicio 45: Generar números primos hasta un valor dado (con un método simple).
print("--- Ejercicio 45: Generar Primos hasta N ---")
try:
    limite = int(input("Ingresa un número hasta el cual quieres generar números primos: "))
    if limite < 2:
        print("No hay números primos hasta ese valor. Debes ingresar un número igual o mayor que 2.")
    else:
        lista_primos = []
        # Este método es simple de entender, pero no el más eficiente para números muy grandes (Criba de Eratóstenes es mejor).
        for num in range(2, limite + 1): # Empezamos desde 2 (el primer primo) hasta el límite
            es_primo = True # Asumimos que el número es primo hasta que se demuestre lo contrario
            import math # Aseguramos que math esté disponible para sqrt()
            # Solo necesitamos verificar divisores hasta la raíz cuadrada del número.
            for i in range(2, int(math.sqrt(num)) + 1):
                if num % i == 0: # Si encontramos un divisor, no es primo
                    es_primo = False
                    break # Salimos del bucle interno, no hace falta seguir revisando
            if es_primo:
                lista_primos.append(num) # Si no encontramos ningún divisor, es primo, lo añadimos a la lista
        print(f"Números primos hasta {limite}: {lista_primos}")
except ValueError:
    print("Por favor, ingresa un número entero válido para el límite.")
print("-" * 60)

# Ejercicio 46: Implementar un sistema de reservas de boletos de cine (simplificado).
print("--- Ejercicio 46: Sistema de Reservas de Cine ---")
# Una sala de cine simple representada por una lista de listas (filas y asientos).
# "L" significa Libre, "O" significa Ocupado.
asientos_cine = [
    ["L", "L", "L", "L", "L"], # Fila 1 (índice 0)
    ["L", "L", "L", "L", "L"], # Fila 2 (índice 1)
    ["L", "L", "L", "L", "L"]  # Fila 3 (índice 2)
]

def mostrar_asientos_cine():
    print("\n--- Estado Actual de los Asientos ---")
    print("  1 2 3 4 5  (Asientos)") # Encabezado de asientos
    for i, fila in enumerate(asientos_cine): # enumerate() nos da el índice y el elemento de la lista
        print(f"F{i+1} {' '.join(fila)}") # Muestra F1, F2, F3 y los asientos separados por espacios
    print("-------------------------------------")

def reservar_asiento_cine():
    try:
        # Pedimos fila y asiento, restamos 1 para convertirlos en índices de lista (que empiezan en 0)
        fila_elegida = int(input("Ingresa el número de fila (1-3) para reservar: ")) - 1
        asiento_elegido = int(input("Ingresa el número de asiento (1-5) para reservar: ")) - 1

        # Verificamos que los índices estén dentro de los límites válidos
        if not (0 <= fila_elegida < len(asientos_cine) and 0 <= asiento_elegido < len(asientos_cine[0])):
            print("¡Error! La fila o el asiento ingresado no es válido. Inténtalo de nuevo.")
        # Verificamos si el asiento ya está ocupado
        elif asientos_cine[fila_elegida][asiento_elegido] == "O":
            print("Lo siento, ese asiento ya está OCUPADO. Por favor, elige otro.")
        else:
            # Si todo está bien, marcamos el asiento como ocupado
            asientos_cine[fila_elegida][asiento_elegido] = "O"
            # Mostramos un mensaje de éxito, sumando 1 para mostrar el número de fila/asiento real al usuario
            print(f"¡Asiento F{fila_elegida+1}-A{asiento_elegido+1} RESERVADO con éxito!")
    except ValueError:
        print("Por favor, ingresa números válidos para la fila y el asiento.")
    except IndexError: # En caso de que el usuario ingrese un número fuera de rango muy grande/pequeño
        print("Error al acceder al asiento. Verifica tus entradas.")

def liberar_asiento_cine():
    try:
        fila_elegida = int(input("Ingresa el número de fila (1-3) para liberar: ")) - 1
        asiento_elegido = int(input("Ingresa el número de asiento (1-5) para liberar: ")) - 1

        if not (0 <= fila_elegida < len(asientos_cine) and 0 <= asiento_elegido < len(asientos_cine[0])):
            print("¡Error! La fila o el asiento ingresado no es válido. Inténtalo de nuevo.")
        elif asientos_cine[fila_elegida][asiento_elegido] == "L":
            print("Ese asiento ya está LIBRE. No hay nada que liberar.")
        else:
            asientos_cine[fila_elegida][asiento_elegido] = "L" # Marcar como libre
            print(f"¡Asiento F{fila_elegida+1}-A{asiento_elegido+1} LIBERADO con éxito!")
    except ValueError:
        print("Por favor, ingresa números válidos para la fila y el asiento.")
    except IndexError:
        print("Error al acceder al asiento. Verifica tus entradas.")

# Menú interactivo para el sistema de reservas
while True:
    mostrar_asientos_cine() # Mostrar el estado actual al inicio de cada ciclo
    print("\n--- Menú de Reservas de Cine ---")
    print("1. Reservar asiento")
    print("2. Liberar asiento")
    print("3. Salir del sistema")
    opcion = input("Elige una opción (1, 2 o 3): ")

    if opcion == '1':
        reservar_asiento_cine()
    elif opcion == '2':
        liberar_asiento_cine()
    elif opcion == '3':
        print("¡Gracias por usar el sistema de reservas del cine!")
        break # Sale del bucle while y termina el ejercicio
    else:
        print("Opción no válida. Por favor, elige 1, 2 o 3.")
print("-" * 60)

# Ejercicio 47: Implementar un sistema de notas para estudiantes (simplificado).
print("--- Ejercicio 47: Sistema de Notas de Estudiantes ---")
# Usaremos un diccionario para guardar las notas de cada estudiante.
# La clave será el nombre del estudiante (una cadena) y el valor será una lista de sus notas (números).
notas_estudiantes = {}

def agregar_estudiante():
    # .strip() elimina espacios al inicio/final, .title() pone la primera letra en mayúscula
    nombre = input("Ingresa el nombre del estudiante: ").strip().title()
    if not nombre: # Si el nombre está vacío
        print("El nombre del estudiante no puede estar vacío.")
        return
    if nombre in notas_estudiantes:
        print(f"El estudiante '{nombre}' ya existe en el registro.")
    else:
        notas_estudiantes[nombre] = [] # Creamos una lista vacía para sus futuras notas
        print(f"Estudiante '{nombre}' agregado correctamente.")

def agregar_nota():
    nombre = input("Ingresa el nombre del estudiante para añadirle una nota: ").strip().title()
    if nombre not in notas_estudiantes:
        print(f"El estudiante '{nombre}' no está registrado. Agrégalo primero.")
    else:
        try:
            nota = float(input(f"Ingresa la nota para {nombre} (0-100): "))
            if 0 <= nota <= 100: # Suponemos que las notas válidas están entre 0 y 100
                notas_estudiantes[nombre].append(nota) # Añadimos la nota a la lista de notas del estudiante
                print(f"Nota {nota} agregada a {nombre}.")
            else:
                print("La nota debe estar entre 0 y 100.")
        except ValueError:
            print("Por favor, ingresa un número válido para la nota.")

def ver_notas():
    if not notas_estudiantes: # Si el diccionario está vacío
        print("No hay estudiantes registrados aún en el sistema.")
        return

    print("\n--- Listado de Notas y Promedios ---")
    # Iteramos sobre cada estudiante y sus notas en el diccionario
    for nombre, notas in notas_estudiantes.items(): # .items() nos da pares (clave, valor)
        if notas: # Si la lista de notas no está vacía
            promedio = sum(notas) / len(notas) # Calculamos el promedio
            print(f"  {nombre}: Notas: {notas}, Promedio: {promedio:.2f}") # .2f para 2 decimales
        else:
            print(f"  {nombre}: Aún no tiene notas registradas.")
    print("-------------------------------------")

# Menú interactivo para el sistema de notas
while True:
    print("\n--- Menú Sistema de Notas ---")
    print("1. Agregar un nuevo estudiante")
    print("2. Agregar una nota a un estudiante")
    print("3. Ver todas las notas y promedios")
    print("4. Salir del sistema")
    opcion = input("Elige una opción (1, 2, 3 o 4): ")

    if opcion == '1':
        agregar_estudiante()
    elif opcion == '2':
        agregar_nota()
    elif opcion == '3':
        ver_notas()
    elif opcion == '4':
        print("¡Saliendo del sistema de notas!")
        break # Sale del bucle y termina el ejercicio
    else:
        print("Opción no válida. Por favor, elige 1, 2, 3 o 4.")
print("-" * 60)

# Ejercicio 48: Crear un conversor de moneda (con tasas fijas).
print("--- Ejercicio 48: Conversor de Moneda ---")
# Definimos algunas tasas de cambio de forma fija en un diccionario anidado.
# Esto es para el ejemplo; en la vida real, las tasas cambian constantemente.
# La clave exterior es la moneda de origen, la clave interior es la moneda de destino.
tasas_cambio = {
    "USD": {"EUR": 0.92, "GBP": 0.79, "JPY": 156.40, "COP": 3950.00},
    "EUR": {"USD": 1.09, "GBP": 0.86, "JPY": 170.00, "COP": 4300.00},
    "COP": {"USD": 0.00025, "EUR": 0.00023, "GBP": 0.00020, "JPY": 0.0064},
    # Puedes añadir más monedas y sus tasas aquí si lo deseas
}

def convertir_moneda():
    # Mostramos las monedas disponibles para que el usuario sepa qué elegir
    monedas_disponibles = ", ".join(sorted(tasas_cambio.keys()))
    print(f"\nMonedas disponibles: {monedas_disponibles}")
    
    moneda_origen = input("Ingresa la moneda de origen (ej: USD): ").upper() # .upper() para estandarizar a mayúsculas
    moneda_destino = input("Ingresa la moneda de destino (ej: EUR): ").upper()

    # Verificamos si las monedas ingresadas son válidas y si la conversión está definida.
    if moneda_origen not in tasas_cambio:
        print(f"Error: La moneda de origen '{moneda_origen}' no está soportada.")
        return
    if moneda_destino not in tasas_cambio[moneda_origen]:
        print(f"Error: La conversión de '{moneda_origen}' a '{moneda_destino}' no está definida en el sistema.")
        return

    try:
        cantidad = float(input(f"Ingresa la cantidad en {moneda_origen} que quieres convertir: "))
        if cantidad < 0:
            print("La cantidad a convertir no puede ser negativa.")
            return

        tasa = tasas_cambio[moneda_origen][moneda_destino] # Obtenemos la tasa de cambio
        resultado = cantidad * tasa # Realizamos la conversión
        print(f"{cantidad:.2f} {moneda_origen} son {resultado:.2f} {moneda_destino}.") # .2f para 2 decimales
    except ValueError:
        print("Por favor, ingresa una cantidad numérica válida para la conversión.")

# Menú interactivo para el conversor de moneda
while True:
    print("\n--- Menú Conversor de Moneda ---")
    print("1. Realizar una conversión")
    print("2. Salir del conversor")
    opcion = input("Elige una opción (1 o 2): ")

    if opcion == '1':
        convertir_moneda()
    elif opcion == '2':
        print("¡Gracias por usar el conversor de moneda!")
        break # Sale del bucle y termina el ejercicio
    else:
        print("Opción no válida. Por favor, elige 1 o 2.")
print("-" * 60)

# Ejercicio 49: Convertir una cadena a mayúsculas y minúsculas.
print("--- Ejercicio 49: Mayúsculas y Minúsculas ---")
cadena_original = input("Ingresa una cadena de texto: ")

# Métodos integrados de string para cambiar el caso
cadena_mayusculas = cadena_original.upper() # Convierte toda la cadena a mayúsculas
cadena_minusculas = cadena_original.lower() # Convierte toda la cadena a minúsculas
cadena_titulo = cadena_original.title()     # Convierte la primera letra de cada palabra a mayúscula
cadena_capitalizada = cadena_original.capitalize() # Convierte solo la primera letra de la cadena a mayúscula

print(f"Original:    '{cadena_original}'")
print(f"Mayúsculas:  '{cadena_mayusculas}'")
print(f"Minúsculas:  '{cadena_minusculas}'")
print(f"Tipo Título: '{cadena_titulo}'")
print(f"Capitalizada: '{cadena_capitalizada}'")
print("-" * 60)

# Ejercicio 50: Eliminar un elemento específico de una lista.
print("--- Ejercicio 50: Eliminar elemento de una lista ---")
print("Ingresa elementos para la lista (separados por espacios, ej: manzana banana naranja manzana):")
entrada_lista = input("Lista de elementos: ")
lista_elementos = entrada_lista.split()

if not lista_elementos:
    print("La lista está vacía. No hay elementos para eliminar.")
else:
    print(f"Lista original: {lista_elementos}")
    elemento_a_eliminar = input("Ingresa el elemento que deseas eliminar (se eliminará la primera ocurrencia): ")

    # El método .remove() elimina la primera ocurrencia del valor especificado.
    # Si el elemento no está en la lista, lanza un ValueError.
    try:
        lista_elementos.remove(elemento_a_eliminar)
        print(f"Elemento '{elemento_a_eliminar}' eliminado. Lista resultante: {lista_elementos}")
    except ValueError:
        print(f"El elemento '{elemento_a_eliminar}' no se encontró en la lista.")
print("-" * 60)

# Ejercicio 51: Unir los elementos de una lista en una cadena.
print("--- Ejercicio 51: Unir elementos de lista en cadena ---")
print("Ingresa elementos para la lista (separados por espacios, ej: hola mundo python):")
entrada_lista = input("Elementos de la lista: ")
lista_palabras = entrada_lista.split()

# El método .join() de las cadenas es muy útil para esto.
# Se usa sobre la cadena que servirá como "separador" entre los elementos de la lista.
separador_espacio = " "
cadena_unida_espacio = separador_espacio.join(lista_palabras)
print(f"Lista original: {lista_palabras}")
print(f"Unida con espacios: '{cadena_unida_espacio}'")

separador_guion = "-"
cadena_unida_guion = separador_guion.join(lista_palabras)
print(f"Unida con guiones: '{cadena_unida_guion}'")

separador_vacio = ""
cadena_unida_sin_espacios = separador_vacio.join(lista_palabras)
print(f"Unida sin espacios: '{cadena_unida_sin_espacios}'")
print("-" * 60)

# Ejercicio 52: Dividir una cadena en una lista de palabras.
print("--- Ejercicio 52: Dividir cadena en palabras ---")
cadena_completa = input("Ingresa una frase o cadena de texto (ej: Esto es una frase de ejemplo): ")

# El método .split() de las cadenas divide la cadena en una lista de subcadenas.
# Si no le pasamos ningún argumento, divide por espacios en blanco y maneja múltiples espacios.
lista_de_palabras = cadena_completa.split()
print(f"Cadena original: '{cadena_completa}'")
print(f"Lista de palabras: {lista_de_palabras}")

# También podemos especificar un separador, por ejemplo, coma:
cadena_con_comas = "manzana,banana,naranja"
lista_por_comas = cadena_con_comas.split(",")
print(f"Cadena con comas: '{cadena_con_comas}'")
print(f"Dividida por comas: {lista_por_comas}")
print("-" * 60)

# Ejercicio 53: Calcular el producto de todos los números en una lista.
print("--- Ejercicio 53: Producto de números en una lista ---")
print("Ingresa números separados por espacios (ej: 2 3 4 5):")
entrada = input("Números: ")
numeros_str = entrada.split()
lista_numeros = []
for num_str in numeros_str:
    try:
        lista_numeros.append(float(num_str))
    except ValueError:
        print(f"'{num_str}' no es un número válido y será ignorado.")

if not lista_numeros:
    print("La lista está vacía o no contiene números válidos. El producto es 1 (por convención para listas vacías).")
    producto_total = 1
else:
    producto_total = 1 # Empezamos con 1, porque cualquier número multiplicado por 1 es el mismo
    for numero in lista_numeros:
        producto_total *= numero # Equivalente a: producto_total = producto_total * numero
    print(f"La lista de números es: {lista_numeros}")
    print(f"El producto de todos los números es: {producto_total}")
print("-" * 60)

# Ejercicio 54: Verificar si un número es una potencia de 2.
print("--- Ejercicio 54: Potencia de 2 ---")
try:
    numero = int(input("Ingresa un número entero para verificar si es una potencia de 2: "))

    if numero <= 0: # Las potencias de 2 son números positivos (1, 2, 4, 8, ...)
        es_potencia_de_2 = False
    elif numero == 1: # 2^0 = 1, así que 1 es una potencia de 2
        es_potencia_de_2 = True
    else:
        es_potencia_de_2 = True
        temp_numero = numero
        # Mientras el número sea divisible por 2 y no sea 0, lo dividimos.
        # Si al final queda 1, era una potencia de 2.
        while temp_numero % 2 == 0 and temp_numero > 0:
            temp_numero //= 2
        if temp_numero != 1:
            es_potencia_de_2 = False

    if es_potencia_de_2:
        print(f"El número {numero} SÍ es una potencia de 2.")
    else:
        print(f"El número {numero} NO es una potencia de 2.")

    # Un truco muy común en programación para potencias de 2 (si num > 0):
    # return (num & (num - 1) == 0) and num != 0
    # Esto usa operaciones a nivel de bits y es muy eficiente.
    # print(f"Con truco de bits: {bool((numero > 0) and ((numero & (numero - 1)) == 0))}")
except ValueError:
    print("Por favor, ingresa un número entero válido.")
print("-" * 60)

# Ejercicio 55: Encontrar la intersección de dos listas.
print("--- Ejercicio 55: Intersección de dos listas ---")
print("Ingresa elementos para la primera lista (separados por espacios, ej: a b c d):")
entrada1 = input("Lista 1: ")
lista1 = entrada1.split()

print("Ingresa elementos para la segunda lista (separados por espacios, ej: c d e f):")
entrada2 = input("Lista 2: ")
lista2 = entrada2.split()

# La intersección son los elementos que están en AMBAS listas.
# Usar conjuntos (sets) es la forma más eficiente y elegante para esto en Python.
# Un conjunto es una colección de elementos únicos.
set1 = set(lista1)
set2 = set(lista2)

# El operador '&' entre conjuntos calcula la intersección.
interseccion_set = set1 & set2
# Convertimos el conjunto de intersección de nuevo a una lista para mostrarlo.
interseccion_lista = list(interseccion_set)

print(f"Lista 1: {lista1}")
print(f"Lista 2: {lista2}")
print(f"La intersección de las dos listas es: {interseccion_lista}")

# Forma manual (menos eficiente para listas muy grandes):
# interseccion_manual = []
# for elemento in lista1:
#     if elemento in lista2 and elemento not in interseccion_manual: # Evitar duplicados en el resultado
#         interseccion_manual.append(elemento)
# print(f"Intersección (manual): {interseccion_manual}")
print("-" * 60)

# Ejercicio 56: Implementar el algoritmo de búsqueda binaria.
print("--- Ejercicio 56: Búsqueda Binaria ---")
# La búsqueda binaria solo funciona en listas ORDENADAS.
# Es mucho más rápida que la búsqueda lineal para listas grandes.
print("Ingresa números ordenados separados por espacios (ej: 1 5 8 12 13 15 18):")
entrada_ordenada = input("Lista ordenada de números: ")
numeros_str = entrada_ordenada.split()
lista_ordenada = []
for num_str in numeros_str:
    try:
        lista_ordenada.append(int(num_str))
    except ValueError:
        print(f"'{num_str}' no es un número entero válido y será ignorado.")

# Ordenamos la lista para asegurar que sea apta para búsqueda binaria, aunque ya se pidió ordenada.
lista_ordenada.sort()
print(f"Lista para buscar (ordenada): {lista_ordenada}")

try:
    elemento_buscar = int(input("Ingresa el número que quieres buscar: "))
except ValueError:
    print("Por favor, ingresa un número entero para buscar.")
    elemento_buscar = None # Para evitar errores si la entrada no es un número

if elemento_buscar is not None:
    # Definimos la función de búsqueda binaria
    def busqueda_binaria(lista, elemento):
        izquierda = 0
        derecha = len(lista) - 1

        while izquierda <= derecha:
            medio = (izquierda + derecha) // 2 # Calculamos el índice del medio
            if lista[medio] == elemento: # Si el elemento está en el medio
                return medio # ¡Lo encontramos! Devolvemos su índice
            elif lista[medio] < elemento: # Si el elemento buscado es mayor que el del medio
                izquierda = medio + 1 # Buscamos en la mitad derecha
            else: # Si el elemento buscado es menor que el del medio
                derecha = medio - 1 # Buscamos en la mitad izquierda
        return -1 # Si el bucle termina, significa que el elemento no se encontró

    indice_encontrado = busqueda_binaria(lista_ordenada, elemento_buscar)

    if indice_encontrado != -1:
        print(f"El número {elemento_buscar} se encontró en el índice {indice_encontrado}.")
    else:
        print(f"El número {elemento_buscar} NO se encontró en la lista.")
print("-" * 60)

# Ejercicio 57: Calcular la raíz cuadrada de un número sin usar `math.sqrt()`.
print("--- Ejercicio 57: Raíz Cuadrada (sin math.sqrt) ---")
# Usaremos el método de Newton-Raphson, que es un algoritmo iterativo.
try:
    numero = float(input("Ingresa un número no negativo para calcular su raíz cuadrada: "))

    if numero < 0:
        print("No se puede calcular la raíz cuadrada de un número negativo en los números reales.")
    elif numero == 0:
        print("La raíz cuadrada de 0 es 0.")
    else:
        aproximacion = numero / 2.0 # Empezamos con una aproximación inicial
        tolerancia = 0.000001 # Qué tan preciso queremos el resultado (un número muy pequeño)

        # Repetimos mientras la diferencia entre la aproximación actual y la anterior sea mayor que la tolerancia
        while abs(aproximacion * aproximacion - numero) >= tolerancia:
            aproximacion = (aproximacion + numero / aproximacion) / 2.0 # Fórmula de Newton-Raphson
        print(f"La raíz cuadrada aproximada de {numero} es: {aproximacion:.5f}") # Mostramos con 5 decimales
except ValueError:
    print("Por favor, ingresa un número numérico válido.")
print("-" * 60)

# Ejercicio 58: Generar los primeros N números de Fibonacci.
print("--- Ejercicio 58: Números de Fibonacci ---")
# La secuencia de Fibonacci comienza con 0 y 1, y cada número siguiente es la suma de los dos anteriores:
# 0, 1, 1, 2, 3, 5, 8, 13, ...
try:
    n_fibonacci = int(input("Ingresa cuántos números de Fibonacci quieres generar (N): "))

    if n_fibonacci <= 0:
        print("Por favor, ingresa un número entero positivo para N.")
    elif n_fibonacci == 1:
        print("Los primeros 1 números de Fibonacci son: [0]")
    else:
        fib_secuencia = [0, 1] # Empezamos con los dos primeros números
        # Generamos los números restantes hasta alcanzar N
        while len(fib_secuencia) < n_fibonacci:
            siguiente_fib = fib_secuencia[-1] + fib_secuencia[-2] # Suma los dos últimos
            fib_secuencia.append(siguiente_fib) # Añade el nuevo número a la secuencia
        print(f"Los primeros {n_fibonacci} números de Fibonacci son: {fib_secuencia}")
except ValueError:
    print("Por favor, ingresa un número entero válido para N.")
print("-" * 60)

# Ejercicio 59: Ordenar una lista de cadenas alfabéticamente.
print("--- Ejercicio 59: Ordenar lista de cadenas alfabéticamente ---")
print("Ingresa palabras o nombres separados por espacios (ej: zanahoria manzana pera uva banana):")
entrada_cadenas = input("Lista de cadenas: ")
lista_cadenas = entrada_cadenas.split()

if not lista_cadenas:
    print("La lista está vacía. No hay cadenas para ordenar.")
else:
    print(f"Lista original: {lista_cadenas}")
    # El método .sort() también funciona para listas de cadenas y las ordena alfabéticamente.
    # Por defecto, la ordenación es lexicográfica (alfabética) y sensible a mayúsculas/minúsculas.
    # Para ordenar ignorando mayúsculas/minúsculas, podrías usar:
    # lista_cadenas.sort(key=str.lower)
    lista_cadenas.sort()
    print(f"Lista ordenada alfabéticamente: {lista_cadenas}")
print("-" * 60)

# Ejercicio 60: Calcular la distancia entre dos puntos en un plano 2D.
print("--- Ejercicio 60: Distancia entre dos puntos 2D ---")
# Necesitamos math para la raíz cuadrada.
import math

print("Vamos a calcular la distancia entre dos puntos (x1, y1) y (x2, y2).")
try:
    x1 = float(input("Ingresa la coordenada X del primer punto (x1): "))
    y1 = float(input("Ingresa la coordenada Y del primer punto (y1): "))
    x2 = float(input("Ingresa la coordenada X del segundo punto (x2): "))
    y2 = float(input("Ingresa la coordenada Y del segundo punto (y2): "))

    # La fórmula de la distancia entre dos puntos (x1, y1) y (x2, y2) es:
    # Distancia = sqrt((x2 - x1)^2 + (y2 - y1)^2)
    distancia = math.sqrt((x2 - x1)**2 + (y2 - y1)**2)

    print(f"El Punto 1 es ({x1}, {y1})")
    print(f"El Punto 2 es ({x2}, {y2})")
    print(f"La distancia entre los dos puntos es: {distancia:.2f}") # Mostramos con 2 decimales
except ValueError:
    print("Por favor, asegúrate de ingresar números válidos para las coordenadas.")
print("-" * 60)

print("\n==============================================================================")
print("¡Felicidades! Has completado los 60 primeros ejercicios de pensamiento algorítmico.")
print("¡Sigue practicando para mejorar tus habilidades de programación!")
print("==============================================================================")

