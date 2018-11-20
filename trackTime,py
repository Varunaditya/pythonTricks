#A python code that uses context manager to track time of code blocks.

from time import time
from time import sleep

class trackTime:
	def __init__(self):
		self.level = 0
		self.startTime = []
		self.now = 0


	def __enter__(self):
		self.level += 1
		self.startTime.append(time())
		return self

	def __exit__(self, exc_type, exc_val, exc_tb):
		print("Level #{}: {} seconds".format(self.level, round(time() - self.startTime[self.level - 1], 2)))
		self.level -= 1


with trackTime() as t:
	sleep(2)
	with t:
		sleep(3)
		sleep(1)
		with t:
			sleep(3)
