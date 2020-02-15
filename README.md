#He so tuong quan

import numpy as np
from PIL import Image
from io import BytesIO
import requests
#correlation coeffecient
x = [7, 18, 29, 2, 10, 9, 9]
y = [1, 6, 12, 8, 6, 21, 10]
def find_corr_x_y(x,y):
  n = len(x)
  p1 = []
  s3 = 0
  s4 = 0
  for i in range(n):
    p1.append(x[i]*y[i])
    s3 = s3 + x[i]**2
    s4 = s4 + y[i]**2
  s1 = n*sum(p1)
  s2 = sum(x)*sum(y)
  s3 = n*s3 - (sum(x))**2
  s3 = s3**0.5
  s4 = n*s4 - (sum(y))**2
  s4 = s4**0.5
  S = (s1 - s2)/(s3*s4)
  return S
#print(corr_x_y(x,y))
# load ảnh và chuyển về kiểu list
req1 = requests.get('https://www.dropbox.com/s/vfe090qo24t3v46/img1.png?raw=1')
req5 = requests.get('https://www.dropbox.com/s/wdj080tsf92a0l0/img1_scale2.png?raw=1')
req6 = requests.get('https://www.dropbox.com/s/9fr6h5y9vejyl7h/img1_scale1.png?raw=1')
image1 = Image.open(BytesIO(req1.content))
image5 = Image.open(BytesIO(req5.content))
image6 = Image.open(BytesIO(req6.content))
image1_list = np.asarray(image1).flatten().tolist()
image5_list = np.asarray(image5).flatten().tolist()
image6_list = np.asarray(image6).flatten().tolist()
# tính correlation coefficient
corr_1_5 = find_corr_x_y(image1_list, image5_list)
corr_1_6 = find_corr_x_y(image1_list, image6_list)
print('corr_1_5:', corr_1_5)
print('corr_1_6:', corr_1_6)
