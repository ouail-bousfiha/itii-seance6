# itii-seance6

#EXO 1

def integrale(f, a, b, n):
    
    inte = 0
    k=a;
    while(i < b):
        l = (b-a)/n
        h = f(a + i*(b-a)/n)
        aire = l * h
        inte += aire
        i+=n
 
    return inte

#EXO 2

def integrale_precise(f, a, b, n0, prec):
    val = integrale(f, a, b, n0)
    val0 = None
    while val0 is None or abs(val - val0) / val0 > prec:
        val0 = val
        n0 += 1
        val = integrale(f, a, b, n0)
    return val, n0

integrale_precise(lambda x: x, 0.1, 1, 10, 1e-4)

#EXO 3

f = lambda x : 3*x**3 + 2*x - 1
print(integrale(f,0,10,0.001))

#EXO 4

import math
g = lambda x : math.cos(1/x)
print(integrale(g,0.1,10,0.001))
