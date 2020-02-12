# tính e theo công thức: e = 1+ 1/1! + 1/2! + ... + 1/n!

def factorial(n):
  if (n==0) or (n==1) :
    return 1
  else: 
    return n*factorial(n-1)
def estimate_e(n):
  if n==0:
    return 1
  elif n==1:
    return 2
  else:
    return 1/factorial(n) + estimate_e(n-1)
print(estimate_e(10))
