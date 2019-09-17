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


