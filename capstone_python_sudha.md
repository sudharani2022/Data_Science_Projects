# **Project on Olympic_games_dataset using Python and appropriate visualization techniques**


# **Introduction**:
   The modern Olympic Games or Olympics are leading international sports events featuring summer and winter sports competitions in which thousands of athletes from around the world participate in a variety of competitions with more than 200 nations participating.

   Here olympic games dataset gives information about the players and their basic information like name,age,country and also number of medals they have won from different years between 2000 to 2012

   The target is to analyse the players from different countries who have won different number of medals gold,silver,bronze in different years between 2000 t0 2012 

There are 10 variables in the dataset  and they can be explained as follows

**1)name** : name of the player who won any one of the medals in the olympics

**2)age** : age of the olympic players

**3)country** : country to which the player belong to

**4)date_given** : the date on which the player had won the medal 

**5)year** : the year in which the player won the medal

**6)sports** : the name of the sports conducted in olympics

**7)gold_medal** : the number of gold medals won by each player respectively

**8)silver_medal** : the number of silver medals won by each player respectively

**9)bronze_medal** : the number of bronze medals won by each player respectively

**10)Total_medal** : the number of total medals won by each player respectively


```python
#Importing necessary librarires
```


```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```


```python
#Reading the dataset which is a csv file using read_csv() function
olympic_data=pd.read_csv("/content/olympix_data_organized_with_header (1) (1).csv")
olympic_data

```





  <div id="df-2317d2e0-9036-4b56-bb25-03bf1504bb1d">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>country</th>
      <th>year</th>
      <th>Date_Given</th>
      <th>sports</th>
      <th>gold_medal</th>
      <th>silver_medal</th>
      <th>brone_medal</th>
      <th>total_medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Michael Phelps</td>
      <td>23.0</td>
      <td>United States</td>
      <td>2008</td>
      <td>8/24/2008</td>
      <td>Swimming</td>
      <td>8</td>
      <td>0</td>
      <td>0</td>
      <td>8</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Michael Phelps</td>
      <td>19.0</td>
      <td>United States</td>
      <td>2004</td>
      <td>8/29/2004</td>
      <td>Swimming</td>
      <td>6</td>
      <td>0</td>
      <td>2</td>
      <td>8</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Michael Phelps</td>
      <td>27.0</td>
      <td>United States</td>
      <td>2012</td>
      <td>08-12-2012</td>
      <td>Swimming</td>
      <td>4</td>
      <td>2</td>
      <td>0</td>
      <td>6</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Natalie Coughlin</td>
      <td>25.0</td>
      <td>United States</td>
      <td>2008</td>
      <td>8/24/2008</td>
      <td>Swimming</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>6</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Aleksey Nemov</td>
      <td>24.0</td>
      <td>Russia</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Gymnastics</td>
      <td>2</td>
      <td>1</td>
      <td>3</td>
      <td>6</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>8613</th>
      <td>Olena Sadovnycha</td>
      <td>32.0</td>
      <td>Ukraine</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Archery</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>8614</th>
      <td>Kateryna Serdiuk</td>
      <td>17.0</td>
      <td>Ukraine</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Archery</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>8615</th>
      <td>Wietse van Alten</td>
      <td>21.0</td>
      <td>Netherlands</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Archery</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>8616</th>
      <td>Sandra Wagner-Sachse</td>
      <td>31.0</td>
      <td>Germany</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Archery</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>8617</th>
      <td>Rod White</td>
      <td>23.0</td>
      <td>United States</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Archery</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
<p>8618 rows × 10 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-2317d2e0-9036-4b56-bb25-03bf1504bb1d')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-2317d2e0-9036-4b56-bb25-03bf1504bb1d button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-2317d2e0-9036-4b56-bb25-03bf1504bb1d');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>




# Basic exploration of dataset 


