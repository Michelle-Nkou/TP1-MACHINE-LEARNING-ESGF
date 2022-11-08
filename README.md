# TP 1 MACHINE LEARNING


1. IMPORTATION DES DONNEES

```python
import pandas as pd
import numpy as np

Com_pos = pd.read_pickle(r'data/imdb_raw_pos.pickle')
Com_neg = pd.read_pickle(r'data/imdb_raw_neg.pickle')
```

2. PREPROCESSING

```python
def Cleaner_data(txt):
    # Conversion des textes majuscule en minuscule
    txt = txt.lower()
    # suppression de la ponctuaction 
    puncts = str.maketrans(string.punctuation, ' '*len(string.punctuation))
    txt = txt.translate(puncts)
    # regex
    txt = re.sub(r'\d+', '', txt)
    txt = re.sub('https?://\S+|www\.\S+', '', txt)
    txt = re.sub('\n', '', txt)

    return txt
```

2. MODELISATION
```python
Reg = LogisticRegression()
```

2. EVALUATION
```python
def test_model():
    test_model = []
    test_model.append(input())
    test_Vecteurs = Vecteurs.transform(test_model)
    predLabel = Reg.predict(test_Vecteurs)
    Classes = ['Negative','Positive']
    print("Votre commentaire est ",Classes[predLabel[0]])
```