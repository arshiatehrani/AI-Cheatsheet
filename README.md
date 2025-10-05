The difference between **dimension** and **feature** is mainly one of context and level of abstraction, but in the context of a dataset, they are often used to refer to the same thing.

***

# Dimension vs. Feature: The Distinction

| Concept | Definition | Context |
| :--- | :--- | :--- |
| **Feature** | A single, measurable property or attribute of a phenomenon being observed. | The specific columns in your dataset like 'Age', 'Height', or 'Income'. This is a **domain-specific** term. |
| **Dimension** | The **total number of features** (columns/variables) in your dataset. | The size of the vector space where your data lives. This is a **mathematical/linear algebra** term. |

### The Overlap

In data science, the terms are frequently used interchangeably:

* **A Feature is a Dimension:** Each feature ('Age', 'Height') corresponds to an axis (or dimension) in a coordinate system. A dataset with 5 features is said to be 5-dimensional.
* **The total number of Features is the Dimension:** The *dimensionality* of the data is the count of its features.

The key conceptual difference emerges in advanced techniques like **Dimensionality Reduction** (e.g., PCA), where you reduce the *dimension* (the total number of axes) to a new, smaller set of axes, and these new axes are called **latent features** or **principal components**, which are combinations of the original features. 
***

## Columns and Rows in a Dataset

In your typical, rectangular dataset (a data table):

* **Every Column is a Feature** (or an **Attribute**). Each column represents a property being measured across all samples.
* **The Rows are Samples** (or **Observations** or **Data Points**). Each row represents a single entity (a person, a house, a transaction) with its set of feature values.

| Data Element | Role | Example |
| :--- | :--- | :--- |
| **Row** | **Sample / Observation** ($N$ rows total) | A single customer. |
| **Column** | **Feature / Attribute** ($D$ columns total) | The customer's Age. |
| **$D$** | **The Dimension** | The total count of columns/features. |

***

## Interpreting Statistical Notation ($\boldsymbol{x_i}$, $\boldsymbol{\mu}$, and $\boldsymbol{\sigma}$)

The notation in statistical and machine learning formulas can sometimes be confusing because the subscript '$i$' can refer to a sample or a feature, depending on the context of the formula.

### $x_i$: The Data Point

In general statistics and machine learning **when calculating a statistic for a single feature**, $x_i$ refers to:

| Symbol | What it Represents | Context |
| :--- | :--- | :--- |
| $\boldsymbol{x_i}$ | The **$i^{th}$ value** of a specific feature. | Used when calculating the Mean or Standard Deviation for a single feature across all samples. |

**It is a random feature for the $i^{th}$ sample.**
* If you are looking at the 'Age' feature, $x_1$ is the Age of the first sample, $x_2$ is the Age of the second sample, and so on. The index $i$ is iterating over the **samples (rows)**.

### $\mu$ (Mu) and $\sigma$ (Sigma): The Statistics

These Greek letters represent **Population Parameters** (statistics calculated over the entire theoretical population). In practice, when calculated over a dataset, they represent **Sample Statistics** (often denoted as $\bar{x}$ for mean and $s$ for standard deviation, but $\mu$ and $\sigma$ are commonly used in machine learning when treating the dataset as the entire focus).

| Symbol | Name | Meaning | What it Describes |
| :--- | :--- | :--- | :--- |
| $\boldsymbol{\mu}$ | **Mu** | The **Mean** (Average) | The central tendency of a **single feature's** values across all samples. |
| $\boldsymbol{\sigma}$ | **Sigma** | The **Standard Deviation** | The spread or variability of a **single feature's** values around its mean ($\mu$) across all samples. |

The most common formula in which you'll see these symbols together is the formula for the **Population Mean**:

$$\mu = \frac{1}{N} \sum_{i=1}^{N} x_i$$

Where:
* $N$: Total number of samples (rows).
* $\sum_{i=1}^{N}$: Summing from the first sample ($i=1$) to the last sample ($i=N$).
* $x_i$: The value of the specific feature for the $i^{th}$ sample.

***

## Example and Visualization

Imagine a simple dataset about four students with two features: **Height** and **Test Score**.

| Student (Sample $j$) | Feature 1: Height ($x_{j, 1}$) | Feature 2: Score ($x_{j, 2}$) |
| :--- | :--- | :--- |
| **1** | 170 cm | 85 |
| **2** | 175 cm | 92 |
| **3** | 180 cm | 78 |
| **4** | 165 cm | 95 |

