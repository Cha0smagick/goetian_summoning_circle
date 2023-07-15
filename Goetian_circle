import pygame
import math

# Dimensiones de la ventana
WIDTH = 800
HEIGHT = 600

# Inicializar Pygame
pygame.init()

# Crear la ventana
window = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Pentágono Movimiento")

# Definir colores
BLACK = (0, 0, 0)
RED = (255, 0, 0)

# Posición y rotación del pentágono
x = WIDTH // 2
y = HEIGHT // 2
rotation = 0

# Velocidad de rotación del pentágono
rotation_speed = 0.01

# Bucle principal del juego
running = True
while running:
    # Manejo de eventos
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    # Limpiar la pantalla
    window.fill(BLACK)

    # Dibujar el pentágono en el centro de la pantalla
    points = []
    for i in range(5):
        angle = (math.pi * 2 * i / 5) - math.pi / 2 + rotation
        points.append((x + math.cos(angle) * 100, y + math.sin(angle) * 100))
    pygame.draw.lines(window, RED, True, points, 2)  # 2 es el grosor de las líneas del pentágono

    # Conectar cada una de las puntas con las otras puntas
    for i in range(5):
        for j in range(i + 1, 5):
            pygame.draw.line(window, RED, points[i], points[j], 2)

    # Dibujar el círculo alrededor del pentágono
    pygame.draw.circle(window, RED, (x, y), 120, 2)

    # Actualizar la pantalla
    pygame.display.flip()

    # Actualizar la rotación del pentágono
    rotation += rotation_speed

# Salir del programa
pygame.quit()
