# Pràctica Kaggle APC UAB 2022-23 ### Nom: *****
### DATASET: Credit Card Fraud Detection
### URL: [kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
## Resum
El dataset utilitza dades de transaccions realitzades amb targetes de crédit en septembre de 2013 per titulars de targetes europeas.
Tenim 284807 dades amb 31 atributs. Dels 31 atributs, l'atribut Class és categoric i es el que anomoenarem atribut objectiu. Els altres atributs són numerics.
El nostre atribut objectiu pot tenir dos valors que son 1 o 0. Si el valor es 1 vol dir que aquella transacció es fraudulenta i si el valor es 0 vol dir que la transacció es correcta. L'atribut Amount, indica l'import de la transacció. L'atribut Time es inidica el temps entre una transsació i la primera transsació. Per últim, els atributs de V1 a V28 son funcions numériques que son el resultat de la transformació PCA. 

### Objectius del dataset Volem aprender quina és la ...
Volem aprender quin és el millor model que prediu si una transacció es fraudulenta o no.

## Experiments
Durant aquesta pràctica he realitzat diferents execucions amb múltiples models, tals com:
* Regrsssor Logístic
* KNearest
* Suported Vector Classfication
* DecisionTreeClassifier

### Preprocessat
El principal problema d'aquest dataset esque estaba molt desbalancejat(99.83% són de classe 0 i 0.17% són de clase 1). LLavors per poder fer els experiments de forma més efectiva i que els resultats fosin els més precisos posibles he balancejat el dataset. He utilitzat un subsample aleatori, en el que les clases son 50% i 50%. 
A més el dataset no conté valors Nulls per tant no he tingut que tractar aixó. Per últim he estandaritzat  els atributs Time i Amount ja que no ho estaven a diferencia  dels atributs V1-28. 

### Model
A continuació mostraré els resultats de els diferents models. 

| Model | Preprocessing | Accuracy | Precision | Recall | F1-Score |
| -- | -- | -- | -- | -- | -- |
| Regresor Logístic | Estandarització | 96% | 99% | 93% | 96% |
| KNearest| Estandarització | 95% | 98% | 93% | 95% |
| Support Vector Classifier | Estandarització | 94% | 100% | 88% | 94% |
| DecisionTreeClassifier| Estandarització | 89% | 86% | 93% | 89% |

| Model | Preprocessing | Hiperparametres | Mètrica | Temps |
| -- | -- | -- | -- | -- |
| Regresor Logístic | Estandarització | penalty: l2, solver: newton-cg, warm_start: True | 98.30 % | 1.87 s |
| Gradient Descent | Estandarització | 'alpha': 0.001, 'class_weight': 'balanced', 'fit_intercept': True, 'learning_rate': 'optimal', 'loss': 'log', 'max_iter': 5000, 'penalty': 'l2', 'shuffle': True, 'warm_start': 'True' | 98.24 % | 4.78 s |
| SVC | Estandarització | 'class_weight': 'balanced', 'gamma': 'scale', 'kernel': 'linear' | 98.30 % | 1.37 s |
| Random Forest | default | 'balanced_subsample', 'criterion': 'gini', 'max_features': 'auto', 'n_estimators': 75, 'warm_start': True | 98.91 % | 101.31 s |
| Naive Bayes | Feature Selection | default | 97.25 % | 0.01 s |

Aquells valors marcats com a 'default' signifiquen que no s'ha realitzat cap tipus de modificació. Per exemple, 'default' en preprocessing indica que no s'han tractat les dades i en hipermaràmetres inica que s'ha utilitzat la configuració per defecte del model.

## Demo
Per tal de fer una prova, es pot fer servir amb la següent comanda ``` python3 demo/demo.py --input here ```

## Conclusions
El millor model que s'ha aconseguit ha estat...
En comparació amb l'estat de l'art i els altres treballs que hem analitzat....
## Idees per treballar en un futur
Crec que seria interesant indagar més en...

## Llicencia
El projecte s’ha desenvolupat sota llicència ZZZz.
