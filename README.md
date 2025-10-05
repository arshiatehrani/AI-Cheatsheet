# Dimension vs. Feature: The Distinction

***

The difference between **dimension** and **feature** is mainly one of context and level of abstraction, but in the context of a dataset, they are often used to refer to the same thing.

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

***

# Independent Component Analysis (ICA) Algorithm

**Independent Component Analysis (ICA)** is a computational method used for **Blind Source Separation (BSS)**. Its primary goal is to take a mixed signal—like a recording from multiple microphones in a noisy room—and decompose it into its original, statistically **independent source signals** without knowing the mixing process.

The "blind" aspect means you don't have any prior information about the sources or how they were mixed.

### 1. The Mixing Model

ICA assumes that the observed data is a linear mixture of unobserved source signals.

The model is:
$$\mathbf{X} = \mathbf{A}\mathbf{S}$$

Where:
* $\mathbf{X}$ is the **Observed Data Matrix** (the mixed signals, e.g., the microphone recordings).
* $\mathbf{S}$ is the **Source Matrix** (the unobserved, independent source signals, e.g., the individual voices).
* $\mathbf{A}$ is the unknown **Mixing Matrix** (how the sources were linearly combined to create the observed signals).

The ICA algorithm's task is to find a **de-mixing matrix** $\mathbf{W}$ such that when applied to the observed data $\mathbf{X}$, it recovers the original sources $\mathbf{S}$:
$$\mathbf{S} \approx \mathbf{W}\mathbf{X}$$

### 2. ICA vs. PCA: The Core Difference

This is the most critical distinction in understanding ICA:

* **PCA** aims to find directions (Principal Components) that **maximize the variance** and remove **correlation** (second-order statistical dependence). The components are uncorrelated (orthogonal), but not necessarily fully independent.
* **ICA** aims to find components that **maximize statistical independence** (higher-order statistical dependence). The components are not just uncorrelated, they are as independent as possible, which is a much stronger condition.