```python
#Reading first five rows of the dataset using head function
olympic_data.head()
```





  <div id="df-db468732-62c5-414a-89c5-face7a05501a">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>country</th>
      <th>year</th>
      <th>Date_Given</th>
      <th>sports</th>
      <th>gold_medal</th>
      <th>silver_medal</th>
      <th>brone_medal</th>
      <th>total_medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Michael Phelps</td>
      <td>23.0</td>
      <td>United States</td>
      <td>2008</td>
      <td>8/24/2008</td>
      <td>Swimming</td>
      <td>8</td>
      <td>0</td>
      <td>0</td>
      <td>8</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Michael Phelps</td>
      <td>19.0</td>
      <td>United States</td>
      <td>2004</td>
      <td>8/29/2004</td>
      <td>Swimming</td>
      <td>6</td>
      <td>0</td>
      <td>2</td>
      <td>8</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Michael Phelps</td>
      <td>27.0</td>
      <td>United States</td>
      <td>2012</td>
      <td>08-12-2012</td>
      <td>Swimming</td>
      <td>4</td>
      <td>2</td>
      <td>0</td>
      <td>6</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Natalie Coughlin</td>
      <td>25.0</td>
      <td>United States</td>
      <td>2008</td>
      <td>8/24/2008</td>
      <td>Swimming</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>6</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Aleksey Nemov</td>
      <td>24.0</td>
      <td>Russia</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Gymnastics</td>
      <td>2</td>
      <td>1</td>
      <td>3</td>
      <td>6</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-db468732-62c5-414a-89c5-face7a05501a')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-db468732-62c5-414a-89c5-face7a05501a button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-db468732-62c5-414a-89c5-face7a05501a');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```python
#Reading the last five rows of the dataset  using tail function
olympic_data.tail()
```





  <div id="df-e6e28e34-82d4-417d-9c64-a7231df9c562">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>country</th>
      <th>year</th>
      <th>Date_Given</th>
      <th>sports</th>
      <th>gold_medal</th>
      <th>silver_medal</th>
      <th>brone_medal</th>
      <th>total_medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>8613</th>
      <td>Olena Sadovnycha</td>
      <td>32.0</td>
      <td>Ukraine</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Archery</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>8614</th>
      <td>Kateryna Serdiuk</td>
      <td>17.0</td>
      <td>Ukraine</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Archery</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>8615</th>
      <td>Wietse van Alten</td>
      <td>21.0</td>
      <td>Netherlands</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Archery</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>8616</th>
      <td>Sandra Wagner-Sachse</td>
      <td>31.0</td>
      <td>Germany</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Archery</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>8617</th>
      <td>Rod White</td>
      <td>23.0</td>
      <td>United States</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Archery</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-e6e28e34-82d4-417d-9c64-a7231df9c562')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-e6e28e34-82d4-417d-9c64-a7231df9c562 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-e6e28e34-82d4-417d-9c64-a7231df9c562');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```python
#examining the number of rows and columns in the given dataset using shape function
olympic_data.shape
```




    (8618, 10)



**So there are 8618 records collected and 10 variables in the given dataset**

# Analysing the dataset statistically and also how python reading it


**Statistical analysis:**
**Qualitative:**

**Nominal:**

**name** : It is simply the name of the player.so it is a nominal data

**country** : It is simply the name of the country.so it is a nominal data

**Date_given** :Here date_given column is given as string.
 Actually date is a numerical data .since it is date of medal distribution and it is not the measure of interval of time and there is no necessity of addition or subtraction of date(numerical operation),it is considered as nominal data here

**sports** : It is simply the name of the sport.so it is a nominal data

**Quantitative:**

**discrete:**

**year** : It is the measurement and it cannot be decimal.so it is discrete data

**gold_medal** : since it is a count of medals,it is dicrete data

**silver_medal** : since it is a count of medals,it is dicrete data

**bronze_medal** : since it is a count of medals,it is dicrete data

**total_medal** : since it is a count of medals,it is dicrete data

**continuous** :

**age** : since it is the measure of number of years of a person,and it measured in terms of years,months and days,it is continuous data


