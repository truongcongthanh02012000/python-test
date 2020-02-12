##tính trung vị
def calculate_median(data):
  data.sort()
  n = len(data)
  if n%2==0:
    m1 = int((n/2)-1)
    m2 = int(n/2)
    value = (data[m1]+data[m2])/2
    return value
  else:
    return data[int(n/2)]
data = [3,1,2,9,7,4,6,5,8]
median = calculate_median(data)
print(median)
  
