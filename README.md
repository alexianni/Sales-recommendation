# Sales-recommendation-with-R

### Carga de la base de datos
```
rm(list =ls())
data(mtcars)
```
### Visualización de la base de datos
```
view(mtcars)
```
- Output 
<table style="border-collapse:collapse;" class="table_6273" border="1">
<thead>
<tr>
  <th id="tableHTML_header_1"> </th>
  <th id="tableHTML_header_2">mpg</th>
  <th id="tableHTML_header_3">cyl</th>
  <th id="tableHTML_header_4">disp</th>
  <th id="tableHTML_header_5">hp</th>
  <th id="tableHTML_header_6">drat</th>
  <th id="tableHTML_header_7">wt</th>
  <th id="tableHTML_header_8">qsec</th>
  <th id="tableHTML_header_9">vs</th>
  <th id="tableHTML_header_10">am</th>
  <th id="tableHTML_header_11">gear</th>
  <th id="tableHTML_header_12">carb</th>
</tr>
</thead>
<tbody>
<tr>
  <td id="tableHTML_rownames">Mazda RX4</td>
  <td id="tableHTML_column_1">21</td>
  <td id="tableHTML_column_2">6</td>
  <td id="tableHTML_column_3">160</td>
  <td id="tableHTML_column_4">110</td>
  <td id="tableHTML_column_5">3.9</td>
  <td id="tableHTML_column_6">2.62</td>
  <td id="tableHTML_column_7">16.46</td>
  <td id="tableHTML_column_8">0</td>
  <td id="tableHTML_column_9">1</td>
  <td id="tableHTML_column_10">4</td>
  <td id="tableHTML_column_11">4</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Mazda RX4 Wag</td>
  <td id="tableHTML_column_1">21</td>
  <td id="tableHTML_column_2">6</td>
  <td id="tableHTML_column_3">160</td>
  <td id="tableHTML_column_4">110</td>
  <td id="tableHTML_column_5">3.9</td>
  <td id="tableHTML_column_6">2.875</td>
  <td id="tableHTML_column_7">17.02</td>
  <td id="tableHTML_column_8">0</td>
  <td id="tableHTML_column_9">1</td>
  <td id="tableHTML_column_10">4</td>
  <td id="tableHTML_column_11">4</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Datsun 710</td>
  <td id="tableHTML_column_1">22.8</td>
  <td id="tableHTML_column_2">4</td>
  <td id="tableHTML_column_3">108</td>
  <td id="tableHTML_column_4">93</td>
  <td id="tableHTML_column_5">3.85</td>
  <td id="tableHTML_column_6">2.32</td>
  <td id="tableHTML_column_7">18.61</td>
  <td id="tableHTML_column_8">1</td>
  <td id="tableHTML_column_9">1</td>
  <td id="tableHTML_column_10">4</td>
  <td id="tableHTML_column_11">1</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Hornet 4 Drive</td>
  <td id="tableHTML_column_1">21.4</td>
  <td id="tableHTML_column_2">6</td>
  <td id="tableHTML_column_3">258</td>
  <td id="tableHTML_column_4">110</td>
  <td id="tableHTML_column_5">3.08</td>
  <td id="tableHTML_column_6">3.215</td>
  <td id="tableHTML_column_7">19.44</td>
  <td id="tableHTML_column_8">1</td>
  <td id="tableHTML_column_9">0</td>
  <td id="tableHTML_column_10">3</td>
  <td id="tableHTML_column_11">1</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Hornet Sportabout</td>
  <td id="tableHTML_column_1">18.7</td>
  <td id="tableHTML_column_2">8</td>
  <td id="tableHTML_column_3">360</td>
  <td id="tableHTML_column_4">175</td>
  <td id="tableHTML_column_5">3.15</td>
  <td id="tableHTML_column_6">3.44</td>
  <td id="tableHTML_column_7">17.02</td>
  <td id="tableHTML_column_8">0</td>
  <td id="tableHTML_column_9">0</td>
  <td id="tableHTML_column_10">3</td>
  <td id="tableHTML_column_11">2</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Valiant</td>
  <td id="tableHTML_column_1">18.1</td>
  <td id="tableHTML_column_2">6</td>
  <td id="tableHTML_column_3">225</td>
  <td id="tableHTML_column_4">105</td>
  <td id="tableHTML_column_5">2.76</td>
  <td id="tableHTML_column_6">3.46</td>
  <td id="tableHTML_column_7">20.22</td>
  <td id="tableHTML_column_8">1</td>
  <td id="tableHTML_column_9">0</td>
  <td id="tableHTML_column_10">3</td>
  <td id="tableHTML_column_11">1</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Duster 360</td>
  <td id="tableHTML_column_1">14.3</td>
  <td id="tableHTML_column_2">8</td>
  <td id="tableHTML_column_3">360</td>
  <td id="tableHTML_column_4">245</td>
  <td id="tableHTML_column_5">3.21</td>
  <td id="tableHTML_column_6">3.57</td>
  <td id="tableHTML_column_7">15.84</td>
  <td id="tableHTML_column_8">0</td>
  <td id="tableHTML_column_9">0</td>
  <td id="tableHTML_column_10">3</td>
  <td id="tableHTML_column_11">4</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Merc 240D</td>
  <td id="tableHTML_column_1">24.4</td>
  <td id="tableHTML_column_2">4</td>
  <td id="tableHTML_column_3">146.7</td>
  <td id="tableHTML_column_4">62</td>
  <td id="tableHTML_column_5">3.69</td>
  <td id="tableHTML_column_6">3.19</td>
  <td id="tableHTML_column_7">20</td>
  <td id="tableHTML_column_8">1</td>
  <td id="tableHTML_column_9">0</td>
  <td id="tableHTML_column_10">4</td>
  <td id="tableHTML_column_11">2</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Merc 230</td>
  <td id="tableHTML_column_1">22.8</td>
  <td id="tableHTML_column_2">4</td>
  <td id="tableHTML_column_3">140.8</td>
  <td id="tableHTML_column_4">95</td>
  <td id="tableHTML_column_5">3.92</td>
  <td id="tableHTML_column_6">3.15</td>
  <td id="tableHTML_column_7">22.9</td>
  <td id="tableHTML_column_8">1</td>
  <td id="tableHTML_column_9">0</td>
  <td id="tableHTML_column_10">4</td>
  <td id="tableHTML_column_11">2</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Merc 280</td>
  <td id="tableHTML_column_1">19.2</td>
  <td id="tableHTML_column_2">6</td>
  <td id="tableHTML_column_3">167.6</td>
  <td id="tableHTML_column_4">123</td>
  <td id="tableHTML_column_5">3.92</td>
  <td id="tableHTML_column_6">3.44</td>
  <td id="tableHTML_column_7">18.3</td>
  <td id="tableHTML_column_8">1</td>
  <td id="tableHTML_column_9">0</td>
  <td id="tableHTML_column_10">4</td>
  <td id="tableHTML_column_11">4</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Merc 280C</td>
  <td id="tableHTML_column_1">17.8</td>
  <td id="tableHTML_column_2">6</td>
  <td id="tableHTML_column_3">167.6</td>
  <td id="tableHTML_column_4">123</td>
  <td id="tableHTML_column_5">3.92</td>
  <td id="tableHTML_column_6">3.44</td>
  <td id="tableHTML_column_7">18.9</td>
  <td id="tableHTML_column_8">1</td>
  <td id="tableHTML_column_9">0</td>
  <td id="tableHTML_column_10">4</td>
  <td id="tableHTML_column_11">4</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Merc 450SE</td>
  <td id="tableHTML_column_1">16.4</td>
  <td id="tableHTML_column_2">8</td>
  <td id="tableHTML_column_3">275.8</td>
  <td id="tableHTML_column_4">180</td>
  <td id="tableHTML_column_5">3.07</td>
  <td id="tableHTML_column_6">4.07</td>
  <td id="tableHTML_column_7">17.4</td>
  <td id="tableHTML_column_8">0</td>
  <td id="tableHTML_column_9">0</td>
  <td id="tableHTML_column_10">3</td>
  <td id="tableHTML_column_11">3</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Merc 450SL</td>
  <td id="tableHTML_column_1">17.3</td>
  <td id="tableHTML_column_2">8</td>
  <td id="tableHTML_column_3">275.8</td>
  <td id="tableHTML_column_4">180</td>
  <td id="tableHTML_column_5">3.07</td>
  <td id="tableHTML_column_6">3.73</td>
  <td id="tableHTML_column_7">17.6</td>
  <td id="tableHTML_column_8">0</td>
  <td id="tableHTML_column_9">0</td>
  <td id="tableHTML_column_10">3</td>
  <td id="tableHTML_column_11">3</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Merc 450SLC</td>
  <td id="tableHTML_column_1">15.2</td>
  <td id="tableHTML_column_2">8</td>
  <td id="tableHTML_column_3">275.8</td>
  <td id="tableHTML_column_4">180</td>
  <td id="tableHTML_column_5">3.07</td>
  <td id="tableHTML_column_6">3.78</td>
  <td id="tableHTML_column_7">18</td>
  <td id="tableHTML_column_8">0</td>
  <td id="tableHTML_column_9">0</td>
  <td id="tableHTML_column_10">3</td>
  <td id="tableHTML_column_11">3</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Cadillac Fleetwood</td>
  <td id="tableHTML_column_1">10.4</td>
  <td id="tableHTML_column_2">8</td>
  <td id="tableHTML_column_3">472</td>
  <td id="tableHTML_column_4">205</td>
  <td id="tableHTML_column_5">2.93</td>
  <td id="tableHTML_column_6">5.25</td>
  <td id="tableHTML_column_7">17.98</td>
  <td id="tableHTML_column_8">0</td>
  <td id="tableHTML_column_9">0</td>
  <td id="tableHTML_column_10">3</td>
  <td id="tableHTML_column_11">4</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Lincoln Continental</td>
  <td id="tableHTML_column_1">10.4</td>
  <td id="tableHTML_column_2">8</td>
  <td id="tableHTML_column_3">460</td>
  <td id="tableHTML_column_4">215</td>
  <td id="tableHTML_column_5">3</td>
  <td id="tableHTML_column_6">5.424</td>
  <td id="tableHTML_column_7">17.82</td>
  <td id="tableHTML_column_8">0</td>
  <td id="tableHTML_column_9">0</td>
  <td id="tableHTML_column_10">3</td>
  <td id="tableHTML_column_11">4</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Chrysler Imperial</td>
  <td id="tableHTML_column_1">14.7</td>
  <td id="tableHTML_column_2">8</td>
  <td id="tableHTML_column_3">440</td>
  <td id="tableHTML_column_4">230</td>
  <td id="tableHTML_column_5">3.23</td>
  <td id="tableHTML_column_6">5.345</td>
  <td id="tableHTML_column_7">17.42</td>
  <td id="tableHTML_column_8">0</td>
  <td id="tableHTML_column_9">0</td>
  <td id="tableHTML_column_10">3</td>
  <td id="tableHTML_column_11">4</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Fiat 128</td>
  <td id="tableHTML_column_1">32.4</td>
  <td id="tableHTML_column_2">4</td>
  <td id="tableHTML_column_3">78.7</td>
  <td id="tableHTML_column_4">66</td>
  <td id="tableHTML_column_5">4.08</td>
  <td id="tableHTML_column_6">2.2</td>
  <td id="tableHTML_column_7">19.47</td>
  <td id="tableHTML_column_8">1</td>
  <td id="tableHTML_column_9">1</td>
  <td id="tableHTML_column_10">4</td>
  <td id="tableHTML_column_11">1</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Honda Civic</td>
  <td id="tableHTML_column_1">30.4</td>
  <td id="tableHTML_column_2">4</td>
  <td id="tableHTML_column_3">75.7</td>
  <td id="tableHTML_column_4">52</td>
  <td id="tableHTML_column_5">4.93</td>
  <td id="tableHTML_column_6">1.615</td>
  <td id="tableHTML_column_7">18.52</td>
  <td id="tableHTML_column_8">1</td>
  <td id="tableHTML_column_9">1</td>
  <td id="tableHTML_column_10">4</td>
  <td id="tableHTML_column_11">2</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Toyota Corolla</td>
  <td id="tableHTML_column_1">33.9</td>
  <td id="tableHTML_column_2">4</td>
  <td id="tableHTML_column_3">71.1</td>
  <td id="tableHTML_column_4">65</td>
  <td id="tableHTML_column_5">4.22</td>
  <td id="tableHTML_column_6">1.835</td>
  <td id="tableHTML_column_7">19.9</td>
  <td id="tableHTML_column_8">1</td>
  <td id="tableHTML_column_9">1</td>
  <td id="tableHTML_column_10">4</td>
  <td id="tableHTML_column_11">1</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Toyota Corona</td>
  <td id="tableHTML_column_1">21.5</td>
  <td id="tableHTML_column_2">4</td>
  <td id="tableHTML_column_3">120.1</td>
  <td id="tableHTML_column_4">97</td>
  <td id="tableHTML_column_5">3.7</td>
  <td id="tableHTML_column_6">2.465</td>
  <td id="tableHTML_column_7">20.01</td>
  <td id="tableHTML_column_8">1</td>
  <td id="tableHTML_column_9">0</td>
  <td id="tableHTML_column_10">3</td>
  <td id="tableHTML_column_11">1</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Dodge Challenger</td>
  <td id="tableHTML_column_1">15.5</td>
  <td id="tableHTML_column_2">8</td>
  <td id="tableHTML_column_3">318</td>
  <td id="tableHTML_column_4">150</td>
  <td id="tableHTML_column_5">2.76</td>
  <td id="tableHTML_column_6">3.52</td>
  <td id="tableHTML_column_7">16.87</td>
  <td id="tableHTML_column_8">0</td>
  <td id="tableHTML_column_9">0</td>
  <td id="tableHTML_column_10">3</td>
  <td id="tableHTML_column_11">2</td>
