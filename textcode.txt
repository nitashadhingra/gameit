import pygame, sys
from pygame.locals import QUIT   #,KEYUP,K_ESCAPE

def runtetris():
    pygame.init                  #starting game engine
    window_size=(640,480)
    screen = pygame.display.set_mode(window_size)
    pygame.display.set_caption('TETRIS')

    game_matrix = matrix()

    while True:
        screen.fill((0,0,0))

        pygame.draw.rect(
            screen,
            (0,0,155),
            [150,50,20*15,20*20], 5)

        pygame.display.update()
        for event in pygame.event.get(QUIT):
            pygame.quit()
            sys.exit()

def matrix():
    cols=15
    rows=20
    matrixx=[]
    for row in range(rows):
        new_row=[]
        for column in range(cols):
            new_row.append('.')
        matrixx.append(new_row)
    return matrixx

runtetris()
