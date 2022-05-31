import pandas as pd
import numpy as np
import matplotlib as plt
import seaborn as sns
######################################################################################################################################################################

data = data
num_cols = the required numerical columns for which correlation is required

#creating 
cor_mat = data[num_cols].corr()

#getting the traditional heat map
plt.figure(figsize=(10,6))
sns.set_theme(style="whitegrid", font_scale=1)
title_name = "Heatmap"
sns.heatmap(cor_mat, 
        xticklabels=cor_mat.columns,
        yticklabels=cor_mat.columns)
######################################################################################################################################################################

# getting the multiple bar plots of correlation for each category 

data = data
cat_col =  categorical column (in strings)
num_cols = a list of required numerical columns for which correlation is required
col_wrap = number of plots in a single row (numerical value)
x = the variable against which the correlation is needed to be shown

#corelation matrix wrt each sub category 
cor_mat = data.groupby(cat_col)[num_cols].corr().reset_index()
cor_mat.rename(columns = {'level_1':'category'}, inplace = True)
cor_mat = cor_mat[cor_var]

#ploting
plt.figure(figsize=(25,8))
sns.set_theme(style="whitegrid", font_scale=1)
title_name = "Corplot for " + cat_col
g = sns.FacetGrid(cor_mat, col = cat_col, col_wrap = col_wrap ,size=4)
g.map(sns.barplot, 'category', x, palette = sns.color_palette('bright'))

for ax in g.axes:
    for p in ax.patches:
             ax.annotate("%.2f" % p.get_height(), (p.get_x() + p.get_width() / 2., p.get_height()),
                 ha='center', va='center', fontsize=11, color='black', xytext=(0, 8),
                 textcoords='offset points')
g.fig.subplots_adjust(top=0.94) 
g.fig.suptitle(title_name.title(),fontsize = 20)
g.set_titles('{col_name}')

