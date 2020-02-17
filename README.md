#handle data

file = open('Iris1.txt','r')
lines = file.readlines()
data = []
#data handle
for i in range(1,151):
  string = lines[i].split(',')
  sepal_length = float(string[1].strip())
  sepal_width  = float(string[2].strip())
  pedal_length = float(string[3].strip())
  pedal_width  = float(string[4].strip())
  
  species = 0
  if string[5].strip() == 'Iris-versicolor':
    species = 1
  elif string[5].strip() == 'Iris-virginica':
    species = 2
  data.append([sepal_length,sepal_width,pedal_length,pedal_width,species])
file.close()

print(data[0])
print(data[50])  
print(data[100])

# create 4 column characteristic
sepal__length = []    
sepal__width = []
depal__length = []
depal__width = []

for j in range(4):
  for i in range(150):
    if j==0:
      sepal__length.append(data[i][j])
    elif j == 1:
      sepal__width.append(data[i][j])
    elif j == 2:
      depal__length.append(data[i][j])
    else:
      depal__width.append(data[i][j])
###
def calculate_mean(data):
  s = sum(data)
  n = len(data)
  return s/n
###
def calculate_standard_deviation(data):
  mean = calculate_mean(data)
  n = len(data)
  squared_diff = []
  for i in range(n):
    squared_diff.append((data[i]-mean)**2)
  variance = sum(squared_diff)/n
  return variance**0.5
###    
print(min(sepal__length))
print(max(sepal__length))
print(calculate_mean(sepal__length))
print(calculate_standard_deviation(sepal__length))
