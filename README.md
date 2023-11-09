import sys
import matplotlib
matplotlib.use('Agg')

import pandas as pd
import matplotlib.pyplot as plt
from scipy.optimize import curve_fit
import numpy as np

full_health_data = pd.read_csv("data.csv", header=0, sep=",")

x = full_health_data["Average_Pulse"]
y = full_health_data["Calorie_Burnage"]

def polynomial_func(x, a, b, c):
    return a * x + b * x + c


params, covariance = curve_fit(polynomial_func, x, y)

a, b, c = params

predicted_values = polynomial_func(x, a, b, c)

plt.scatter(x, y)
plt.plot(x, predicted_values)
plt.ylim(ymin=0, ymax=2000)
plt.xlim(xmin=0, xmax=200)
plt.xlabel("Average_Pulse")
plt.ylabel("Calorie_Burnage")
plt.show()

plt.savefig(sys.stdout.buffer)
sys.stdout.flush()




Array = [2000, 2005, 2010, 2015, 2020, 2025, 2030, 2035, 2040, 2045]
print(Array)



import pandas as pd
d = {'Кітап аты': ['Абай жолы','Бақытсыз жамал','Кемел адам','Ұлпан','Оян қазақ'], 'Кітап саны': [5, 8, 5, 4, 6], 'Шығарылған жылы': [1942, 1910, 2021, 1928, 1909], 'Бөлім саны': [4, 1, 2, 1, 1]}
df = pd.DataFrame(data=d)
print(df)



import numpy as np
import pandas as pd
danceability = [89, 47, 65, 88, 50, 105, 15, 32, 69, 57]
print (max(danceability))
print (min(danceability))
print(np.mean(danceability))


import pandas as pd

health_data = pd.read_csv("data.csv", header=0, sep=",")

health_data.dropna(axis=0,inplace=True)

print(health_data)
