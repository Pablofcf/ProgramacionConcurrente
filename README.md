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
```python
from time import sleep
from threading import Thread

# Menú con las opciones disponibles
MENU = [
    '1. Mostrar Biblioteca',
    '2. Descargar Libro',
    '3. Salir'
]

# Lista inicial de libros en la biblioteca
biblioteca = ['El Quijote']

# Función para mostrar las opciones del menú
def mostrar_menu():
    for opcion in MENU:
        print(opcion)

# Función que muestra los libros almacenados en la biblioteca
def mostrar_biblioteca():
    print('Libros de la biblioteca:')
    for libro in biblioteca:
        print(libro)

# Función que simula la descarga y añade un libro a la biblioteca
def descargar_y_aniadir_libro(titulo):
    libro = titulo.title()
    print(f'Descargando {libro}...')
    sleep(7)  # Simula un retardo en la descarga
    print(f'Descarga de {libro} completa')
    biblioteca.append(libro)

# Bloque principal del programa
if __name__ == '__main__':
    while True:
        mostrar_menu()
        op = input()
        if op == '1':
            mostrar_biblioteca()
            print('PRESIONE ENTER PARA VOLVER AL MENÚ PRINCIPAL')
            input()
            continue
        elif op == '2':
            titulo = input('Introduzca el título:\n')
            descargar_y_aniadir_libro(titulo)
            print('PRESIONE ENTER PARA VOLVER AL MENÚ PRINCIPAL')
            input()
            continue
        elif op == '3':
            break
```
