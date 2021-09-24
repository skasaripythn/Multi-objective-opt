# Multi-objective-opt
# max 224000x1 + 152000x2 + 170000x3 + 210000x4 + 292000x5
# min 476000x1 + 468000x2 + 450000x3 + 410000x4 + 468000x5
# min 200000x1 + 180000x2 + 180000x3 + 180000x4 + 240000x5
# 2x1+2x2+2x3+2x4+2x5<=600
# 2x1+2x2+2x3+2x4+2x5>=330
# 2x1+2x2+1.4x3+2.50x5<=540
# 0.50x1 + 0.50x2 + 0.30x3 + 0.2x4 + 0.30x5<=120
# 14x1 + 10x2 + 8x3 >=1836
# 2x5<=128
# 2x1+2x2+2x3+2x4+2x5<=604
# 8x1 + 7x2 + 6x3 + 6x4 + 6,5x5<=2400
# 2x1<=100
# 2x2<=114
# 2x3<=132
# 2x4<=132
# 2x5<=122
# 2x1>=70
# 2x2>=50
# 2x3>=60
# 2x4>=80
# 2x5>=60

import pulp
linearProblem = pulp.LpProblem("Maximizing for first objective",pulp.LpMaximize)

x1 = pulp.LpVariable("x1",lowBound = 0)
x2 = pulp.LpVariable("x2",lowBound = 0)
x3 = pulp.LpVariable("x3",lowBound = 0)
x4 = pulp.LpVariable("x4",lowBound = 0)
x5 = pulp.LpVariable("x5",lowBound = 0)

linearProblem += 224000*x1 + 152000*x2 + 170000*x3 + 210000*x4 + 292000*x5

linearProblem +=2*x1 + 2*x2 + 2*x3 + 2*x4 + 2*x5 <= 600
linearProblem += 2*x1 + 2*x2 + 2*x3 + 2*x4+ 2*x5 >= 330
linearProblem += 0.50*x1 + 0.50*x2 + 0.30*x3 + 0.2*x4 + 0.30*x5 <= 120
linearProblem += 14*x1 + 10*x2 + 8*x3 >= 1836
linearProblem += 2*x5 <= 128
linearProblem += 2*x1 + 2*x2 + 2*x3 + 2*x4 + 2*x5 <= 604
linearProblem += 8*x1 + 7*x2 + 6*x3 + 6*x4 + 6.50*x5 <= 2400
linearProblem += 2*x1 <= 100
linearProblem += 2*x2 <= 114
linearProblem +=2* x3 <= 132
linearProblem += 2*x4 <= 132
linearProblem += 2*x5 <= 122
linearProblem += 2*x1 >= 70
linearProblem += 2*x2 >= 50
linearProblem += 2*x3 >= 60
linearProblem += 2*x4 >= 80
linearProblem += 2*x5 >= 60

solution = linearProblem.solve()
print (str(pulp.LpStatus [solution])+" ; max value = "+str (pulp.value(linearProblem.objective))+
    " ; x1_opt = "+str(pulp.value(x1))+
    " ; x2_opt = "+str(pulp.value(x2))+
    " ; x3_opt = "+str(pulp.value(x3))+
    " ; x4_opt = "+str(pulp.value(x4))+
    " ; x5_opt = "+str(pulp.value(x5)))

linearProblem = pulp.LpProblem("Minimizing for 2th objective",pulp.LpMinimize)

x1 = pulp.LpVariable("x1",lowBound = 0)
x2 = pulp.LpVariable("x2",lowBound = 0)
x3 = pulp.LpVariable("x3",lowBound = 0)
x4 = pulp.LpVariable("x4",lowBound = 0)
x5 = pulp.LpVariable("x5",lowBound = 0)

linearProblem += 476000*x1 + 468000*x2 + 450000*x3 + 410000*x4 + 468000*x5

