from typing import Any
import pygame
from pygame.locals import *
from sys import exit


pygame.init()
tela = pygame.display.set_mode((600, 600))
class sapo(pygame.sprite.Sprite):
    def __init__(self) -> None:
        super().__init__()
        self.image = pygame.Surface((60, 60))
        self.lista = []
        self.lista.append(pygame.image.load('sprites/attack_1.png'))
        self.lista.append(pygame.image.load('sprites/attack_2.png'))
        self.lista.append(pygame.image.load('sprites/attack_3.png'))
        self.lista.append(pygame.image.load('sprites/attack_4.png'))
        self.lista.append(pygame.image.load('sprites/attack_5.png'))
        self.lista.append(pygame.image.load('sprites/attack_6.png'))
        self.lista.append(pygame.image.load('sprites/attack_7.png'))
        self.lista.append(pygame.image.load('sprites/attack_8.png'))
        self.lista.append(pygame.image.load('sprites/attack_9.png'))
        self.lista.append(pygame.image.load('sprites/attack_10.png'))
        self.image = self.lista[0]
        self.rect = self.image.get_rect()
        self.rect.x = 100
        self.rect.y = 100
    def update(self) -> None:
        if self.rect.x < 600:
            self.rect.x += 1
        else:
            self.rect.x = 0
sapo1 = sapo()
t = pygame.sprite.Group()
t.add(sapo1)

        

        
while True:
    tela.fill((0,0,0))
    t.update()
    t.draw(tela)

    for event in pygame.event.get():
        if event.type == QUIT:
            pygame.quit()
            exit()
    
    pygame.display.flip()
