# Datensatz

```python
import pandas as pd
gammas = pd.read_csv('gamma.txt', delim_space=True).loc[:,'gamma']
```

# Absoluter Fehler

```python
gammas.std() / np.sqrt(gammas.size)
```

# Relativer Fehler

```python
gammas.std() / np.sqrt(gammas.size) / gammas.mean()
```

# t-Test

Nullhypothese: μ=1
Alternativhypothese: μ=0

```python
n = gammas.size
t.cdf(x=gammas.mean(), df=n-1, loc=1, scale=gammas.std()/np.sqrt(n))
```

Es wird das Stichproben-Mittel gegen die Nullhypothese (μ=1) geprüft!

# Vertrauensintervall von 95%

```python
n = gammas.size
t.ppf(q=0.95, df=n-1, loc=gammas.mean(), scale=gammas.std()/np.sqrt(n))
```

Es wird geprüft, wo sich mit 95%iger Sicherheit das wahre Mittel bei einem
gegebenen Stichproben-Mittel befindet.