linearProblem +=2*x1 + 2*x2 + 2*x3 + 2*x4 + 2*x5 <= 600
linearProblem += 2*x1 + 2*x2 + 2*x3 + 2*x4+ 2*x5 >= 330
linearProblem += 0.50*x1 + 0.50*x2 + 0.30*x3 + 0.2*x4 + 0.30*x5 <= 120
linearProblem += 14*x1 + 10*x2 + 8*x3 >= 1836
linearProblem += 2*x5 <= 128
linearProblem += 2*x1 + 2*x2 + 2*x3 + 2*x4 + 2*x5 <= 604
linearProblem += 8*x1 + 7*x2 + 6*x3 + 6*x4 + 6.50*x5 <= 2400
linearProblem += 2*x1 <= 100
linearProblem += 2*x2 <= 114
linearProblem +=2* x3 <= 132
linearProblem += 2*x4 <= 132
linearProblem += 2*x5 <= 122
linearProblem += 2*x1 >= 70
linearProblem += 2*x2 >= 50
linearProblem += 2*x3 >= 60
linearProblem += 2*x4 >= 80
linearProblem += 2*x5 >= 60
linearProblem += 224000*x1 + 152000*x2 + 170000*x3 + 210000*x4 + 292000*x5 >= 62756000

solution = linearProblem.solve()
print (str(pulp.LpStatus [solution])+" ; min value = "+str (pulp.value(linearProblem.objective))+
    " ; x1_opt = "+str(pulp.value(x1))+
    " ; x2_opt = "+str(pulp.value(x2))+
    " ; x3_opt = "+str(pulp.value(x3))+
    " ; x4_opt = "+str(pulp.value(x4))+
    " ; x5_opt = "+str(pulp.value(x5)))

linearProblem = pulp.LpProblem("Minimizing for 3th objective",pulp.LpMinimize)

x1 = pulp.LpVariable("x1",lowBound = 0)
x2 = pulp.LpVariable("x2",lowBound = 0)
x3 = pulp.LpVariable("x3",lowBound = 0)
x4 = pulp.LpVariable("x4",lowBound = 0)
x5 = pulp.LpVariable("x5",lowBound = 0)

linearProblem += 200000*x1 + 180000*x2 + 180000*x3 + 180000*x4 + 250000*x5

linearProblem +=2*x1 + 2*x2 + 2*x3 + 2*x4 + 2*x5 <= 600
linearProblem += 2*x1 + 2*x2 + 2*x3 + 2*x4+ 2*x5 >= 330
linearProblem += 0.50*x1 + 0.50*x2 + 0.30*x3 + 0.2*x4 + 0.30*x5 <= 120
linearProblem += 14*x1 + 10*x2 + 8*x3 >= 1836
linearProblem += 2*x5 <= 128
linearProblem += 2*x1 + 2*x2 + 2*x3 + 2*x4 + 2*x5 <= 604
linearProblem += 8*x1 + 7*x2 + 6*x3 + 6*x4 + 6.50*x5 <= 2400
linearProblem += 2*x1 <= 100
linearProblem += 2*x2 <= 114
linearProblem +=2* x3 <= 132
linearProblem += 2*x4 <= 132
linearProblem += 2*x5 <= 122
linearProblem += 2*x1 >= 70
linearProblem += 2*x2 >= 50
linearProblem += 2*x3 >= 60
linearProblem += 2*x4 >= 80
linearProblem += 2*x5 >= 60
linearProblem += 224000*x1 + 152000*x2 + 170000*x3 + 210000*x4 + 292000*x5 >= 62756000
linearProblem += 476000*x1 + 468000*x2 + 450000*x3 + 410000*x4 + 468000*x5 >= 136004400.0

solution = linearProblem.solve()
print (str(pulp.LpStatus [solution])+" ; min value = "+str (pulp.value(linearProblem.objective))+
    " ; x1_opt = "+str(pulp.value(x1))+
    " ; x2_opt = "+str(pulp.value(x2))+
    " ; x3_opt = "+str(pulp.value(x3))+
    " ; x4_opt = "+str(pulp.value(x4))+
    " ; x5_opt = "+str(pulp.value(x5)))

