# Notes from a hackathon

Notes from a hackathon.

# Reading a .pickle file

A starting point was files prepared for the event. These were copied to
the route of the project with bash as follows:

``` {bash}
mkdir data
mv -v ~/Downloads/*.pickle data
```

We can list the pickle files as follows:

``` python
import os
# List pickle files in route directory:
for file in os.listdir('data'):
    print(file)
```

    AA_example_links.pickle
    AA_example_key_nodes.pickle

``` python
import pickle
# Read the first pickle file:
with open('data/AA_example_links.pickle', 'rb') as f:
    links = pickle.load(f)
```

Show what’s in the links object, with output showning first 80
characters:

``` python
# Find length of links:
len(links)
links.__class__
links.__sizeof__()
links_items = links.items()
links_items.__class__
# links_items[:10]
# Convert dict to list:
links_list = list(links_items)
links_list.__class__
len(links_list)
# Convert list to character string:
links_str = str(links_list)
links_str[:80]
```

    "[('332550_436550', [[245949.0, 2524482.0, 3770702.0, 1557159.0, 244653.0, 604353"