</tr>
<tr>
  <td id="tableHTML_rownames">AMC Javelin</td>
  <td id="tableHTML_column_1">15.2</td>
  <td id="tableHTML_column_2">8</td>
  <td id="tableHTML_column_3">304</td>
  <td id="tableHTML_column_4">150</td>
  <td id="tableHTML_column_5">3.15</td>
  <td id="tableHTML_column_6">3.435</td>
  <td id="tableHTML_column_7">17.3</td>
  <td id="tableHTML_column_8">0</td>
  <td id="tableHTML_column_9">0</td>
  <td id="tableHTML_column_10">3</td>
  <td id="tableHTML_column_11">2</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Camaro Z28</td>
  <td id="tableHTML_column_1">13.3</td>
  <td id="tableHTML_column_2">8</td>
  <td id="tableHTML_column_3">350</td>
  <td id="tableHTML_column_4">245</td>
  <td id="tableHTML_column_5">3.73</td>
  <td id="tableHTML_column_6">3.84</td>
  <td id="tableHTML_column_7">15.41</td>
  <td id="tableHTML_column_8">0</td>
  <td id="tableHTML_column_9">0</td>
  <td id="tableHTML_column_10">3</td>
  <td id="tableHTML_column_11">4</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Pontiac Firebird</td>
  <td id="tableHTML_column_1">19.2</td>
  <td id="tableHTML_column_2">8</td>
  <td id="tableHTML_column_3">400</td>
  <td id="tableHTML_column_4">175</td>
  <td id="tableHTML_column_5">3.08</td>
  <td id="tableHTML_column_6">3.845</td>
  <td id="tableHTML_column_7">17.05</td>
  <td id="tableHTML_column_8">0</td>
  <td id="tableHTML_column_9">0</td>
  <td id="tableHTML_column_10">3</td>
  <td id="tableHTML_column_11">2</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Fiat X1-9</td>
  <td id="tableHTML_column_1">27.3</td>
  <td id="tableHTML_column_2">4</td>
  <td id="tableHTML_column_3">79</td>
  <td id="tableHTML_column_4">66</td>
  <td id="tableHTML_column_5">4.08</td>
  <td id="tableHTML_column_6">1.935</td>
  <td id="tableHTML_column_7">18.9</td>
  <td id="tableHTML_column_8">1</td>
  <td id="tableHTML_column_9">1</td>
  <td id="tableHTML_column_10">4</td>
  <td id="tableHTML_column_11">1</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Porsche 914-2</td>
  <td id="tableHTML_column_1">26</td>
  <td id="tableHTML_column_2">4</td>
  <td id="tableHTML_column_3">120.3</td>
  <td id="tableHTML_column_4">91</td>
  <td id="tableHTML_column_5">4.43</td>
  <td id="tableHTML_column_6">2.14</td>
  <td id="tableHTML_column_7">16.7</td>
  <td id="tableHTML_column_8">0</td>
  <td id="tableHTML_column_9">1</td>
  <td id="tableHTML_column_10">5</td>
  <td id="tableHTML_column_11">2</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Lotus Europa</td>
  <td id="tableHTML_column_1">30.4</td>
  <td id="tableHTML_column_2">4</td>
  <td id="tableHTML_column_3">95.1</td>
  <td id="tableHTML_column_4">113</td>
  <td id="tableHTML_column_5">3.77</td>
  <td id="tableHTML_column_6">1.513</td>
  <td id="tableHTML_column_7">16.9</td>
  <td id="tableHTML_column_8">1</td>
  <td id="tableHTML_column_9">1</td>
  <td id="tableHTML_column_10">5</td>
  <td id="tableHTML_column_11">2</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Ford Pantera L</td>
  <td id="tableHTML_column_1">15.8</td>
  <td id="tableHTML_column_2">8</td>
  <td id="tableHTML_column_3">351</td>
  <td id="tableHTML_column_4">264</td>
  <td id="tableHTML_column_5">4.22</td>
  <td id="tableHTML_column_6">3.17</td>
  <td id="tableHTML_column_7">14.5</td>
  <td id="tableHTML_column_8">0</td>
  <td id="tableHTML_column_9">1</td>
  <td id="tableHTML_column_10">5</td>
  <td id="tableHTML_column_11">4</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Ferrari Dino</td>
  <td id="tableHTML_column_1">19.7</td>
  <td id="tableHTML_column_2">6</td>
  <td id="tableHTML_column_3">145</td>
  <td id="tableHTML_column_4">175</td>
  <td id="tableHTML_column_5">3.62</td>
  <td id="tableHTML_column_6">2.77</td>
  <td id="tableHTML_column_7">15.5</td>
  <td id="tableHTML_column_8">0</td>
  <td id="tableHTML_column_9">1</td>
  <td id="tableHTML_column_10">5</td>
  <td id="tableHTML_column_11">6</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Maserati Bora</td>
  <td id="tableHTML_column_1">15</td>
  <td id="tableHTML_column_2">8</td>
  <td id="tableHTML_column_3">301</td>
  <td id="tableHTML_column_4">335</td>
  <td id="tableHTML_column_5">3.54</td>
  <td id="tableHTML_column_6">3.57</td>
  <td id="tableHTML_column_7">14.6</td>
  <td id="tableHTML_column_8">0</td>
  <td id="tableHTML_column_9">1</td>
  <td id="tableHTML_column_10">5</td>
  <td id="tableHTML_column_11">8</td>
