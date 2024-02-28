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
