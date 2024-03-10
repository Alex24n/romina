# Importar la biblioteca NumPy
import numpy as np

# Definir las ciudades, los días y las semanas
ciudades = ["Guayaquil", "Quito", "Cuenca", "Loja", "Manta"]
dias = ["Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado", "Domingo"]
semanas = ["Semana 1", "Semana 2", "Semana 3", "Semana 4"]

# Crear una matriz 3D vacía con la forma (ciudades, días, semanas)
matriz = np.empty((len(ciudades), len(dias), len(semanas)))

# Llenar la matriz con datos de temperaturas aleatorios entre 15 y 35 grados Celsius
np.random.seed(0) # Fijar una semilla para la reproducibilidad
matriz = np.random.randint(15, 36, size=matriz.shape)

# Mostrar la matriz
print("Matriz de temperaturas:")
print(matriz)

# Usar bucles anidados para calcular el promedio de temperaturas para cada ciudad y semana
for i, ciudad in enumerate(ciudades):
    for j, semana in enumerate(semanas):
        # Extraer la submatriz correspondiente a la ciudad y la semana
        submatriz = matriz[i, :, j]
        # Calcular el promedio de temperaturas
        promedio = np.mean(submatriz)
        # Mostrar el resultado
        print(f"El promedio de temperaturas para {ciudad} en {semana} es {promedio:.2f} grados Celsius.")
def temperatura_promedio(datos):
    promedios_ciudades = {}
    
    for ciudad, semanas in datos.items():
        total_temperaturas = 0
        total_dias = 0
        
        for semana, temperaturas in semanas.items():
            total_temperaturas += sum(temperaturas)
            total_dias += len(temperaturas)
        
        promedio = total_temperaturas / total_dias
        promedios_ciudades[ciudad] = promedio
    
    return promedios_ciudades

# Ejemplo de datos de temperaturas de 3 ciudades durante 4 semanas
datos_temperaturas = {
    'Ciudad A': {
        'Semana 1': [25, 26, 27, 28, 29],
        'Semana 2': [24, 25, 26, 27, 28],
        'Semana 3': [23, 24, 25, 26, 27],
        'Semana 4': [22, 23, 24, 25, 26]
    },
    'Ciudad B': {
        'Semana 1': [20, 21, 22, 23, 24],
        'Semana 2': [19, 20, 21, 22, 23],
        'Semana 3': [18, 19, 20, 21, 22],
        'Semana 4': [17, 18, 19, 20, 21]
    },
    'Ciudad C': {
        'Semana 1': [30, 31, 32, 33, 34],
        'Semana 2': [29, 30, 31, 32, 33],
        'Semana 3': [28, 29, 30, 31, 32],
        'Semana 4': [27, 28, 29, 30, 31]
    }
}

# Llamada a la función y muestra de resultados
resultados = temperatura_promedio(datos_temperaturas)
for ciudad, promedio in resultados.items():
    print(f"Temperatura promedio en {ciudad}: {promedio:.2f} grados Celsius")
    
