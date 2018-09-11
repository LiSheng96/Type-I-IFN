# Type-I-IFN
import matplotlib.pyplot as plt
import numpy as np

# A549 after 1000U/ml IFN treatment 0h data

all_data = [([1.02,0.79,1.23]),([1.22,0.80,1.02]),([1.90,0.99,0.53]),([1.02,1.62,0.60])]
print (all_data)
labels = ['ISG54', 'ITIH5 all', 'ITIH5 v2', 'ITIH5 v1v3']

fig, ax = plt.subplots()

# rectangular box plot
bplot1 = ax.boxplot(all_data,
                         vert=True,  # vertical box alignment
                         patch_artist=True,  # fill with color
                         labels=labels)  # will be used to label x-ticks
ax.set_title('A549 after 1000U/ml IFN treatment 0h')


# fill with colors
colors = ['pink', 'lightblue', 'lightgreen']

for patch, color in zip(bplot1['boxes'], colors):
        patch.set_facecolor(color)

# adding horizontal grid lines

ax.yaxis.grid(True)
ax.set_xlabel('Gene')
ax.set_ylabel('Fold change')

plt.show()
