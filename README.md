# MyCodes
For intership
import pygame
from settings import Settings
from ship import Ship
import game_functions as gf
#Creat display

def run_game():
    #Creat object display
    pygame.init()
    ai_settings = Settings()
    screen = pygame.display.set_mode(
        (ai_settings.screen_width,ai_settings.screen_height))#Разрешение
    pygame.display.set_caption("Alien Invasion")#Заголовок
    #Create ship.
    ship = Ship(ai_settings,screen)
    while True:
        #Keybords and mouse.
        gf.check_events(ship)
        ship.update()
        gf.update_screen(ai_settings,screen,ship)
run_game()
