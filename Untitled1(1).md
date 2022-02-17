```python
import  pandas  as  pd 
#Criar uma váriavel com pandas com preço custo/ preço venda 
analise_produtos  =  pd . read_csv ( 'Contoso - Cadastro Produtos.csv' , sep  =  ';' )
analise_produtos . info ()
analise_produtos  =  analise_produtos [[ 'Nome da Marca' , 'ID Produto' , 'Custo Unitario' , 'Preco Unitario' ]] 
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 1690 entries, 0 to 1689
    Data columns (total 6 columns):
     #   Column          Non-Null Count  Dtype 
    ---  ------          --------------  ----- 
     0   Nome da Marca   1690 non-null   object
     1   Tipo            1690 non-null   object
     2   Custo Unitario  1690 non-null   object
     3   Preco Unitario  1690 non-null   object
     4   ID Produto      1690 non-null   int64 
     5   Categoria       1690 non-null   object
    dtypes: int64(1), object(5)
    memory usage: 46.3+ KB
    


```python
analise_produtos['Custo Unitario'] = analise_produtos['Custo Unitario'].str.replace(',', '.')
analise_produtos['Preco Unitario'] = analise_produtos['Preco Unitario'].str.replace(',', '.')
display(analise_produtos[['Custo Unitario','Preco Unitario']])

```


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
      <th>Custo Unitario</th>
      <th>Preco Unitario</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>10.69</td>
      <td>20.96</td>
    </tr>
    <tr>
      <th>1</th>
      <td>6.63</td>
      <td>13</td>
    </tr>
    <tr>
      <th>2</th>
      <td>6.63</td>
      <td>13</td>
    </tr>
    <tr>
      <th>3</th>
      <td>6.63</td>
      <td>13</td>
    </tr>
    <tr>
      <th>4</th>
      <td>6.63</td>
      <td>13</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1685</th>
      <td>82.77</td>
      <td>179.99</td>
    </tr>
    <tr>
      <th>1686</th>
      <td>73.57</td>
      <td>159.99</td>
    </tr>
    <tr>
      <th>1687</th>
      <td>82.77</td>
      <td>179.99</td>
    </tr>
    <tr>
      <th>1688</th>
      <td>73.57</td>
      <td>159.99</td>
    </tr>
    <tr>
      <th>1689</th>
      <td>82.77</td>
      <td>179.99</td>
    </tr>
  </tbody>
</table>
<p>1690 rows × 2 columns</p>
</div>



```python
analise_produtos[['Custo Unitario','Preco Unitario']] = analise_produtos[['Custo Unitario','Preco Unitario']].astype(float)
analise_produtos . info ()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 1690 entries, 0 to 1689
    Data columns (total 4 columns):
     #   Column          Non-Null Count  Dtype  
    ---  ------          --------------  -----  
     0   Nome da Marca   1690 non-null   object 
     1   ID Produto      1690 non-null   int64  
     2   Custo Unitario  1690 non-null   float64
     3   Preco Unitario  1690 non-null   float64
    dtypes: float64(2), int64(1), object(1)
    memory usage: 46.3+ KB
    


```python
analise_produtos['Lucro Produtos'] = analise_produtos['Preco Unitario'] - analise_produtos['Custo Unitario']
analise_produtos.loc['Total'] = analise_produtos.sum()
analise_produtos
```




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
      <th>Nome da Marca</th>
      <th>ID Produto</th>
      <th>Custo Unitario</th>
      <th>Preco Unitario</th>
      <th>Lucro Produtos</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Contoso</td>
      <td>873</td>
      <td>10.69</td>
      <td>20.96</td>
      <td>10.27</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Contoso</td>
      <td>879</td>
      <td>6.63</td>
      <td>13.00</td>
      <td>6.37</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Contoso</td>
      <td>880</td>
      <td>6.63</td>
      <td>13.00</td>
      <td>6.37</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Contoso</td>
      <td>881</td>
      <td>6.63</td>
      <td>13.00</td>
      <td>6.37</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Contoso</td>
      <td>882</td>
      <td>6.63</td>
      <td>13.00</td>
      <td>6.37</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1686</th>
      <td>Southridge Video</td>
      <td>1606</td>
      <td>73.57</td>
      <td>159.99</td>
      <td>86.42</td>
    </tr>
    <tr>
      <th>1687</th>
      <td>Southridge Video</td>
      <td>1607</td>
      <td>82.77</td>
      <td>179.99</td>
      <td>97.22</td>
    </tr>
    <tr>
      <th>1688</th>
      <td>Southridge Video</td>
      <td>1611</td>
      <td>73.57</td>
      <td>159.99</td>
      <td>86.42</td>
    </tr>
    <tr>
      <th>1689</th>
      <td>Southridge Video</td>
      <td>1612</td>
      <td>82.77</td>
      <td>179.99</td>
      <td>97.22</td>
    </tr>
    <tr>
      <th>Total</th>
      <td>ContosoContosoContosoContosoContosoContosoCont...</td>
      <td>4361115</td>
      <td>658040.91</td>
      <td>1606780.50</td>
      <td>948739.59</td>
    </tr>
  </tbody>
</table>
<p>1691 rows × 5 columns</p>
</div>


