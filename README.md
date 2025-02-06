# datafun-04-eda
Create Repo in Github
Clone the Repository (to VS)
Navigate to the Project Folder #  cd -datafun-04-eda
add gitignore and requirements
Set Up a Virtual Environment  # py -m venv venv
Activate the Virtual Environment # venv\Scripts\activate
Dependencies # pip install --upgrade pip setuptools wheel  # pip install -r requirements.txt
Commit # git add .  # git commit -m "Updated project setup"   # git push origin main
Create Notebook # VS Code, go to File → New File → save it as nameofyournotebook.ipynb
set up interpreter & kernal # To select a kernel (Python environment) for your notebook in Visual Studio Code, click on the Select Kernel name in the top-right corner of the notebook interface and choose the desired kernel from the dropdown menu. Follow suggestions to install recommended extensions. Once installed, click Select Kernel / Python Environments and choose the Recommended .venv option
Commit # git add .  # git commit -m "Updated project setup"   # git push origin main


Open Jupyter Notebook.
If you're in VS Code or Anaconda, launch Jupyter from there.

Create Your Title.
Add a new Markdown cell.
 
Section for Imports.
Add a Markdown cell:

## 1. Imports
Add a code cell below it and type:python

import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from matplotlib.axes import Axes

Add a Markdown Cell:
## 2. Load Data

Add a Code Cell to Load the Iris Dataset:python

iris_df = sns.load_dataset('iris')  # Load dataset
iris_df.columns                     # List column names
iris_df.head()                      # View first few rows

Add a Markdown Cell
## 3. Initial Data Inspection

Add a Code Cell to Explore the Data: python

iris_df.head(10)       # Show first 10 rows
iris_df.shape          # Get (rows, columns)
iris_df.dtypes         # Data types of each column
iris_df.info()         # Summary of data

Add a Markdown Cell:
## 4. Initial Descriptive Statistics

Add a Code Cell:python

iris_df.describe()  # Summary stats like mean, std, min, max

Add a Markdown Cell:
## 5. Initial Data Distribution for Numerical Columns

Add a Code Cell for Histograms: python

iris_df['sepal_length'].hist()  # Histogram for one column
iris_df.hist()                  # Histograms for all numerical columns
plt.show()                      # Show plots
Document Observations (Markdown Cell):


Add a Markdown Cell:
# 6. Initial Data Distribution for Categorical Columns

Add a Code Cell:python
# Count of each species
iris_df['species'].value_counts()

# Loop for all categorical columns
for col in iris_df.select_dtypes(include=['object', 'category']).columns:
    sns.countplot(x=col, data=iris_df)
    plt.title(f'Distribution of {col}')
    plt.show()
Document Observations (Markdown Cell):


## 7. Initial Data Transformation and Feature Engineering
Add a Code python cell

# Rename column
iris_df.rename(columns={'sepal_length': 'Sepal Length'}, inplace=True)

# Create a new feature 
iris_df['Sepal Area'] = iris_df['Sepal Length'] * iris_df['sepal_width']

Add a Markdown Cell:
## 8. Initial Visualizations

Add python code cell 

  sns.pairplot(iris_df, hue='species')  # Relationships between features
  plt.show()

Add Code forpython
  scatter_plt = sns.scatterplot(
      data=iris_df, x="Sepal Length", y="Sepal Area", hue="species"
)
  scatter_plt.set_xlabel("Sepal Length (mm)")
  scatter_plt.set_ylabel("Sepal Area (mm²)")
  scatter_plt.set_title("Iris Sepal Length vs. Sepal Area (by Species)")
  plt.show()
Document Observations (Markdown Cell):


## 9. Initial Insights
Summarize:

Highlight key trends, patterns, and interesting findings from the data.
