# 🕸️ Cyber Shujaa - Data Wrangling 🚀

This is my updated solution to the week 2 assignment in the Cyber Shujaa program 
for the **Data and AI Specialist** track.

## 🧭 Table of Contents

- [🌟 Overview](#🌟-overview)
  - [The assignment 🎯](#the-assignment-🎯)
  - [Links 🔗](#links-🔗)
- [🛠️ My process](#🛠️-my-process)
  - [Built with 🧱](#built-with-🧱)
  - [What I learned 🧠](#what-i-learned-🧠)
  - [Continued development 🌱](#continued-development-🌱)
  - [Useful resources 📚](#useful-resources-📚)
- [🧑🏽‍💻 Author](#🧑🏽‍💻-author)

## 🌟 Overview

### The assignment 🎯

The purpose of the assignment was to develop hands-on experience wrangling data 
using a Kaggle dataset and publishing the work on Kaggle.

We were required to practice data wrangling concepts to clean up the 
[Netflix dataset](https://www.kaggle.com/datasets/shivamb/netflix-shows).

The objectives of the assignment were to:
  1. **Load** the **Netflix dataset** from a `.csv` file and **explore its struture** 
  using `Pandas`. 🐼
  2. Perform **data discovery** to assess **data types**, **missing values** and 
  **quality issues**. 🧐
  3. **Clean** the dataset by handling **duplicates**, **missing values** and 
  **formatting inconsistencies**. ✨
  4. **Transform** and **enrich** the dataset using techniques like **filtering**, 
  **sorting**, **grouping** and **feature extraction**. ⚙️
  5. **Validate** the final dataset by checking **consistecy**, **completeness** 
  and **logical accuracy**. ✅
  6. **Export** the final cleaned dataset to a `.csv` file ready for **analysis** 
  or **visualization**. 💾

### Links 🔗

- [Kaggle](https://www.kaggle.com/code/gracesampao/grace-sampao-cs-da02-25057) 
assignment submission

## 🛠️ My process

### Built with 🧱

- **[`Python`](https://www.python.org)** 🐍
- **[`Pandas`](https://pandas.pydata.org/docs/index.html)** `Python` library used 
for working with datasets with functions for cleaning, exploring and manipulating 
data 🐼
- **[Visual Studio Code](https://code.visualstudio.com/)** open source code editor 💻
- **[Jupyter Notebook](https://jupyter.org/)** web application for creating and 
sharing computational documents 📓

### What I learned 🧠

**1. Removing columns from a `DataFrame`**

I didn't see the relevance of the `description` column for data analysis. Therefore
I opted to delete it using `pop()` and not `del`, just in case a need arises for it.

```python
  description_column = netflix_titles.pop("description")
```

### Continued development 🌱

### Useful resources 📚

- Column selection, addition and deletion in [`Pandas`](https://pandas.pydata.org/docs/user_guide/dsintro.html#column-selection-addition-deletion)

## 🧑🏽‍💻 Author

- LinkedIn - [Grace Sampao](https://www.linkedin.com/in/grace-sampao)
- GitHub - [@nadupoy](https://github.com/nadupoy)
- X (formerly Twitter) - [@grace_sampao](https://x.com/grace_sampao)
- [Blog](https://nadupoy.github.io/)
