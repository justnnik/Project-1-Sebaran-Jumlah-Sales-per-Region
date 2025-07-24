# Project-1 : Sales Revenue Analysis based per Region

## 🧠 Goal

The goal of this project is to identify the factors that contribute to the sales revenue, specifically whether the discount or region.

By performing data analysis using Python, this project aims to provide valuable insights that can help movie companies make more informed decisions about:
- Which region needs attention about sales strategy,
- Which region and products are the highest sales in 2024 by (Jan-Feb),
- And how to allocate resources to maximize the chances of success.

---

## ⚙️ Setup

### Importing Necessary Libraries

```python
import pandas as pd
import numpy as np
import seaborn as sns

from scipy import stats

import matplotlib.pyplot as plt
import matplotlib.mlab as mlab
import matplotlib
plt.style.use('ggplot')
from matplotlib.pyplot import figure

%matplotlib inline
matplotlib.rcParams['figure.figsize'] = (12,8)

pd.options.mode.chained_assignment = None

### Importing Necessary Libraries

