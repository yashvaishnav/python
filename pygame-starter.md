```python
import sys
import pygame
# The first thing is tell pygame to start
pygame.init()
# Make the screen with a certain size
screen = pygame.display.set_mode((500, 500))

# Set up all the images in my game
image = pygame.image.load("basketball.png")
imagePosition = image.get_rect()

while True:
	# Check if the exit event was launched
	for event in pygame.event.get():
		if event.type == pygame.QUIT:
			sys.exit()
		# Check other key events here

	# Move image positions
	imagePosition = imagePosition.move([5, 5])

	# Draw the image at the image position
	screen.fill((114, 196, 207))
	screen.blit(image, imagePosition)

	pygame.display.flip()
	pygame.time.delay(33)
```