```python
#statistical analysis using python where we use info() function to do that.
olympic_data.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 8618 entries, 0 to 8617
    Data columns (total 10 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0   name          8613 non-null   object 
     1   age           8613 non-null   float64
     2   country       8618 non-null   object 
     3   year          8618 non-null   int64  
     4   Date_Given    8618 non-null   object 
     5   sports        8618 non-null   object 
     6   gold_medal    8618 non-null   int64  
     7   silver_medal  8618 non-null   int64  
     8   brone_medal   8618 non-null   int64  
     9   total_medal   8618 non-null   int64  
    dtypes: float64(1), int64(5), object(4)
    memory usage: 673.4+ KB
    

Here we have 5 variables of int data type and 4 variable of object(string) data type and 1 float variable.
Here name and age variables  has null values and all other variable do not have null values.
The count of duplicate and null values can be calculated as:



```python
#checking for duplicate values using duplicated() function and summing them
duplicate_values = olympic_data[olympic_data.duplicated()]
duplicate_values

```





  <div id="df-40620d44-6095-4f84-9d32-b1a090e43953">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>country</th>
      <th>year</th>
      <th>Date_Given</th>
      <th>sports</th>
      <th>gold_medal</th>
      <th>silver_medal</th>
      <th>brone_medal</th>
      <th>total_medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1429</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>Brazil</td>
      <td>2012</td>
      <td>08-12-2012</td>
      <td>Volleyball</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1430</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>Brazil</td>
      <td>2012</td>
      <td>08-12-2012</td>
      <td>Volleyball</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4486</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>Argentina</td>
      <td>2012</td>
      <td>08-12-2012</td>
      <td>Hockey</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-40620d44-6095-4f84-9d32-b1a090e43953')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-40620d44-6095-4f84-9d32-b1a090e43953 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-40620d44-6095-4f84-9d32-b1a090e43953');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```python
#dropping the duplicates using drop_duplicates() function
olympic_data.drop_duplicates(inplace=True)
```


```python
#cross checking for duplicates
duplicate_values=olympic_data[olympic_data.duplicated()]
duplicate_values

```





  <div id="df-6500855e-65a4-49db-bf12-3562afe1ba8a">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>country</th>
      <th>year</th>
      <th>Date_Given</th>
      <th>sports</th>
      <th>gold_medal</th>
      <th>silver_medal</th>
      <th>brone_medal</th>
      <th>total_medal</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-6500855e-65a4-49db-bf12-3562afe1ba8a')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-6500855e-65a4-49db-bf12-3562afe1ba8a button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-6500855e-65a4-49db-bf12-3562afe1ba8a');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>




Yes,the duplicate values are deleted.Now we have to work with null values .


```python
#finding the null values by isnull() function and then retrieving count by summing them
olympic_data.isnull().sum()
olympic_data[olympic_data.isnull().any(axis=1)]
```





  <div id="df-570bfbb7-1cd6-4866-99a7-25e898400774">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>country</th>
      <th>year</th>
      <th>Date_Given</th>
      <th>sports</th>
      <th>gold_medal</th>
      <th>silver_medal</th>
      <th>brone_medal</th>
      <th>total_medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1428</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>Brazil</td>
      <td>2012</td>
      <td>08-12-2012</td>
      <td>Volleyball</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1429</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>Brazil</td>
      <td>2012</td>
      <td>08-12-2012</td>
      <td>Volleyball</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1430</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>Brazil</td>
      <td>2012</td>
      <td>08-12-2012</td>
      <td>Volleyball</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4485</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>Argentina</td>
      <td>2012</td>
      <td>08-12-2012</td>
      <td>Hockey</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4486</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>Argentina</td>
      <td>2012</td>
      <td>08-12-2012</td>
      <td>Hockey</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-570bfbb7-1cd6-4866-99a7-25e898400774')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-570bfbb7-1cd6-4866-99a7-25e898400774 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-570bfbb7-1cd6-4866-99a7-25e898400774');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>




we have two rows whose name ,age column has null values ,but we have information about countries and medals
  we may lose the information in our calculation of medals so  I am not deleting the null values here.


```python
# checking for special character using isalpha() function
olympic_data["check_special"]=olympic_data["name"].str.isalpha()
olympic_data
```





  <div id="df-c66307fd-e7bc-4b72-955e-ff34fc095eb8">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>country</th>
      <th>year</th>
      <th>Date_Given</th>
      <th>sports</th>
      <th>gold_medal</th>
      <th>silver_medal</th>
      <th>brone_medal</th>
      <th>total_medal</th>
      <th>check_special</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Michael Phelps</td>
      <td>23.0</td>
      <td>United States</td>
      <td>2008</td>
      <td>8/24/2008</td>
      <td>Swimming</td>
      <td>8</td>
      <td>0</td>
      <td>0</td>
      <td>8</td>
      <td>False</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Michael Phelps</td>
      <td>19.0</td>
      <td>United States</td>
      <td>2004</td>
      <td>8/29/2004</td>
      <td>Swimming</td>
      <td>6</td>
      <td>0</td>
      <td>2</td>
      <td>8</td>
      <td>False</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Michael Phelps</td>
      <td>27.0</td>
      <td>United States</td>
      <td>2012</td>
      <td>08-12-2012</td>
      <td>Swimming</td>
      <td>4</td>
      <td>2</td>
      <td>0</td>
      <td>6</td>
      <td>False</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Natalie Coughlin</td>
      <td>25.0</td>
      <td>United States</td>
      <td>2008</td>
      <td>8/24/2008</td>
      <td>Swimming</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>6</td>
      <td>False</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Aleksey Nemov</td>
      <td>24.0</td>
      <td>Russia</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Gymnastics</td>
      <td>2</td>
      <td>1</td>
      <td>3</td>
      <td>6</td>
      <td>False</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>8613</th>
      <td>Olena Sadovnycha</td>
      <td>32.0</td>
      <td>Ukraine</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Archery</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>8614</th>
      <td>Kateryna Serdiuk</td>
      <td>17.0</td>
      <td>Ukraine</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Archery</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>8615</th>
      <td>Wietse van Alten</td>
      <td>21.0</td>
      <td>Netherlands</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Archery</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>8616</th>
      <td>Sandra Wagner-Sachse</td>
      <td>31.0</td>
      <td>Germany</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Archery</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>8617</th>
      <td>Rod White</td>
      <td>23.0</td>
      <td>United States</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Archery</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>False</td>
    </tr>
  </tbody>
</table>
<p>8618 rows × 11 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-c66307fd-e7bc-4b72-955e-ff34fc095eb8')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-c66307fd-e7bc-4b72-955e-ff34fc095eb8 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-c66307fd-e7bc-4b72-955e-ff34fc095eb8');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>




Here we are getting false if there are special characters and space also.since space cannot be considered as special character,we can delete only special characters as follows:


```python
#Here I have created a list of all the special characters 
spec_chars = ["!",'"',"#","%","&","'","(",")",
              "*","+",",","-",".","/",":",";","<",
              "=",">","?","@","[","\\","]","^","_",
              "`","{","|","}","~","–",".","$"]
