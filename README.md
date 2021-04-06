# SUMMARY-STATISTICS-Summarizing-Automobile-Evaluation-Data
Codeacademy project

import pandas as pd
import numpy as np

car_eval = pd.read_csv('car_eval_dataset.csv')
print(car_eval.head())

print(car_eval['manufacturer_country'].value_counts())
print(car_eval['manufacturer_country'].value_counts().index[4])

print(car_eval['manufacturer_country'].value_counts()/len(car_eval['manufacturer_country']))

x = car_eval['buying_cost'].unique()
print(x)

buying_cost_categories = ['low','med','high','vhigh']
car_eval['buying_cost']= pd.Categorical(car_eval['buying_cost'] ,buying_cost_categories ,ordered = True)

median_category_num=np.median(car_eval['buying_cost'].cat.codes)
print(median_category_num)

median_category = buying_cost_categories[int(median_category_num)]
print(median_category)

print(car_eval['luggage'].value_counts(normalize = True))

print(car_eval['luggage'].value_counts(dropna = False ,normalize = True))
