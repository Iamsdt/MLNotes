# Data clean technique

Steps 1:
- Explore the data in the column
- Identify pattern and classes
- Remove no digit characters
- Convert the column to a numeric data type
- Rename columns if required


# Replace string
```
laptops["ram"] = laptops["ram"].str.replace('GB','')
```

# Convert to Number
```
laptops['ram'] = laptops['ram'].astype(float)
```

# Rename column name
```
laptops.rename({'ram':'ram_gb'}, axis=1, inplace=True)
```

# Extract String into new Columns
```
laptops['cpu_manufacturer'] = laptops['cpu'].str.split().str[0]
```

# Correcting Values
```
mapping_dict = {
    'Android': 'Android',
    'Chrome OS': 'Chrome OS',
    'Linux': 'Linux',
    'Mac OS': 'macOS',
    'No OS': 'No OS',
    'Windows': 'Windows',
    'macOS': 'macOS'
}

laptops['os'] = laptops['os'].map(mapping_dict)
```

# Remove Null value
from row 
```
laptops.dropna()
```
From Columns
```
laptops.dropna(axis=1)
```

# Filling Missing value
```
no_os = laptops['os'] == 'No OS'

laptops.loc[no_os, 'os_version'] = 'Version Unknown'
```

# Produce new CSV file
```
laptops.to_csv('laptops_cleaned.csv', index=False)
```