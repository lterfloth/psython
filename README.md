# Psython

This package include SPSS related calculations done using python.

## Installation

```
pip install psython
```

## Importing

```
import psython as psy
```

## Cronbach's alpha - with "if deleted"

This package is for calculating Cronbach's alpha of an entire dataset with an "if deleted" table for finding items that should be removed.

The package is using the pingouin package for the actuall calculation of Coronbach's alpha.

### Usage

Here an example of the SAQ DataFrame (q3r = q3 reversed):

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>q1</th>
      <th>q2</th>
      <th>q4</th>
      <th>q5</th>
      <th>q6</th>
      <th>q7</th>
      <th>q8</th>
      <th>q9</th>
      <th>q10</th>
      <th>q11</th>
      <th>...</th>
      <th>q15</th>
      <th>q16</th>
      <th>q17</th>
      <th>q18</th>
      <th>q19</th>
      <th>q20</th>
      <th>q21</th>
      <th>q22</th>
      <th>q23</th>
      <th>q3r</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2</td>
      <td>1</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>3</td>
      <td>1</td>
      <td>1</td>
      <td>2</td>
      <td>1</td>
      <td>...</td>
      <td>2</td>
      <td>3</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>5</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>1</td>
      <td>3</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>5</td>
      <td>2</td>
      <td>2</td>
      <td>...</td>
      <td>4</td>
      <td>3</td>
      <td>2</td>
      <td>2</td>
      <td>3</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>3</td>
      <td>2</td>
      <td>4</td>
      <td>1</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>3</td>
      <td>...</td>
      <td>2</td>
      <td>3</td>
      <td>2</td>
      <td>3</td>
      <td>1</td>
      <td>4</td>
      <td>3</td>
      <td>2</td>
      <td>2</td>
      <td>4</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>1</td>
      <td>4</td>
      <td>3</td>
      <td>3</td>
      <td>4</td>
      <td>2</td>
      <td>2</td>
      <td>4</td>
      <td>2</td>
      <td>...</td>
      <td>3</td>
      <td>3</td>
      <td>2</td>
      <td>4</td>
      <td>2</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>3</td>
      <td>5</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2</td>
      <td>1</td>
      <td>2</td>
      <td>2</td>
      <td>3</td>
      <td>3</td>
      <td>2</td>
      <td>4</td>
      <td>2</td>
      <td>2</td>
      <td>...</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>3</td>
      <td>3</td>
      <td>4</td>
      <td>2</td>
      <td>4</td>
      <td>4</td>
      <td>3</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 23 columns</p>
</div>

```
psy.cronbach_alpha_scale_if_deleted(df)
```

Where df is the items dataframe (each item as a column) and the function will return two objects - the Cronbach's alpha of the entire DataFrame at position 0 and the table of the "if delete" items in position 1.

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Item</th>
      <th>Scale Mean if Item Deleted</th>
      <th>Scale Variance if Item Deleted</th>
      <th>Corrected Item-Total Correlation</th>
      <th>Cronbach's Alpha if Item Deleted</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>q1</td>
      <td>59.892260</td>
      <td>90.121072</td>
      <td>0.520928</td>
      <td>0.791887</td>
    </tr>
    <tr>
      <th>1</th>
      <td>q2</td>
      <td>60.642940</td>
      <td>101.063899</td>
      <td>-0.163158</td>
      <td>0.819978</td>
    </tr>
    <tr>
      <th>2</th>
      <td>q4</td>
      <td>59.480358</td>
      <td>87.967999</td>
      <td>0.569241</td>
      <td>0.788177</td>
    </tr>
    <tr>
      <th>3</th>
      <td>q5</td>
      <td>59.544146</td>
      <td>89.303401</td>
      <td>0.480579</td>
      <td>0.792419</td>
    </tr>
    <tr>
      <th>4</th>
      <td>q6</td>
      <td>60.039284</td>
      <td>87.605071</td>
      <td>0.482416</td>
      <td>0.791397</td>
    </tr>
    <tr>
      <th>5</th>
      <td>q7</td>
      <td>59.342668</td>
      <td>85.655685</td>
      <td>0.594245</td>
      <td>0.785032</td>
    </tr>
    <tr>
      <th>6</th>
      <td>q8</td>
      <td>60.029560</td>
      <td>89.900293</td>
      <td>0.503704</td>
      <td>0.792141</td>
    </tr>
    <tr>
      <th>7</th>
      <td>q9</td>
      <td>59.420070</td>
      <td>100.881838</td>
      <td>-0.137191</td>
      <td>0.828613</td>
    </tr>
    <tr>
      <th>8</th>
      <td>q10</td>
      <td>59.985609</td>
      <td>92.232867</td>
      <td>0.355784</td>
      <td>0.798693</td>
    </tr>
    <tr>
      <th>9</th>
      <td>q11</td>
      <td>60.011280</td>
      <td>88.790145</td>
      <td>0.568318</td>
      <td>0.789112</td>
    </tr>
    <tr>
      <th>10</th>
      <td>q12</td>
      <td>59.106962</td>
      <td>88.451979</td>
      <td>0.562942</td>
      <td>0.788889</td>
    </tr>
    <tr>
      <th>11</th>
      <td>q13</td>
      <td>59.817192</td>
      <td>87.839720</td>
      <td>0.576902</td>
      <td>0.787798</td>
    </tr>
    <tr>
      <th>12</th>
      <td>q14</td>
      <td>59.390121</td>
      <td>87.491716</td>
      <td>0.562476</td>
      <td>0.787931</td>
    </tr>
    <tr>
      <th>13</th>
      <td>q15</td>
      <td>59.500194</td>
      <td>88.766051</td>
      <td>0.484296</td>
      <td>0.791916</td>
    </tr>
    <tr>
      <th>14</th>
      <td>q16</td>
      <td>59.387009</td>
      <td>88.329154</td>
      <td>0.570772</td>
      <td>0.788520</td>
    </tr>
    <tr>
      <th>15</th>
      <td>q17</td>
      <td>59.799689</td>
      <td>88.441961</td>
      <td>0.587849</td>
      <td>0.788165</td>
    </tr>
    <tr>
      <th>16</th>
      <td>q18</td>
      <td>59.697783</td>
      <td>85.993065</td>
      <td>0.608925</td>
      <td>0.784771</td>
    </tr>
    <tr>
      <th>17</th>
      <td>q19</td>
      <td>59.974329</td>
      <td>104.442142</td>
      <td>-0.295795</td>
      <td>0.832243</td>
    </tr>
    <tr>
      <th>18</th>
      <td>q20</td>
      <td>58.642163</td>
      <td>91.699140</td>
      <td>0.313782</td>
      <td>0.800711</td>
    </tr>
    <tr>
      <th>19</th>
      <td>q21</td>
      <td>59.095683</td>
      <td>87.678779</td>
      <td>0.561128</td>
      <td>0.788157</td>
    </tr>
    <tr>
      <th>20</th>
      <td>q22</td>
      <td>59.378452</td>
      <td>101.109248</td>
      <td>-0.152704</td>
      <td>0.823798</td>
    </tr>
    <tr>
      <th>21</th>
      <td>q23</td>
      <td>58.831972</td>
      <td>98.820783</td>
      <td>-0.044039</td>
      <td>0.818680</td>
    </tr>
    <tr>
      <th>22</th>
      <td>q3r</td>
      <td>58.851809</td>
      <td>89.021221</td>
      <td>0.434762</td>
      <td>0.794258</td>
    </tr>
  </tbody>
</table>
</div>
