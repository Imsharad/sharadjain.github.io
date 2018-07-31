

```python
def table_join(file) :
    
```


```python
import pandas as pd
```


```python
data  =pd.read_csv("./data/train_features_2013-03-07.csv")
```


```python
data.head(5)
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>jobId</th>
      <th>companyId</th>
      <th>jobType</th>
      <th>degree</th>
      <th>major</th>
      <th>industry</th>
      <th>yearsExperience</th>
      <th>milesFromMetropolis</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>JOB1362684407687</td>
      <td>COMP37</td>
      <td>CFO</td>
      <td>MASTERS</td>
      <td>MATH</td>
      <td>HEALTH</td>
      <td>10</td>
      <td>83</td>
    </tr>
    <tr>
      <th>1</th>
      <td>JOB1362684407688</td>
      <td>COMP19</td>
      <td>CEO</td>
      <td>HIGH_SCHOOL</td>
      <td>NONE</td>
      <td>WEB</td>
      <td>3</td>
      <td>73</td>
    </tr>
    <tr>
      <th>2</th>
      <td>JOB1362684407689</td>
      <td>COMP52</td>
      <td>VICE_PRESIDENT</td>
      <td>DOCTORAL</td>
      <td>PHYSICS</td>
      <td>HEALTH</td>
      <td>10</td>
      <td>38</td>
    </tr>
    <tr>
      <th>3</th>
      <td>JOB1362684407690</td>
      <td>COMP38</td>
      <td>MANAGER</td>
      <td>DOCTORAL</td>
      <td>CHEMISTRY</td>
      <td>AUTO</td>
      <td>8</td>
      <td>17</td>
    </tr>
    <tr>
      <th>4</th>
      <td>JOB1362684407691</td>
      <td>COMP7</td>
      <td>VICE_PRESIDENT</td>
      <td>BACHELORS</td>
      <td>PHYSICS</td>
      <td>FINANCE</td>
      <td>8</td>
      <td>16</td>
    </tr>
  </tbody>
</table>
</div>




```python
salary = pd.read_csv("./data/train_salaries_2013-03-07.csv")
```


```python
salary.head(4)
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>jobId</th>
      <th>salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>JOB1362684407687</td>
      <td>130</td>
    </tr>
    <tr>
      <th>1</th>
      <td>JOB1362684407688</td>
      <td>101</td>
    </tr>
    <tr>
      <th>2</th>
      <td>JOB1362684407689</td>
      <td>137</td>
    </tr>
    <tr>
      <th>3</th>
      <td>JOB1362684407690</td>
      <td>142</td>
    </tr>
  </tbody>
</table>
</div>




```python
#pd.merge(df1, df2, on='key', how='left')

data1 = pd.merge(data,salary, on='jobId',how='left')
```


```python
data1.to_csv("features_salary1.csv")
```