### 1. Dimension and Features

* **Features:** Height and Score.
* **Dimension:** 2 (since there are two features).
* **Samples:** 4 (Student 1 through 4).

### 2. Statistical Notation (Calculating for 'Height')

We treat the **Height** column as our single list of values, $x$. In this case, $N=4$.

* $x_1 = 170$
* $x_2 = 175$
* $x_3 = 180$
* $x_4 = 165$

**A. Calculate $\boldsymbol{\mu}$ (Mean Height)**

$$\mu = \frac{1}{N} \sum_{i=1}^{N} x_i = \frac{1}{4} (170 + 175 + 180 + 165) = \frac{690}{4} = 172.5$$

**B. Calculate $\boldsymbol{\sigma}$ (Standard Deviation of Height)**

$$\sigma = \sqrt{\frac{1}{N} \sum_{i=1}^{N} (x_i - \mu)^2}$$

$$\sigma = \sqrt{\frac{1}{4} [ (170-172.5)^2 + (175-172.5)^2 + (180-172.5)^2 + (165-172.5)^2 ]}$$

$$\sigma = \sqrt{\frac{1}{4} [ (-2.5)^2 + (2.5)^2 + (7.5)^2 + (-7.5)^2 ]} = \sqrt{\frac{1}{4} [ 6.25 + 6.25 + 56.25 + 56.25 ]} \approx 5.59$$

### 3. The Visualization

In a 2-dimensional space (a 2D plot), your features become the axes. Each row/sample is a single point.

* The **Height** feature is the X-axis (Dimension 1).
* The **Score** feature is the Y-axis (Dimension 2).

The 4 samples are plotted as 4 points:
(170, 85), (175, 92), (180, 78), (165, 95).

In this plot:
* The dimension of the data is **2**.
* The features are the **Height axis** and the **Score axis**.


If you wanted to visualize the $\mu$ and $\sigma$ for the **Height** feature (X-axis), the $\mu=172.5$ would be a vertical line representing the average height, and the $\sigma \approx 5.59$ would show how far the points typically spread horizontally from that line.

The difference between **dimension** and **feature** is mainly one of context and level of abstraction, but in the context of a dataset, they are often used to refer to the same thing.

***

# Dimension vs. Feature: The Distinction

| Concept | Definition | Context |
| :--- | :--- | :--- |
| **Feature** | A single, measurable property or attribute of a phenomenon being observed. | The specific columns in your dataset like 'Age', 'Height', or 'Income'. This is a **domain-specific** term. |
| **Dimension** | The **total number of features** (columns/variables) in your dataset. | The size of the vector space where your data lives. This is a **mathematical/linear algebra** term. |

### The Overlap

In data science, the terms are frequently used interchangeably:

* **A Feature is a Dimension:** Each feature ('Age', 'Height') corresponds to an axis (or dimension) in a coordinate system. A dataset with 5 features is said to be 5-dimensional.
* **The total number of Features is the Dimension:** The *dimensionality* of the data is the count of its features.

The key conceptual difference emerges in advanced techniques like **Dimensionality Reduction** (e.g., PCA), where you reduce the *dimension* (the total number of axes) to a new, smaller set of axes, and these new axes are called **latent features** or **principal components**, which are combinations of the original features. 
***

## Columns and Rows in a Dataset

In your typical, rectangular dataset (a data table):

* **Every Column is a Feature** (or an **Attribute**). Each column represents a property being measured across all samples.
* **The Rows are Samples** (or **Observations** or **Data Points**). Each row represents a single entity (a person, a house, a transaction) with its set of feature values.

| Data Element | Role | Example |
| :--- | :--- | :--- |
| **Row** | **Sample / Observation** ($N$ rows total) | A single customer. |
| **Column** | **Feature / Attribute** ($D$ columns total) | The customer's Age. |
| **$D$** | **The Dimension** | The total count of columns/features. |

***

## Interpreting Statistical Notation ($\boldsymbol{x_i}$, $\boldsymbol{\mu}$, and $\boldsymbol{\sigma}$)

The notation in statistical and machine learning formulas can sometimes be confusing because the subscript '$i$' can refer to a sample or a feature, depending on the context of the formula.

### $x_i$: The Data Point

