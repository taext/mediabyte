

```python
from mediabyte import omm
```

## Basic Mixtape Operations

We first create two `Sample` objects:


```python
mySample = omm('y.R2ipPgrWypI.5m.James Powell: Advanced Metaphors in Python.lecture.coding.7m')
```


```python
mySample
```




    James Powell: Advanced Metaphors in Python  (lecture, coding)  2m




```python
mySecondSample = omm('y.4t1K66dMhWk.1m9s.Def Con 26 Josh Mitchell: Critical Issues with Police Cameras.security.lecture.45m47s')
```


```python
mySecondSample
```




    Def Con 26 Josh Mitchell: Critical Issues with Police Cameras  (security, lecture)  44m38s



**The `+` operator creates a `Mixtape`** for any combination of `Yota`, `Cue` or `Sample`.

We create a `Mixtape` using the `+` operator:


```python
myMixtape = mySample + mySecondSample
```


```python
myMixtape
```




    0. James Powell: Advanced Metaphors in Python
    1. Def Con 26 Josh Mitchell: Critical Issues with Police Cameras



`Yota`, `Cue` and `Sample` objects can be added to a `Mixtape` using the `+` operator:


```python
myYota = omm('https://www.youtube.com/watch?v=X34taF1R7sU')
```


```python
myYota.title = 'Funny Clip'
```


```python
myMixtape += myYota
```


```python
myMixtape
```




    0. James Powell: Advanced Metaphors in Python
    1. Def Con 26 Josh Mitchell: Critical Issues with Police Cameras
    2. Funny Clip



A `Mixtape` can be accessed by indexing:


```python
myMixtape[1]
```




    Def Con 26 Josh Mitchell: Critical Issues with Police Cameras  (security, lecture)  44m38s



A `Mixtape` can be sliced:


```python
myMixtape[1:]
```




    0. Def Con 26 Josh Mitchell: Critical Issues with Police Cameras
    1. Funny Clip



Items in a `Mixtape` can be deleted with the `del` command:


```python
del myMixtape[0]
```


```python
myMixtape
```




    0. Def Con 26 Josh Mitchell: Critical Issues with Police Cameras
    1. Funny Clip


