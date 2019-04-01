

```python
from mediabyte import omm
```

## Mediabyte Hash Referencing

Every mediabyte parsed by the system can be accessed later by `o.mediabytehash` referencing.

The hash can be viewed using `mediabyteObj.hash()`.

<br>


```python
cd ../mixtapes/
```

We load a **Mixtape** from file using `omm()`:


```python
myMix = omm('hackers2018.omm')
```

thereby making the system aware of its existence and **Sample** hashes.


```python
myMix
```




    0. No Retreat No Surrender
    1. La theorie synthetique
    2. John Oliver: The Lottery
    3. John Oliver: Trade



We check the first **Sample** hash for reference:


```python
omm('hackers2018.omm')[0].hash()
```




    'f41a5c90d4f'



With this hash we can reference it later using `omm()`.

Enough characters to uniquely identify will suffice:


```python
omm('o.f41')
```




    No Retreat No Surrender  (movie, full)  30s



If multiple matches are found, the system informs us:


```python
omm('o.f4')
```




    'Multiple matches, please add characters and try again'



<br>

### Native o.mediabytehash support

Importing `MediabyteHashObj` allows for native `o.mediabytehash` referencing:


```python
from mediabyte import MediabyteHashObj
```


```python
o = MediabyteHashObj()
```


```python
o.f41a5c90d4f                            # note that the full hash is used here
```




    'y.meq3Dn3TNs8.22s.No_Retreat_No_Surrender.movie.full.52s'



As seen above, native `o.mediabytehash` referencing returns the mediabyte string and can be used as such:


```python
omm(o.f41a5c90d4f)
```




    No Retreat No Surrender  (movie, full)  30s