#using for loop to remove all special character from each name of "name" column 
for char in spec_chars:
    olympic_data['name'] = olympic_data['name'].str.replace(char,'') 
olympic_data         
```

    /usr/local/lib/python3.7/dist-packages/ipykernel_launcher.py:8: FutureWarning: The default value of regex will change from True to False in a future version. In addition, single character regular expressions will *not* be treated as literal strings when regex=True.
      
    





  <div id="df-d2a733d8-80b7-47f1-a9e7-e2b894b30ec3">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
      <th>country</th>
      <th>year</th>
      <th>Date_Given</th>
      <th>sports</th>
      <th>gold_medal</th>
      <th>silver_medal</th>
      <th>brone_medal</th>
      <th>total_medal</th>
      <th>check_special</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Michael Phelps</td>
      <td>23.0</td>
      <td>United States</td>
      <td>2008</td>
      <td>8/24/2008</td>
      <td>Swimming</td>
      <td>8</td>
      <td>0</td>
      <td>0</td>
      <td>8</td>
      <td>False</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Michael Phelps</td>
      <td>19.0</td>
      <td>United States</td>
      <td>2004</td>
      <td>8/29/2004</td>
      <td>Swimming</td>
      <td>6</td>
      <td>0</td>
      <td>2</td>
      <td>8</td>
      <td>False</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Michael Phelps</td>
      <td>27.0</td>
      <td>United States</td>
      <td>2012</td>
      <td>08-12-2012</td>
      <td>Swimming</td>
      <td>4</td>
      <td>2</td>
      <td>0</td>
      <td>6</td>
      <td>False</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Natalie Coughlin</td>
      <td>25.0</td>
      <td>United States</td>
      <td>2008</td>
      <td>8/24/2008</td>
      <td>Swimming</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>6</td>
      <td>False</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Aleksey Nemov</td>
      <td>24.0</td>
      <td>Russia</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Gymnastics</td>
      <td>2</td>
      <td>1</td>
      <td>3</td>
      <td>6</td>
      <td>False</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>8613</th>
      <td>Olena Sadovnycha</td>
      <td>32.0</td>
      <td>Ukraine</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Archery</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>8614</th>
      <td>Kateryna Serdiuk</td>
      <td>17.0</td>
      <td>Ukraine</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Archery</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>8615</th>
      <td>Wietse van Alten</td>
      <td>21.0</td>
      <td>Netherlands</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Archery</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>8616</th>
      <td>Sandra WagnerSachse</td>
      <td>31.0</td>
      <td>Germany</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Archery</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>8617</th>
      <td>Rod White</td>
      <td>23.0</td>
      <td>United States</td>
      <td>2000</td>
      <td>10-01-2000</td>
      <td>Archery</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>False</td>
    </tr>
  </tbody>
</table>
<p>8618 rows × 11 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-d2a733d8-80b7-47f1-a9e7-e2b894b30ec3')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-d2a733d8-80b7-47f1-a9e7-e2b894b30ec3 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-d2a733d8-80b7-47f1-a9e7-e2b894b30ec3');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>




This is the dataset after removing special charcters.


```python
#Here I am using histoplot to study the distribution of "age" column
plt.figure(figsize=(15,8))
plt.title("Distribution of age column")
sns.histplot(olympic_data["age"])#it is seaborn histoplot (the library we hav imported earlier)

