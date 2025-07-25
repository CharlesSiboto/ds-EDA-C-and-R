[![Shipping files](https://github.com/neuefische/ds-eda-project-template/actions/workflows/workflow-03.yml/badge.svg?branch=main&event=workflow_dispatch)](https://github.com/neuefische/ds-eda-project-template/actions/workflows/workflow-03.yml)
# ds-project-template

Template for creating ds simple projects

## Requirements

- pyenv
- python==3.11.3
*The list of requirements is presented on the document: requirements.txt 

## Setup

One of the first steps when starting any data science project is to create a virtual environment. For this project you have to create this environment from scratch yourself. However, you should be already familiar with the commands you will need to do so. The general workflow consists of... 

* setting the python version locally to 3.11.3
* creating a virtual environment using the `venv` module
* activating your newly created environment 
* upgrading `pip` (This step is not absolutely necessary, but will save you trouble when installing some packages.)
* installing the required packages via `pip`

At the end, you want to make sure that people who are interested in your project can create an identical environment on their own computer in order to be able to run your code without running into errors. Therefore you can create a `requirements file` and add it to your repository. You can create such a file by running the following command: 

```bash
pip freeze > requirements.txt
```

*Note: In rare case such a requirements file created with `pip freeze` might not ensure that another (especially M1 chip) user can install and execute it properly. This can happen if libraries need to be compiled (e.g. SciPy). Then it also depends on environment variables and the actual system libraries.*

### Unit testing (Optional)

If you write python scripts for your data processing methods, you can also write unit tests. In order to run the tests execute in terminal:

```bash
pytest
```

This command will execute all the functions in your project that start with the word **test**.

## Set up your Environment
This repo contains a requirements.txt file with a list of all the packages and dependencies you will need.

Before you can start with plotly in Jupyter Lab you have to install node.js (if you haven't done it before).
- Check **Node version**  by run the following commands:
    ```sh
    node -v
    ```
    If you haven't installed it yet, begin at `step_1`. Otherwise, proceed to `step_2`.


### **`macOS`** type the following commands : 


- `Step_1:` Update Homebrew and install Node by following commands:
    ```sh
    brew update
    brew install node
    ```

- `Step_2:` Install the virtual environment and the required packages by following commands:

    ```BASH
    pyenv local 3.11.3
    python -m venv .venv
    source .venv/bin/activate
    pip install --upgrade pip
    pip install -r requirements.txt
    ```
### **`WindowsOS`** type the following commands :


- `Step_1:` Update Chocolatey and install Node by following commands:
    ```sh
    choco upgrade chocolatey
    choco install nodejs
    ```

- `Step_2:` Install the virtual environment and the required packages by following commands.

   For `PowerShell` CLI :

    ```PowerShell
    pyenv local 3.11.3
    python -m venv .venv
    .venv\Scripts\Activate.ps1
    python -m pip install --upgrade pip
    pip install -r requirements.txt
    ```

    For `Git-Bash` CLI :
  
    ```BASH
    pyenv local 3.11.3
    python -m venv .venv
    source .venv/Scripts/activate
    python -m pip install --upgrade pip
    pip install -r requirements.txt
    ```
 
# DS-EDA-C-AND-R
Project centered on exploratory data. Analyzing robust data using SQL, filtering the most relevant variables with the help of visualizations according to needs of the exercise. 

## EXERCISE
Use the data from King County Housing. This data set contains information about the home sales in King County (USA). You will use this information to tailor-made a set of houses for your specific client (previously chosen). In this case, the client is Jennifer Montgomery. 

You can find this database on DBeaver:

postgreg > Databases > postgreg > Schemas > eda

You can find the description of each one of the details of the houses on the document: column_names.md

By exploring the data set, create a Join for the 2 tables. Consequently, create a Query that satisfies the necessities of your customer. According to her profile, you should select which details are more important for her. This way, excluding all unnecessary data from the analysis.

Jennifer Montgomery’s profile: “High budget, wants to show off, timing within 1 month, waterfront, renovated, high grades, resell within 1 year.”

Once the query has been formulated, we will fetch the data onto python. The document “Fetching_the_data_eda.ipynb” will guide us through it. 

## FETCHING EDA DATA

The notebook “Fetching_the_data_eda.ipynb” is a guide to connect a PostgreSQL database with Python. There is the possibility to use 2 python packages, in this exercise we use “pyscopg2”. Python allows executing SQL queries and getting result into a Pandas data frame, avoiding exporting a .csv file from DBeaver. 

Using pyscopg2 we connect to the database to retrieve the desire data. For this, we write the information of the database (name, user, host, password, etc.). This notebook also includes how to store information that is not supposed to be shared (.gitignore).

As a final step, we create a .csv file representing the final details proposed on the query. The .csv file information can be found in the project folder under: EDA.csv

## VISUALIZATIONS
Once all the important data has been filtered and we have a connection to the database so we can use such data, we create visualizations the help us draw conclusions for the exercise. This step is explained in the notebook: EDA_C_and_R.ipynb.

We can create a diverse variety of charts or tables using Python Libraries: Seaborn, Plotly, Matplotlib, etc. The visualizations used are the following: 

- Heatmap: A graphical representation of data where individual values are shown as colors in a matrix.
- Boxplot: A statistical chart that shows the distribution, median, and outliers of a dataset using quartiles.
- Scatterplot: A plot that displays the relationship between two variables using points on a Cartesian plane.
- Histogram: A bar chart that shows the frequency distribution of a continuous variable by grouping values into bins.

The main point of data visualization is to obtain the correlation among the variables. It is easier for the human mind to comprehend this correlation through a graph than reading numbers through a table. The information gather will be the base to formulate the key insights that our customer needs to make an well-founded decision. 

## CONCLUSION
The finalization of this exercise comes with the list of key insights and recommend houses to buy for our client. These are also presented in the notebook: EDA_C_and_R.ipynb. 

As complementary information we also created a presentation for the client. 

The details of the entire exercise can be found in Github: 

https://github.com/CharlesSiboto/ds-EDA-C-and-R
