---
title:  Making Animations with Python
date:   2021-02-31 15:01:35 +0300
image:  'https://miro.medium.com/max/689/1*ICPW7ZxYOzlOoUr6HHcM_w.gif'
tags:   [Coding,animations]
---
Hello !, We’ll create this simple animation in not more than 30 lines of code.
Requirements:- ffmpeg installed can be installed from this site , python installed
Firstly Open the cmd and type out pip install manim
Now,Open Your text-editor or IDE and write then the code the explanation is in comments

	from manim import *
	class animateMyName(Scene): # Scene reffers that it is a scene for Manim ## MUST ##
	def construct(self):
	# Creating object
	circle,sq = Circle(),Square()
	circle.set_fill(PINK,opacity = .5) # changed colour of circle
	sq.set_fill(BLUE,opacity=.7) # changed colour of Square
	first_line = Text(‘My name is Arnav’,color=ORANGE)
	sec_line = Text(‘We have created beautiful name Animation’)
	third_line = Text(‘Using MANIM’,color=RED)
	sq.next_to(first_line,UP)
	circle.next_to(first_line,UP)
	# Adjust the sec_line benath first line
	sec_line.next_to(first_line,DOWN) # down as it has to be downwards
	# Adjust third_line beneath sec_line
	third_line.next_to(sec_line,DOWN)
	# Display the text
	self.wait(2) # pauses for 2 second
	self.play(ShowCreation(sq)) # shows the square
	self.play(Transform(sq,circle))
	self.play(Write(first_line),Write(sec_line),Write(third_line)) # ‘write’ func writes the lines
	self.wait(3) # pause again

Our code is done to run it open your terminal window and locate the file and type:- 

	“ manim animations.py animateMyName -p -ql”
	“-p -qh” exports in high quality
	“-p -qm” exports in medium quality
	“-p -ql” exports the file in low quality

We can add -i for exporting as GIF like “-p -ql -i”