```




    <matplotlib.axes._subplots.AxesSubplot at 0x7f3fd4126550>




    
![png](output_25_1.png)
    


It is right skewed plot which clearly shows most of the players who won the medals are between 20  and 30 age group
and  there are almost negligible players after 50


```python
#Here I am using histoplot to study the distribution of "years" column
plt.figure(figsize=(15,8))
plt.title("distribution of year column")
sns.histplot(olympic_data["year"])#it is seaborn histoplot (the library we hav imported earlier)
```




    <matplotlib.axes._subplots.AxesSubplot at 0x7f3fd3f847d0>




    
![png](output_27_1.png)
    


Here the plot shows us that olympic games has been for every 2 years without fail between 2000 and 2012 

It also tells us medals are more in 2000,2004,2008,2012 than other years and there is uniformity.

# **Analysis of all the numerical measures**


```python
#Here all the numerical measures of variables can be  calculated using describe method
olympic_data.describe()
```





  <div id="df-59a61c61-50d8-42b0-818e-50357a3a93e2">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>age</th>
      <th>year</th>
      <th>gold_medal</th>
      <th>silver_medal</th>
      <th>brone_medal</th>
      <th>total_medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>8613.000000</td>
      <td>8615.000000</td>
      <td>8615.000000</td>
      <td>8615.000000</td>
      <td>8615.000000</td>
      <td>8615.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>26.405434</td>
      <td>2005.976785</td>
      <td>0.364829</td>
      <td>0.363088</td>
      <td>0.377829</td>
      <td>1.105746</td>
    </tr>
    <tr>
      <th>std</th>
      <td>5.102118</td>
      <td>4.289221</td>
      <td>0.545401</td>
      <td>0.511564</td>
      <td>0.505044</td>
      <td>0.408958</td>
    </tr>
    <tr>
      <th>min</th>
      <td>15.000000</td>
      <td>2000.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>23.000000</td>
      <td>2002.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>26.000000</td>
      <td>2006.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>29.000000</td>
      <td>2010.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>61.000000</td>
      <td>2012.000000</td>
      <td>8.000000</td>
      <td>3.000000</td>
      <td>3.000000</td>
      <td>8.000000</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-59a61c61-50d8-42b0-818e-50357a3a93e2')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-59a61c61-50d8-42b0-818e-50357a3a93e2 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-59a61c61-50d8-42b0-818e-50357a3a93e2');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>




Here the minimum age of players who won medal is 15 and maximum age is 61

The duration of years between 2000 and 2012

The minimum number of medals a player won in a year is !2 and the maximun is 8


```python
olympic_data.median()#calculating the median
```

    /usr/local/lib/python3.7/dist-packages/ipykernel_launcher.py:1: FutureWarning: Dropping of nuisance columns in DataFrame reductions (with 'numeric_only=None') is deprecated; in a future version this will raise TypeError.  Select only valid columns before calling the reduction.
      """Entry point for launching an IPython kernel.
    




    age                26.0
    year             2006.0
    gold_medal          0.0
    silver_medal        0.0
    brone_medal         0.0
    total_medal         1.0
    check_special       0.0
    dtype: float64



Here we can observe mean,median,min,max of all the numerical variables.


```python
# Here I am calculating the skewness of all the numerical variables using skew() function
olympic_data.skew()
```

    /usr/local/lib/python3.7/dist-packages/ipykernel_launcher.py:1: FutureWarning: Dropping of nuisance columns in DataFrame reductions (with 'numeric_only=None') is deprecated; in a future version this will raise TypeError.  Select only valid columns before calling the reduction.
      """Entry point for launching an IPython kernel.
    




    age              0.859007
    year            -0.001464
    gold_medal       1.639170
    silver_medal     0.954215
    brone_medal      0.762454
    total_medal      5.581633
    check_special    7.405543
    dtype: float64



    The skewness of "age" column  is 0.85 which  is between -1 to 1, which is moderately skewed .
     The skewness of "year" column is 0 . so there is obviously no skewness in the column since games are coducted every two years.

For right skewed data we use square root,cube root,logarithms,reciprocals methods to convert to normal distribution

       But logarithms method is more effective one for right skewness()


```python
#Here bar plot is used to study the distribution of categorical column sports
olympic_data['sports'].value_counts().plot(kind='bar',figsize=(15,5))
plt.title("distribution of sports\n")
plt.ylabel("count")
plt.xlabel("list of all the sports")
```




    Text(0.5, 0, 'list of all the sports')




    
![png](output_37_1.png)
    


Among all sports conducted "Athletics" is the most played game and it is the one where more number of  medals are won


```python
#displaying each country and the gold medals the have won
olympic_data_gold=olympic_data.groupby("country")["gold_medal"].sum().sort_values(ascending=False).head(10)
olympic_data_gold
```




    country
    United States    552
    Russia           234
    China            234
    Germany          223
    Canada           168
    Australia        163
    Great Britain    124
    South Korea      110
    France           108
    Netherlands      101
    Name: gold_medal, dtype: int64



Here united states got maximum gold medals and the count is 552


```python
#displaying each country and the silver_medals the have won
olympic_data_silver=olympic_data.groupby("country")["silver_medal"].sum().sort_values(ascending=False).head(10)
print(olympic_data_silver)
print("\nThe maximum number of silver medals was won by US which are :",440)
```

    country
    United States    440
    Australia        226
    Russia           221
    Germany          183
    China            156
    Netherlands      135
    Spain            116
    Japan            112
    France           107
    Italy            103
    Name: silver_medal, dtype: int64
    
    The maximum number of silver medals was won by US which are : 440
    


```python
#displaying each country and the bronze medals they have won
olympic_data_brone=olympic_data.groupby("country")["brone_medal"].sum().sort_values(ascending=False).head(10)
print(olympic_data_brone)
print("\nThe maximum number of bronze  medals was won by US which are :",320)
```

    country
    United States    320
    Russia           313
    Germany          223
    Australia        220
    Italy            142
    China            140
    Japan            113
    South Korea      105
    Canada           104
    France           103
    Name: brone_medal, dtype: int64
    
    The maximum number of bronze  medals was won by US which are : 320
    


```python
##displaying each country and the total medals they have won
olympic_data_total_medal=olympic_data.groupby("country")["total_medal"].sum().sort_values(ascending=False).head(10)
print(olympic_data_total_medal)
print("\nThe maximum number of total medals was won by US which are :",1312)
```

    country
    United States    1312
    Russia            768
    Germany           629
    Australia         609
    China             530
    Canada            370
    Italy             331
    Great Britain     322
    France            318
    Netherlands       318
    Name: total_medal, dtype: int64
    
    The maximum number of total medals was won by US which are : 1312
    
