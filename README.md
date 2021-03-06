<h1 style="text-align: justify; color: black">TOPSIS
</h1>TOPSIS is an acronym that stands for ‘Technique of Order Preference Similarity to the Ideal Solution’ and is a pretty straightforward MCDA method. As the name implies, the method is based on finding an ideal and an anti-ideal solution and comparing the distance of each one of the alternatives to those. It was presented in Hwang and Yoon (Multiple attribute decision making: methods and applications. Springer, Berlin, 1981) and Chen and Hwang (Fuzzy multiple attribute decision making methods. Springer, Berlin, 1992), and can be considered as one of the classical MCDA methods that has received a lot of attention from scholars and researchers.
<h2 style="text-align: justify; color: black">Dependencies
</h2>

```
• OS
• Pandas
```

<h2 style="text-align: justify; color: black">Installation
</h2>

```
pip install TOPSIS-Parth-101983047==0.0.7
```

<h2 style="text-align: justify; color: black">Usage
</h2>

```
perform_Topsis(source, weights, impacts, result)
```

<h2 style="text-align: justify; color: black">Parameters
</h2>

```
source : Input data file in .csv format
weights : List of weights for columns except first column
impacts : list of impacts for columns except first column
result : Output file name to store results in .csv format
```

<h2 style="text-align: justify; color: black">Constraints / Exceptions handled
</h2>

```
1. Correct number of parameters (source, weights, impacts, result)
2. Handling of “File not Found” exception
3. Input file must contain three or more columns.
4. From 2 nd to last columns must contain numeric values only (Handling of non-numeric values)
5. Number of weights, number of impacts and number of columns (from 2 nd to last columns) must
be same.
6. Impacts must be either +ve or -ve.
7. Impacts and weights must be separated by ‘,’ (comma).
8. Output "File already exists" condition
```

<h2 style="text-align: justify; color: black">Example
</h2><h5 style="text-align: justify; color: black">'data.csv' in the same folder ----&gt;
</h5><br><table class="table table-bordered table-hover table-condensed">
<thead><tr><th title="Field #1">Model</th>
<th title="Field #2">Corr</th>
<th title="Field #3">Rseq</th>
<th title="Field #4">RMSE</th>
<th title="Field #5">Accuracy</th>
</tr></thead>
<tbody><tr>
<td>M1</td>
<td align="right">0.79</td>
<td align="right">0.62</td>
<td align="right">1.25</td>
<td align="right">60.89</td>
</tr>
<tr>
<td>M2</td>
<td align="right">0.66</td>
<td align="right">0.44</td>
<td align="right">2.89</td>
<td align="right">63.07</td>
</tr>
<tr>
<td>M3</td>
<td align="right">0.56</td>
<td align="right">0.31</td>
<td align="right">1.57</td>
<td align="right">62.87</td>
</tr>
<tr>
<td>M4</td>
<td align="right">0.82</td>
<td align="right">0.67</td>
<td align="right">2.68</td>
<td align="right">70.19</td>
</tr>
<tr>
<td>M5</td>
<td align="right">0.75</td>
<td align="right">0.56</td>
<td align="right">1.3</td>
<td align="right">80.39</td>
</tr>
</tbody></table>
<br>

```
>>>python
>>>from Topsis.topsis import perform_Topsis
>>>perform_Topsis('data.csv', [1,2,1,2], ['+','-','-','+'], 'result.csv')

Generating output file ....
Output file generated.

```
<h5 style="text-align: justify; color: black">'result.csv' generated in the same folder ----&gt;
<br>
</h5>
<table class="table table-bordered table-hover table-condensed">
<thead><tr><th title="Field #1">Model</th>
<th title="Field #2">Corr</th>
<th title="Field #3">Rseq</th>
<th title="Field #4">RMSE</th>
<th title="Field #5">Accuracy</th>
<th title="Field #6">Topsis Score</th>
<th title="Field #7">Rank</th>
</tr></thead>
<tbody><tr>
<td>M1</td>
<td align="right">0.79</td>
<td align="right">0.62</td>
<td align="right">1.25</td>
<td align="right">60.89</td>
<td align="right">0.404270981738897</td>
<td align="right">4.0</td>
</tr>
<tr>
<td>M2</td>
<td align="right">0.66</td>
<td align="right">0.44</td>
<td align="right">2.89</td>
<td align="right">63.07</td>
<td align="right">0.44542964404513863</td>
<td align="right">3.0</td>
</tr>
<tr>
<td>M3</td>
<td align="right">0.56</td>
<td align="right">0.31</td>
<td align="right">1.57</td>
<td align="right">62.87</td>
<td align="right">0.6966994505305135</td>
<td align="right">1.0</td>
</tr>
<tr>
<td>M4</td>
<td align="right">0.82</td>
<td align="right">0.67</td>
<td align="right">2.68</td>
<td align="right">70.19</td>
<td align="right">0.2312955403197052</td>
<td align="right">5.0</td>
</tr>
<tr>
<td>M5</td>
<td align="right">0.75</td>
<td align="right">0.56</td>
<td align="right">1.3</td>
<td align="right">80.39</td>
<td align="right">0.534754530220428</td>
<td align="right">2.0</td>
</tr>
</tbody></table>
