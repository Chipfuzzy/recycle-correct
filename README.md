import pgzrun
import random

FONT_option = (255,255,255)
HEIGHT = 800
WIDTH = 1000
CENTRE_X = WIDTH / 2
CENTRE_Y = HEIGHT / 2
CENTRE = (CENTRE_X, CENTRE_Y)
FINAL_LEVEL = 6
START_SPEED = 15
ITEMS = ["battery", "chips", "plastic bottle", "pbag", "bottle"]

game_over = False
game_complete = False
current_level = 1
items = []
animations = [] 

def draw():
    global items, current_level, game_over, game_complete
    screen.clear()
    screen.blit("recycle", (0, 0))
    if game_over:
        display_message("GAME OVER", "try again")
    elif game_complete:
        display_message("YOU WON", "well done")
    else:
        for item in items:
            item.draw()
