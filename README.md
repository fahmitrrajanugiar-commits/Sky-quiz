from pygame import *
from random import randint


font.init()
font1 = font.SysFont('Arial',90)
win = font1.render('YOU WIN!', True, (255, 255, 255))
lose = font1.render('YOU LOSE!', True, (180, 0, 0))


font2 = font.SysFont('Arial', 36)


#background music
mixer.init()
mixer.music.load('space.ogg')
mixer.music.play()
fire_sound = mixer.Sound('fire.ogg')
#we need the following images:
img_back = "galaxy.jpg" #game background
img_bullet = "bullet.png" #bullet
img_hero = "rocket.png" #hero
img_enemy = "ufo.png" #enemy
img_ast = "asteroid.png" 

score =  0 
goal = 20 
lost = 0
max_lost = 10
life = 5

class Gamespirite('spirite.sprite'):
  def __init__(self, player_image, player_x, player_y, size_x, size_y, player speed)
    spirite.Spirite __init__ (self)
    self.image = transform.scale(image.load(player.image), (size_x, size_y))
    self.speed = player_speed

    self.rect = self.image.get.rect()
    self.rect_x = player_x
    self.rect_y = player_y

  def update(self):
      self.rect.y += self.speed
      global lost
      #disappears upon reaching the screen edge
      if self.rect.y > win_height:
          self.rect.x = randint(80, win_width - 80)
          self.rect.y = 0
          lost = lost + 1

class bullet(Gamesprite):
      def update(self):
          self.rect.y += self.speed
      if  self.rect.y < 0:
          self.kill()