</tr>
<tr>
  <td id="tableHTML_rownames">Volvo 142E</td>
  <td id="tableHTML_column_1">21.4</td>
  <td id="tableHTML_column_2">4</td>
  <td id="tableHTML_column_3">121</td>
  <td id="tableHTML_column_4">109</td>
  <td id="tableHTML_column_5">4.11</td>
  <td id="tableHTML_column_6">2.78</td>
  <td id="tableHTML_column_7">18.6</td>
  <td id="tableHTML_column_8">1</td>
  <td id="tableHTML_column_9">1</td>
  <td id="tableHTML_column_10">4</td>
  <td id="tableHTML_column_11">2</td>
</tr>
</tbody>
</table>

## Parte 1: Limpieza de datos. En esta sección se eliminan aquellos autos que contienen características no deseadas para el cliente, así cómo también se realiza una revisión de características generales.

### 1) El auto con menor consumo

```
mtcars <- mtcars %>% mutate(kml = mtcars$mpg * (1.61/3.785))
mtcars %>%  arrange(kml)
```
- Toyota Carolla con 14,41 km/l

### 2) Auto menos pesado
```
mtcars <- mtcars %>%  mutate(kg = mtcars$wt*1000/2.204)
mtcars %>% arrange(kg)
```
-  Lotus Europa con 686.47 kg

