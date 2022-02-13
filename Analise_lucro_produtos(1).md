```python
import pandas as pd
#Criar uma váriavel com pandas com preço custo/ preço venda
analise_produtos = pd.read_csv('Contoso - Cadastro Produtos.csv',sep = ';')
analise_produtos.info()
analise_produtos = analise_produtos[['Nome da Marca','ID Produto','Custo Unitario','Preco Unitario']]
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
display(analise_produtos['Nome da Marca'].value_counts())
display(analise_produtos['Custo Unitario'])
```


    Contoso                 560
    Proseware               177
    Southridge Video        170
    Fabrikam                163
    The Phone Company       152
    Wide World Importers    133
    A. Datum                132
    Adventure Works         128
    Litware                  48
    Northwind Traders        27
    Name: Nome da Marca, dtype: int64



    0       10,69
    1        6,63
    2        6,63
    3        6,63
    4        6,63
            ...  
    1685    82,77
    1686    73,57
    1687    82,77
    1688    73,57
    1689    82,77
    Name: Custo Unitario, Length: 1690, dtype: object



```python
analise_produtos2 = analise_produtos[['Custo Unitario','Preco Unitario']]
analise_produtos2.astype(int)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-47-77a2f3a67637> in <module>
          1 analise_produtos2 = analise_produtos[['Custo Unitario','Preco Unitario']]
    ----> 2 analise_produtos2.astype(int)
    

    ~\anaconda3\lib\site-packages\pandas\core\generic.py in astype(self, dtype, copy, errors)
       5875         else:
       5876             # else, only a single dtype is given
    -> 5877             new_data = self._mgr.astype(dtype=dtype, copy=copy, errors=errors)
       5878             return self._constructor(new_data).__finalize__(self, method="astype")
       5879 
    

    ~\anaconda3\lib\site-packages\pandas\core\internals\managers.py in astype(self, dtype, copy, errors)
        629         self, dtype, copy: bool = False, errors: str = "raise"
        630     ) -> "BlockManager":
    --> 631         return self.apply("astype", dtype=dtype, copy=copy, errors=errors)
        632 
        633     def convert(
    

    ~\anaconda3\lib\site-packages\pandas\core\internals\managers.py in apply(self, f, align_keys, ignore_failures, **kwargs)
        425                     applied = b.apply(f, **kwargs)
        426                 else:
    --> 427                     applied = getattr(b, f)(**kwargs)
        428             except (TypeError, NotImplementedError):
        429                 if not ignore_failures:
    

    ~\anaconda3\lib\site-packages\pandas\core\internals\blocks.py in astype(self, dtype, copy, errors)
        671             vals1d = values.ravel()
        672             try:
    --> 673                 values = astype_nansafe(vals1d, dtype, copy=True)
        674             except (ValueError, TypeError):
        675                 # e.g. astype_nansafe can fail on object-dtype of strings
    

    ~\anaconda3\lib\site-packages\pandas\core\dtypes\cast.py in astype_nansafe(arr, dtype, copy, skipna)
       1072         # work around NumPy brokenness, #1987
       1073         if np.issubdtype(dtype.type, np.integer):
    -> 1074             return lib.astype_intsafe(arr.ravel(), dtype).reshape(arr.shape)
       1075 
       1076         # if we have a datetime/timedelta array of objects
    

    pandas\_libs\lib.pyx in pandas._libs.lib.astype_intsafe()
    

    ValueError: invalid literal for int() with base 10: '10,69'