In general statistics and machine learning **when calculating a statistic for a single feature**, $x_i$ refers to:

| Symbol | What it Represents | Context |
| :--- | :--- | :--- |
| $\boldsymbol{x_i}$ | The **$i^{th}$ value** of a specific feature. | Used when calculating the Mean or Standard Deviation for a single feature across all samples. |

**It is a random feature for the $i^{th}$ sample.**
* If you are looking at the 'Age' feature, $x_1$ is the Age of the first sample, $x_2$ is the Age of the second sample, and so on. The index $i$ is iterating over the **samples (rows)**.

### $\mu$ (Mu) and $\sigma$ (Sigma): The Statistics

These Greek letters represent **Population Parameters** (statistics calculated over the entire theoretical population). In practice, when calculated over a dataset, they represent **Sample Statistics** (often denoted as $\bar{x}$ for mean and $s$ for standard deviation, but $\mu$ and $\sigma$ are commonly used in machine learning when treating the dataset as the entire focus).

| Symbol | Name | Meaning | What it Describes |
| :--- | :--- | :--- | :--- |
| $\boldsymbol{\mu}$ | **Mu** | The **Mean** (Average) | The central tendency of a **single feature's** values across all samples. |
| $\boldsymbol{\sigma}$ | **Sigma** | The **Standard Deviation** | The spread or variability of a **single feature's** values around its mean ($\mu$) across all samples. |

The most common formula in which you'll see these symbols together is the formula for the **Population Mean**:

$$\mu = \frac{1}{N} \sum_{i=1}^{N} x_i$$

Where:
* $N$: Total number of samples (rows).
* $\sum_{i=1}^{N}$: Summing from the first sample ($i=1$) to the last sample ($i=N$).
* $x_i$: The value of the specific feature for the $i^{th}$ sample.

***

## Example and Visualization

Imagine a simple dataset about four students with two features: **Height** and **Test Score**.

| Student (Sample $j$) | Feature 1: Height ($x_{j, 1}$) | Feature 2: Score ($x_{j, 2}$) |
| :--- | :--- | :--- |
| **1** | 170 cm | 85 |
| **2** | 175 cm | 92 |
| **3** | 180 cm | 78 |
| **4** | 165 cm | 95 |

### 1. Dimension and Features

* **Features:** Height and Score.
* **Dimension:** 2 (since there are two features).
* **Samples:** 4 (Student 1 through 4).

### 2. Statistical Notation (Calculating for 'Height')

We treat the **Height** column as our single list of values, $x$. In this case, $N=4$.

* $x_1 = 170$
* $x_2 = 175$
* $x_3 = 180$
* $x_4 = 165$

**A. Calculate $\boldsymbol{\mu}$ (Mean Height)**

$$\mu = \frac{1}{N} \sum_{i=1}^{N} x_i = \frac{1}{4} (170 + 175 + 180 + 165) = \frac{690}{4} = 172.5$$

**B. Calculate $\boldsymbol{\sigma}$ (Standard Deviation of Height)**

$$\sigma = \sqrt{\frac{1}{N} \sum_{i=1}^{N} (x_i - \mu)^2}$$

$$\sigma = \sqrt{\frac{1}{4} [ (170-172.5)^2 + (175-172.5)^2 + (180-172.5)^2 + (165-172.5)^2 ]}$$

$$\sigma = \sqrt{\frac{1}{4} [ (-2.5)^2 + (2.5)^2 + (7.5)^2 + (-7.5)^2 ]} = \sqrt{\frac{1}{4} [ 6.25 + 6.25 + 56.25 + 56.25 ]} \approx 5.59$$

### 3. The Visualization

In a 2-dimensional space (a 2D plot), your features become the axes. Each row/sample is a single point.

* The **Height** feature is the X-axis (Dimension 1).
* The **Score** feature is the Y-axis (Dimension 2).

The 4 samples are plotted as 4 points:
(170, 85), (175, 92), (180, 78), (165, 95).

In this plot:
* The dimension of the data is **2**.
* The features are the **Height axis** and the **Score axis**.


If you wanted to visualize the $\mu$ and $\sigma$ for the **Height** feature (X-axis), the $\mu=172.5$ would be a vertical line representing the average height, and the $\sigma \approx 5.59$ would show how far the points typically spread horizontally from that line.# AI-Cheatsheet