### 3. Main Issues and Characteristics
* **Blind Source Separation (BSS):** It is called "blind" because the mixing matrix $\mathbf{A}$ and the source matrix $\mathbf{S}$ are both unknown.
* **Iterative:** Computing ICA is an **optimization problem** and is typically **computationally heavy** as it requires iterative methods to optimize the de-mixing matrix $\mathbf{W}$.
* **Non-Perfect:** The separation is "never perfect" and may contain residues.
* **Order Ambiguity:** The order of the resulting independent components is not determined (e.g., you get separated Source 1 and Source 2, but you don't know which is which without external labeling).

***

# Clarifying the Conditions for ICA to Work

Three critical conditions for ICA to work:

### Condition 1: Number of Observers $\ge$ Number of Sources
$$\mathbf{N} \ge \mathbf{M}$$

* **Meaning:** The number of sensors ($\mathbf{N}$, e.g., microphones, rows in your observed data) must be greater than or equal to the number of independent sources ($\mathbf{M}$, e.g., people speaking).
* **Why:** You need at least as many "views" of the mixture as there are sources to be able to mathematically untangle them. If you only have one microphone (N=1) and two people speaking (M=2), the problem is generally unsolvable, as you don't have enough information to isolate the two voices.

### Condition 2: The Different Sources Must Be Independent
**This is the most crucial and confusing condition.**

* **Meaning:** The original source signals ($\mathbf{S}$) must be **statistically independent** of each other.
* **What this *really* means:** The value of one source at any time must not provide any information about the value of any other source at the same time. The sources must be independent in their *statistical distribution* (not just uncorrelated like in PCA).
    * **Uncorrelated (PCA):** This means the linear relationship is zero ($\text{Covariance} = 0$).
    * **Independent (ICA):** This means that the entire joint probability distribution is separable (i.e., $p(S_1, S_2) = p(S_1) p(S_2)$).
* **The Second-Level Confusion (The "Same Melody" Question):**
    * You asked: "They can't play the same melody? They can't play the same melody together?"
    * **The answer is NO, they cannot be identical or copies of each other.** If Source 1 and Source 2 are identical (e.g., two people speaking the *exact same words* in the *exact same pitch* and *exact same time*), then the sources are **linearly dependent** and $\mathbf{S}_1$ provides complete information about $\mathbf{S}_2$. ICA cannot separate sources that are copies or very close to being copies of each other, because they are not truly independent. This is also called the **rank condition** in linear algebra—the sources matrix $\mathbf{S}$ must have full rank.

### Condition 3: The Source Distribution Must Be Non-Gaussian (Non-Normal)

* **Meaning:** At most one source can have a **Gaussian (Normal) distribution**.
* **Why (The Limitation of the Covariance Matrix):** The covariance matrix (used in PCA and as a pre-processing step for ICA) only captures second-order statistics (variance and correlation). A **Gaussian distribution** is *completely* defined by its mean ($\mu$) and variance ($\sigma^2$), which are second-order statistics. If a source is Gaussian, all its higher-order information (like skewness and kurtosis, which ICA uses) is zero or useless.
* **The ICA Insight:** ICA works by exploiting the **non-Gaussianity** of the sources. It searches for a projection that maximizes the non-Gaussianity of the resulting components (sources). Since real-world signals like speech and music are typically highly non-Gaussian, ICA can effectively separate them.

***

# Discriminative vs Generative ML Models

The key difference between **discriminative** and **generative** models in machine learning lies in what they learn and what they're primarily used for:

* **Discriminative Models** focus on **drawing boundaries** to separate different classes of data. Their goal is to accurately predict the label ($Y$) given the input features ($X$).
* **Generative Models** focus on **modeling the distribution** of the data. Their goal is to understand how the data ($X$) was generated, which allows them to generate new, synthetic data samples.

***

## Discriminative Models: Drawing Boundaries

Discriminative models are primarily used for **classification** and **prediction**. They learn a **direct mapping** from the input features to the output class.

### How They Work

1.  **Objective:** To find the optimal **decision boundary** or **decision surface** that separates the data points belonging to different classes. They focus only on the aspects of the data that are most useful for distinguishing one class from another.
2.  **Probability:** They model the **conditional probability** $P(Y|X)$, which is the probability of the class label ($Y$) given the input features ($X$). They don't need to understand the underlying structure of each class, only the separation between them.
3.  **Analogy:** Imagine separating apples and oranges. A discriminative model would just look for the best line or curve to draw between the two groups. It only cares about the separation line, not the color, shape, or weight distribution of all the apples and oranges individually.
4.  **Examples:** **Logistic Regression**, **Support Vector Machines (SVM)**, **Decision Trees**, and most traditional **Neural Networks (like CNNs for image classification)**.
5.  **Use Cases:**
    * **Image Classification:** Is this a cat or a dog?
    * **Spam Detection:** Is this email spam or not spam?
    * **Fraud Detection:** Is this financial transaction legitimate or fraudulent?



***

## Generative Models: Modeling Data Distribution

Generative models are used for **data generation**, **density estimation**, and sometimes **classification** (indirectly). They seek to learn the full statistical structure of the data.

### How They Work

1.  **Objective:** To learn the **underlying probability distribution** of the data. This means understanding how likely it is to observe any given sample.
2.  **Probability:** They model the **joint probability** $P(X, Y)$, which is the probability of the features ($X$) and the label ($Y$) occurring together, or just $P(X)$ if there are no labels (unsupervised). By knowing the joint probability, they can also derive the conditional probability $P(Y|X)$ for classification (via **Bayes' theorem**), or the probability of the data itself.
3.  **Analogy:** To separate apples and oranges, a generative model would first learn everything about the "apple category" (e.g., their typical size, color distribution, and shape) and everything about the "orange category." Once it knows how to *generate* a convincing apple or orange, it can classify a new fruit by seeing which category it is more likely to have been generated from.
4.  **Examples:** **Generative Adversarial Networks (GANs)**, **Variational Autoencoders (VAEs)**, **Naïve Bayes**, **Hidden Markov Models**, and large language models like **GPT (Generative Pre-trained Transformer)**.
5.  **Use Cases:**
    * **Creating New Data:** Generating realistic images, deepfake videos, music, or text.
    * **Data Augmentation:** Creating synthetic data to train other models.
    * **Anomaly Detection:** Identifying an outlier because it falls into a region of very low probability in the learned data distribution.



***

## Summary of Core Differences

| Feature | Discriminative Models | Generative Models |
| :--- | :--- | :--- |
| **Primary Goal** | Classification and prediction. | Data generation, density estimation. |
| **Probability Modeled** | Conditional Probability **$P(Y|X)$** (Label given data). | Joint Probability **$P(X, Y)$** (Data and Label occurring together). |
| **What they Learn** | The **boundary** between classes. | The **distribution** of the data within each class. |
| **Main Task** | To **discriminate** between classes. | To **generate** new data samples. |
| **Complexity** | Generally simpler to train and computationally lighter. | Often more complex, data-intensive, and harder to train (e.g., GANs). |
| **Core Question**| "What is the most likely label for this input?" | "How did this data come to be, and what is the data's underlying structure?" |

***

# F1 Score (Standard - Macro - Micro)
You're asking about the difference between the standard **F1-Score** (which you've been working with) and its two variations for multi-class problems: **Micro F1** and **Macro F1**. This distinction is critical when evaluating models on datasets with **imbalanced classes**.

## 1. F1-Score (The Standard)

The standard F1-Score, or often just "F1," is calculated for a **single, specific target class** (the positive class), as you saw with the "Cat" example.

$$F1 = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}} = \frac{2 \times \text{TP}}{2\text{TP} + \text{FP} + \text{FN}}$$