### 3) Filtrado. Se eliminan los autos que tienen más de 6 cilindros 
```
mtcars <- mtcars %>% filter(cyl<=6)
view(mtcars)
```

## Parte 2: Análisis exploratorio de los datos

### 1) Cuantileles y mediana
```
mtcars %>%  arrange(kml)
median(mtcars$kml)
quantile(mtcars$kml, seq(0,1,0.1))
```

| 0%       | 10%      | 20%      | 30%      | 40%      | 50%      | 60%       | 70%        | 80%       | 90%         | 100%      |
|----------|----------|----------|----------|----------|----------|-----------|------------|-----------|-------------|-----------|
| 7.571466 | 8.026605 | 8.600845 | 8.949643 | 9.102774 | 9.421797 | 9.834399  | 10.991387  | 12.403593 | 13.186262   | 14.419815 |


- La mediana de consumo de gasolina es de 9.21

### 2)  Media de consumo, desagregado por tipo de transmisión 
```
mtcars <- mtcars %>%  mutate(Tipo_transmision= if_else(am==1, "Manual", "Automática"))
mtcars %>%  group_by(Tipo_transmision) %>%  summarize(mean(kml))
```

| Tipo_transmision | Mean(klm) |
|------------------|-----------|
| Automática       | 8.82      |
| Manual           | 11.1      |

