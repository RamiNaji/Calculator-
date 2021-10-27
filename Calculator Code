import turtle as trtl
import time
t = trtl.Turtle()
wn = trtl.Screen()

#screen size set to be proportional to coordinates.
wn.setup(800, 800)
#Max speed
t.speed(0)
#pensize and turtle shape
t.pensize(3)

mult = 40.0



def graph():
  wn.bgpic('800x800_coord.png')

  
  #splits user equation to usable variables
  while True:
    try:
      eq = trtl.textinput('Calculator', ("What is the equation? (Please enter eq with terms in order of degree. If you do not, your equation will not be right): "))
      eq = eq.replace(' ', '')
      eq = eq.replace('x', '')
      eq = eq.replace('y=', '')
      eq = eq.replace('+', '')
      eq = list(eq)
      global a
      global b
      
      if len(eq) == 2:    
          while True:
            try:
              neg_1 = eq.index('-')
              eq.pop(neg_1)
              if  neg_1 == 0:
                a = float(eq[2])*-1
                break
            except ValueError or Exception:
                a= float(eq[0])
                b=float(eq[1])
                break
      elif len(eq) == 3:
            while True:
                try:
                  a=float(eq[0])
                  neg_1 = eq.index('-')
                  if neg_1 == 1:
                    b = float(eq[2])*-1
                    break
                except ValueError or Exception:
                    neg_1 = eq.index('-')
                    a = float(eq[1])*-1
                    b = float(eq[2])
                    break
      elif len(eq) == 4:
           neg_1 = eq.index('-')
           eq.pop(neg_1)
           if  neg_1 == 0:
            a = float(eq[2])*-1
           neg_1 = eq.index('-')
           if neg_1 == 1:
            b = float(eq[2])*-1
           
      

      break
      
    except Exception:
      print("Invalid Format of eq. Format as: y=mx+b")
      continue


  #multiplier. Each unit on graph is 40 pixels.
  mult = float(40)


  #Draws first arrow.
  t.penup()
  x = (-10-b)/a
  t.goto(x*mult, -10*mult)
  top_heading  = -90-(45/a)

  t.setheading(top_heading)
  t.backward(21.66)
  t.setheading(top_heading + 90)
  t.pendown()
  l = 25
  t.backward(l/2)
  t.fillcolor('black')
  t.begin_fill()
  for i in range(3):
    t.fd(l)
    t.right(120)
  t.end_fill()


  #Goes to point with the least x-value that still fits in graph.
  x_neg = float(-10)
  y_neg = float(a*x_neg + b)
  while y_neg <= -10:
    wn.update()
    y_neg = float(-1*(abs(a*x_neg)) + b)
    x_neg += 0.01


  #Creates line
  t.penup()
  t.goto(x_neg*mult, y_neg*mult)
  t.pendown()
  x = x_neg
  while True:
      t.pendown()
      y = a*x + b
      t.goto(x*mult, y*mult)
      x += 1
      lol = t.ycor()
      limit  = float((int(lol)/40))
      xint = x
      xint = xint//1
      yint = y
      yint = yint//1
      if xint == 0:
        print(x,y)
      if a>= 0:
        if limit >= 10:
          print('done+')
          break
      else:
        if limit <= -10:
          print('done-')
          break
      
  #creates last arrow.
  t.penup()
  x = (10-b)/a
  t.goto(x*mult, 10*mult)
  top_heading  = 90-(45/a)

  t.setheading(top_heading)
  t.backward(21.66)
  t.setheading(top_heading + 90)
  t.pendown()
  l = 25
  t.backward(l/2)
  t.begin_fill()
  for i in range(3):
    t.fd(l)
    t.right(120)
  t.end_fill()

#runs function
graph()

#creates coordinates
print()
t.penup()
t.goto(0,40*b)
t.write('  (0' + ',' + str(b) + ')', font = (30))
x=(0-b/a)
print(str(x) + ',' + '0')
t.penup()
t.goto(40*x,0)
t.write('  (' + str(x) + ',' + '0)', font = (30))
wn.mainloop()
