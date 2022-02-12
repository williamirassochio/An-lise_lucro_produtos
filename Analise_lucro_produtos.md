```python
import pandas as pd
analise_estoque = pd.read_csv('Contoso - Cadastro Produtos.csv',sep = ';')
analise_estoque
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
      <th>Tipo</th>
      <th>Custo Unitario</th>
      <th>Preco Unitario</th>
      <th>ID Produto</th>
      <th>Categoria</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Contoso</td>
      <td>Econômico</td>
      <td>10,69</td>
      <td>20,96</td>
      <td>873</td>
      <td>Acessório para Computador</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Contoso</td>
      <td>Econômico</td>
      <td>6,63</td>
      <td>13</td>
      <td>879</td>
      <td>Acessório para Computador</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Contoso</td>
      <td>Econômico</td>
      <td>6,63</td>
      <td>13</td>
      <td>880</td>
      <td>Acessório para Computador</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Contoso</td>
      <td>Econômico</td>
      <td>6,63</td>
      <td>13</td>
      <td>881</td>
      <td>Acessório para Computador</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Contoso</td>
      <td>Econômico</td>
      <td>6,63</td>
      <td>13</td>
      <td>882</td>
      <td>Acessório para Computador</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1685</th>
      <td>Southridge Video</td>
      <td>Regular</td>
      <td>82,77</td>
      <td>179,99</td>
      <td>1602</td>
      <td>Filme DVD</td>
    </tr>
    <tr>
      <th>1686</th>
      <td>Southridge Video</td>
      <td>Regular</td>
      <td>73,57</td>
      <td>159,99</td>
      <td>1606</td>
      <td>Filme DVD</td>
    </tr>
    <tr>
      <th>1687</th>
      <td>Southridge Video</td>
      <td>Regular</td>
      <td>82,77</td>
      <td>179,99</td>
      <td>1607</td>
      <td>Filme DVD</td>
    </tr>
    <tr>
      <th>1688</th>
      <td>Southridge Video</td>
      <td>Regular</td>
      <td>73,57</td>
      <td>159,99</td>
      <td>1611</td>
      <td>Filme DVD</td>
    </tr>
    <tr>
      <th>1689</th>
      <td>Southridge Video</td>
      <td>Regular</td>
      <td>82,77</td>
      <td>179,99</td>
      <td>1612</td>
      <td>Filme DVD</td>
    </tr>
  </tbody>
</table>
<p>1690 rows × 6 columns</p>
</div>