* **Purpose:** It gives a balanced measure of a model's performance on that single class. It's often used when that class is the minority class or the class of interest (e.g., Cat, Fraud, Disease).
* **Limitation:** It only tells you how well the model did for *that one class*. If you have 10 classes, you'd get 10 different F1-Scores. You need a way to summarize this performance across *all* classes. That's where Micro and Macro F1 come in.

***

## 2. Macro F1-Score (Averaging Metrics)

The **Macro F1** is calculated by treating all classes **equally**, regardless of how many instances belong to each class.

### Calculation Steps:

1.  **Calculate F1-Score for *Each* Class:** You compute the standard F1-Score individually for every single class (e.g., F1-Cat, F1-Apple, F1-Banana, etc.).
2.  **Average the F1-Scores:** You take the unweighted average of all those individual F1-Scores.

$$\text{Macro F1} = \frac{1}{\text{N}_{\text{classes}}} \sum_{i=1}^{\text{N}_{\text{classes}}} \text{F1}_{\text{i}}$$

### Key Characteristics:

* **Sensitivity to Imbalance:** It is **highly sensitive to performance on minority classes**. If a model performs poorly on a small class (e.g., Cat), the Macro F1 score will drop significantly, even if the model performs perfectly on the large classes (e.g., Apples).
* **When to Use:** Use Macro F1 when you care equally about the accurate classification of every class, especially when you have an imbalanced dataset and want to ensure the model isn't ignoring the small classes.

***

## 3. Micro F1-Score (Averaging Instances)

The **Micro F1** is calculated by aggregating the True Positives, False Positives, and False Negatives across **all** classes first, and then applying the F1 formula.

### Calculation Steps:

1.  **Sum TP, FP, FN Across *All* Classes:** Sum up all the individual $\text{TP}_i$, $\text{FP}_i$, and $\text{FN}_i$ counts from every class to get $\sum \text{TP}$, $\sum \text{FP}$, and $\sum \text{FN}$.
2.  **Calculate F1 from the Total Counts:** Apply the standard F1 formula using these grand totals.

$$\text{Micro F1} = \frac{2 \times (\sum \text{TP})}{2(\sum \text{TP}) + (\sum \text{FP}) + (\sum \text{FN})}$$

### Key Characteristics:

* **Insensitivity to Imbalance:** It is **dominated by the large classes**. It essentially weights each class by its size. In a severe imbalance, Micro F1 will be very close to the overall **Accuracy**.
* **When to Use:** Use Micro F1 when you care about the classification of all individual instances equally. This metric is a good measure of overall model correctness, similar to accuracy, but is more appropriate than accuracy when comparing models because it is less prone to the "accuracy paradox."

***

## Choosing the Best Metric

The correct choice depends entirely on the problem:

| Goal | Metric | Reason |
| :--- | :--- | :--- |
| **Overall Performance** | **Micro F1** | Treats every single instance prediction equally; dominated by the largest class sizes. |
| **Fairness/Minority Class** | **Macro F1** | Treats every class equally, regardless of size; a poor score indicates major issues with small classes. |
| **Specific Focus** | **Standard F1** | Focuses only on the performance of a single, highly critical class (e.g., the "Cat" class). |

For most projects involving imbalanced classification, many practitioners recommend reporting **both** Micro F1 and Macro F1, as well as the standard F1 for the minority class, to provide a complete picture of the model's performance.