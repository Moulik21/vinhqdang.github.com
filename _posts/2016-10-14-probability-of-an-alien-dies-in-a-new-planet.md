---
layout: post
title: "Probability of an alien dies in a new planet"
description: ""
category: 
tags: [probability,puzzle]
---
{% include JB/setup %}

A question is asked (and answered) in a [Youtube video](https://www.youtube.com/watch?v=A5-Q2GdD5xw&index=30&list=PLDZcGqoKA84Eo56G1kIFE6IYwpxFgxFXB).

However, the answer is not really to follow for dummies (like me), so if you want to have a simulator to check whether it is true or not, you might use the following code (written in Python 2.7.12)

```
# YouTube video: goo.gl/mJiEBL

# In the day 1, there is a creature (alien). At each day,
# the animal can do 1 of 4 actions with probability = 1/4
# for each

# 1. die
# 2. do nothing
# 3. double itself (so there are 2 aliens)
# 4. triple itself (so there are 3 aliens)

# what is the probability that in the end
# there is no alien

# number of simulation
N = 10000

# number of day for each simulation
D = 10000

import random

def simulate ():
	# number of living animals
	count = 1
	for i in range (D):
		tmp_count = count
		# for each animal
		for j in range (tmp_count):
			# create a random variable
			x = random.uniform (0,1)
			if x <= 0.25:
				count  -= 1
			elif x <= 0.5:
				count += 1
			elif x <= 0.75:
				count += 2
			# remaining case: do nothing
		if (count <= 0):
			return 1
	if (count <= 0):
		return 1
	else:
		return 0 

die_out = 0
for i in range (N):
	die_out += simulate()

print (float(die_out)/N)
```