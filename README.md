### tìm số, mà xuất hiện nhiều nhất trong list -> số 5

from collections import Counter
data = [1,2,3,4,5,5,5,5,1,1,2,]
def calculate_mode(data):
   c = Counter(data)
   mode = c.most_common(1)
   return mode[0][0]
print(calculate_mode(data))