- Los autos automaticos son más eficientes que los manuales, si se los compara en función de su consumo de gasolina

### 3) Se crea una columna para identificar si la característica del consumo (alto/bajo) y otra para el peso del auto (alto/bajo)
```
mtcars %>% arrange(kml)
mtcars <- mtcars %>% mutate(mediana_kml=median(kml), mediana_kg=median(kg))
mtcars <- mtcars %>%  mutate(consumo= if_else(mediana_kml>kml, "Alto", "Bajo"),peso= if_else(mediana_kg>kg, "Bajo", "Alto"))
```

``` 
table(mtcars$consumo, mtcars$Tipo_transmision)
```

|      | Automática  | Manual |
|------|-------------|--------|
| Alto | 5           | 4      |
| Bajo | 2           | 7      |


## Parte 3: Visualización de datos

### 1)
```
ggplot(mtcars, aes(x=Tipo_transmision, y=kml, fill=Tipo_transmision)) + geom_boxplot() +
  stat_summary(fun= mean, geom= "point") +
  labs(title = "Estadísticos descriptivos del consumo", subtitle = "Por tipo de transmisión") +
  xlab("Tipo de transmisión") + ylab("Consumo") +
  scale_fill_discrete(name= "Tipo de transmisión", labels = c("Automática", "Manual"))
```
	
![image](https://github.com/alexianni/Sales-recommendation-with-R/blob/main/Estad%C3%ADstica%20descriptiva.png)

### 2) Correlación entre el peso y el consumo
```
cor(mtcars$kml, mtcars$kg, method = "pearson")
```

| [1] -0.8321413  |
|-----------------|

- A medida que el peso disminuye el consumo se vuelve más eficiente (+Kilometros por litro).

- Graficamente
```
ggplot(mtcars, aes(x=kml, y=kg)) + geom_point() +
  labs(title = "Relación entre consumo y peso", subtitle = "Mediante un diagrama de dispersión") +
  xlab("Consumo") + ylab("Peso") 
```
	
![image](https://github.com/alexianni/Sales-recommendation-with-R/blob/main/Diagrama%20de%20dispersi%C3%B3n.png)

### Conclusiones:

- Considerando los análisis hechos la recomendación de compra es que el cliente 
adquiera un auto modelo Lotus Europa que tiene consumo y peso bajo, tiene cuatro 
cilindros y es de transmisión manual
