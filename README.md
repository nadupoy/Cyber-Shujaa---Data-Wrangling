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

***N/B: I later on opted to leave it in as it may come in handy in the data analysis stage i.e. in Tableau dashboards when accessing a detailed view of an item.***

**2. Changing a commit message in Git**

Changing the most recent commit message in `Git` is done using the commands:

  ```bash
    git commit --amend -m "Your new, corrected commit message"

    git push --force-with-lease origin <branch-name>
  ```

  Amending creates a new commit with a different ID, force pushing overwrites the 
  history on the remote repository.

  `--force-with-lease` is safer than `--force` because it checks if someone else 
  has pushed to the branch in the meantime, preventing accidentally overwriting 
  their work.

**3. Changing multiple `DataFrame` columns `dtype`**

```python
  netflix_titles = netflix_titles.astype(
    {
      "type": "category",
      "country": "category",
      "rating": "category",
      "listed_in": "category",
    }
  )
```

**4. Converting a column in a `DataFrame` to an ordered categorical type with custom ordering**

This was applicable in the `netflix_titles["rating"]` column:

```python
  from pandas.api.types import CategoricalDtype

  rating_categories = CategoricalDtype(
    categories=["G", "TV-Y", "TV-G", "TV-Y7", "TV-Y7-FV", "PG", "TV-PG", "PG-13", "TV-14", "R", "TV-MA", "NC-17", "NR", "UR"], ordered=True
  )

  netflix_titles["rating"].astype(rating_categories)
```

**5. Selecting a row using a specified value/values from a column**

```python
  netflix_titles[netflix_titles["rating"] == "66 min"]

  netflix_titles[netflix_titles["rating"] == "74 min"]

  netflix_titles[netflix_titles["rating"] == "84 min"]
```

**6. Selecting a row using a specified index**

```python
  netflix_titles.iloc[[5813]]
```

**7. Accessing & changing a value in a column**

```python
  netflix_titles.at[5813, "duration"] = "66 min"
  netflix_titles.at[5813, "rating"] = "UR"
```

**8. `object` to `datetime64[ns]` `dtype` conversion**

This was applicable in the `netflix_titles["date_added"]` columns e.g *September 16, 2016* 
to *2016-09-16*:

```python
  netflix_titles["date_added"] = netflix_titles["date_added"].str.lstrip()
  netflix_titles["date_added"] = pd.to_datetime(netflix_titles["date_added"], dayfirst=True, format="%B %d, %Y")
```

**9. Dropping rows with null values in a specified column in the `DataFrame`**

Given the small number of null values in the `netflix_titles["rating"]` and 
`netflix_titles["date_added"]` columns — 4 and 10 respectively — relative to the 
size of the `DataFrame`, I opted to drop their respective rows.

```python
  netflix_titles.dropna(subset=["rating"], inplace=True)
  netflix_titles.dropna(subset=["date_added"], inplace=True)
```

**10. Filling null values in categorical `dtypes`**

```python
  # add "Unknown" to the list of valid categories in the netflix_titles["country"] column:
  netflix_titles["country"] = netflix_titles["country"].cat.add_categories("Unknown")

  values = {
    "director": "Unknown",
    "cast": "Unknown",
    "country": "Unknown"
  }
  netflix_titles.fillna(value=values, inplace=True)
```

### Continued development 🌱

- `DataFrame` manipulation in `Pandas` 🐼

### Useful resources 📚

- Column selection, addition and deletion in [`Pandas`](https://pandas.pydata.org/docs/user_guide/dsintro.html#column-selection-addition-deletion)

- Changing a commit message in [`Git`](https://docs.github.com/en/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/changing-a-commit-message)

- `Pandas` [API reference](https://pandas.pydata.org/docs/reference/index.html)

## 🧑🏽‍💻 Author

- LinkedIn - [Grace Sampao](https://www.linkedin.com/in/grace-sampao)
- GitHub - [@nadupoy](https://github.com/nadupoy)
- X (formerly Twitter) - [@grace_sampao](https://x.com/grace_sampao)
- [Blog](https://nadupoy.github.io/)
