# ProgramacionConcurrente
```python
import threading
#Sirve para manejar múltiples tareas simultáneamente mediante el uso de hilos (threads)

# Función que imprime números del 0 al 4
def imprimir_numeros():
    for i in range(5):
        print(f"Número: {i}")

# Creación de hilos
hilo1 = threading.Thread(target=imprimir_numeros)
hilo2 = threading.Thread(target=imprimir_numeros)

# Inicio de los hilos
hilo1.start()
hilo2.start()

# Espera a que ambos hilos finalicen
hilo1.join()
hilo2.join()
```
