# Selecting Columns and Custom Slicing ndarray
### Select multiple specific columns

```
cols = [1, 2, 5]
data = data_np[:, cols]
```

### Selecting 1D slice
#### row
```
data_np[2, 1:4]
```
#### Columns
```
data_np[1:4, 2]
```

### select a 2D slice
```
data_np[1:4, 2:4]
```

# Calculating statistics of ndarray
### Getting max of each row
```
data_np.max(axis=1)
```
### Getting max of each columns
```
data_np.max(axis=0)
```

# Boolean Indexing
take threshold value with selected columns
```
tip_bool = tip_amount > 50

top_tips = taxi[tip_bool, 5:14]
```

# Read from csv
```
np.genfromtxt('nyc_taxis.csv', delimiter=',')
```

# Concat
For concat 3 methods available
- concatenate
- vstack for column wise
- hstack for row wise
- r_ for column wise
- c_ for row wise

# Save and load
save as csv
```
np.savetxt('data.csv', data, delimiter=',')
```

Save as npy
```
np.save('data.npy', data)
```

Save multiple arrary as same time
```
np.savez('data.npz', data)
```

## Load
load csv file is as usual

load npy file
```
d = np.load('data.npy')
d
```

load npz file
it's return list of files
```
d2 = np.load('data.npz')
name = d.files[0]
d2[name]
```