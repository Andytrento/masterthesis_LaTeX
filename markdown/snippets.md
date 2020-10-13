```python
f,ax=plt.subplots(1,2,figsize=(18,8))
data['neighbourhood_group'].value_counts().plot.pie(explode=[0,0.05,0,0,0],autopct='%1.1f%%',ax=ax[0],shadow=True)
ax[0].set_title('Share of Neighborhood')
ax[0].set_ylabel('Neighborhood Share')
sns.countplot('neighbourhood_group',data=data,ax=ax[1],order=data['neighbourhood_group'].value_counts().index)
ax[1].set_title('Share of Neighborhood')
plt.show()
```





Situated on [one of the world's largest natural harbors](https://en.wikipedia.org/wiki/New_York_Harbor), New York City is composed of five [boroughs](https://en.wikipedia.org/wiki/Boroughs_of_New_York_City), each of which is a [county of the State of New York](https://en.wikipedia.org/wiki/List_of_counties_in_New_York). The five boroughs—[Brooklyn](https://en.wikipedia.org/wiki/Brooklyn), [Queens](https://en.wikipedia.org/wiki/Queens), [Manhattan](https://en.wikipedia.org/wiki/Manhattan), [the Bronx](https://en.wikipedia.org/wiki/The_Bronx), and [Staten Island](https://en.wikipedia.org/wiki/Staten_Island)—were consolidated into a single city in 1898.[[17\]](https://en.wikipedia.org/wiki/New_York_City#cite_note-17) 