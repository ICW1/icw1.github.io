---
layout: post
published: True
title: Visualisations of Lab tests
---
### 🏃 Submax Test Report (2020–2025)

#### What is a Submax Test?
A submaximal lactate test is a running test used to monitor aerobic fitness. It involves running at progressively faster speeds (e.g., every 3 minutes), with short rest periods (30s) between each stage. After each stage, a small blood sample is taken to measure blood lactate concentration.

Because you’re not running to exhaustion (unlike a VO₂max test), it’s a safer, repeatable way to track changes in fitness over time—perfect for endurance athletes.

#### What Should We Look For?
In general, better aerobic conditioning <!--more-->is reflected by:

📉 Lower lactate levels at the same speed

🏃‍♂️ Higher speed before lactate spikes sharply

🧠 Flatter curve = more efficient aerobic system

#### Visulaisation
Below is a plot which contains all the submax treadmill tests I have done since 2020. 

![an image alt text]({{ site.baseurl }}/images/submax_tests_lactate_plot.png "Lab test lactates")

#### Interpreting Results
Whilst these tests have been done in different labs by deffierent physiologists at different times of the year, we can see some trends:
* Early tests (e.g. Oct 2020) show a steeper rise in lactate at lower speeds.
* Recent tests (Feb 2024 and Jan 2025) show lower lactate at the same speeds, especially around 17–19 km/h.
* Your lactate threshold (the point where lactate starts to rise rapidly) has shifted to higher speeds over time.
* 💪 This suggests improved aerobic fitness, my body can now run faster before switching heavily into anaerobic metabolism.


### code
```
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Original data {speed_in_kmph: [blood_lactates]}
lactates = {
    13: [np.nan, np.nan, np.nan, np.nan, 0.65],
    14: [np.nan, np.nan, np.nan, np.nan, 0.65],
    15: [1.7, 1.1, 0.65, 2.09, 0.65],
    16: [1.3, 1.0, 0.65, 1.88, 1.56],
    17: [1.7, 1.2, 1.36, 2.27, 2.33],
    18: [2.8, 1.6, 1.13, 2.66, 3.50],
    19: [4.2, 2.3, 1.66, 3.45, 6.54],
    20: [6.2, 3.3, 3.75, 5.11, np.nan],
    21: [9.4, 5.1, 4.51, 7.58, np.nan],
    22: [np.nan, 7.2, 4.75, np.nan, np.nan],
    23: [np.nan, 13.92, np.nan, np.nan, np.nan],
}

# Create and reshape dataframe
df = pd.DataFrame(lactates).T
df.columns = ['oct_2020_brum', 'nov_2022_luffbra', 'dec_2023_simmies', 'feb_2024_simmies', 'jan_2025_simmies']
df.index.name = 'Speed'
df = df.reset_index()

# Melt to long format
df_long = df.melt(id_vars='Speed', var_name='Test', value_name='Lactate')

# Define colors by test recency
test_order = df.columns[1:]  # Skip 'Speed'
n_tests = len(test_order)
palette = sns.color_palette("viridis", n_tests)
test_palette = dict(zip(test_order, palette))

# Set style
sns.set(style="whitegrid")

# Plot
plt.figure(figsize=(10, 6))
sns.lineplot(data=df_long, x='Speed', y='Lactate', hue='Test', palette=test_palette, marker='o')

plt.xlim(12, 24)
plt.ylim(0, 15)
plt.xlabel('Speed (km/h)', fontsize=12)
plt.ylabel('Blood Lactate (mmol/L)', fontsize=12)
plt.title('Blood Lactate vs Speed Over Time', fontsize=14)
plt.legend(title='Test Date', bbox_to_anchor=(1.05, 1), loc='upper left')
plt.tight_layout()
plt.show()

```
