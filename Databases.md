---
layout: default
title: Databases
---

# Databases

Here you can find a number of compound databases that you can download for use in your own project work.


#### Smiles files:

These are files that contain the SMILES and corresponding CODE's of the compounds that can be purchased from the given vendors. Each line
is composed of the following format:

```bash
$ gunzip -c asinex.smi.gz | head -3
COc1cc(N/N=C/c2ccccc2O)ncn1	BAS-00132206
C#Cc1ccc(C#C)cc1	BAS-00293357
Cc1nonc1OCCn1c([N+](=O)[O-])cnc1C	BAS-00505574
```

- <a href="Databases/asinex.smi.gz" download>asinex.smi.gz (575,299 compounds)</a>
- <a href="Databases/chembridge.smi.gz" download>chembridge.smi.gz (790,403 compounds)</a>
- <a href="Databases/chemdiv.smi.gz" download>chemdiv.smi.gz (1,133,904 compounds)</a>
- <a href="Databases/chemspace.1.smi.gz" download>chemspace.1.smi.gz (800,299 compounds)</a>
- <a href="Databases/chemspace.2.smi.gz" download>chemspace.2.smi.gz (800,299 compounds)</a>
- <a href="Databases/chemspace.3.smi.gz" download>chemspace.3.smi.gz (800,299 compounds)</a>
- <a href="Databases/chemspace.4.smi.gz" download>chemspace.4.smi.gz (800,299 compounds)</a>
- <a href="Databases/chemspace.5.smi.gz" download>chemspace.5.smi.gz (800,299 compounds)</a>
- <a href="Databases/chemspace.6.smi.gz" download>chemspace.6.smi.gz (800,299 compounds)</a>
- <a href="Databases/chemspace.7.smi.gz" download>chemspace.7.smi.gz (800,299 compounds)</a>
- <a href="Databases/chemspace.8.smi.gz" download>chemspace.8.smi.gz (800,299 compounds)</a>
- <a href="Databases/chemspace.9.smi.gz" download>chemspace.9.smi.gz (800,295 compounds)</a>
- <a href="Databases/enamine.1.smi.gz" download>enamine.1.smi.gz (457,757 compounds)</a>
- <a href="Databases/enamine.2.smi.gz" download>enamine.2.smi.gz (457,757 compounds)</a>
- <a href="Databases/enamine.3.smi.gz" download>enamine.3.smi.gz (457,757 compounds)</a>
- <a href="Databases/enamine.4.smi.gz" download>enamine.4.smi.gz (457,757 compounds)</a>
- <a href="Databases/enamine.5.smi.gz" download>enamine.5.smi.gz (457,757 compounds)</a>
- <a href="Databases/enamine.6.smi.gz" download>enamine.6.smi.gz (457,757 compounds)</a>
- <a href="Databases/enamine.7.smi.gz" download>enamine.7.smi.gz (457,757 compounds)</a>
- <a href="Databases/enamine.8.smi.gz" download>enamine.8.smi.gz (457,757 compounds)</a>
- <a href="Databases/enamine.9.smi.gz" download>enamine.9.smi.gz (457,752 compounds)</a>
- <a href="Databases/lifechemicals.smi.gz" download>lifechemicals.smi.gz (545,400 compounds)</a>

It may be that identical compounds can be found across multiple databases, so before using a filtering step should be implemented to keep only the unique compounds. This can be done in multiple ways, but a common one is to read files into a Python script and keep only the unique ones using a dictionary in which the keys are the SMILES and the values are the CODE's:

```python
import gzip

SMILES2CODE = {}
filenames = ['asinex.smi.gz', 'chembridge.smi.gz', 'chemdiv.smi.gz', 'lifechemicals.smi.gz']
for filename in filenames:
	with gzip.open(filename,'rt') as f:
		for LINE in f.readlines():
			LINE = LINE.strip()
			if LINE is None or LINE == "": continue
			FIELDS = LINE.split()
			if len(FIELDS) != 2: continue
			SMILES = FIELDS[0]
			CODE = FIELDS[1]
			SMILES2CODE[SMILES] = CODE

for i in range(1,10):
	with gzip.open("chemspace.%d.smi.gz" % (i),'rt') as f:
		for LINE in f.readlines():
			LINE = LINE.strip()
			if LINE is None or LINE == "": continue
			FIELDS = LINE.split()
			if len(FIELDS) != 2: continue
			SMILES = FIELDS[0]
			CODE = FIELDS[1]
			SMILES2CODE[SMILES] = CODE
			
for i in range(1,10):
	with gzip.open("enamine.%d.smi.gz" % (i),'rt') as f:
		for LINE in f.readlines():
			LINE = LINE.strip()
			if LINE is None or LINE == "": continue
			FIELDS = LINE.split()
			if len(FIELDS) != 2: continue
			SMILES = FIELDS[0]
			CODE = FIELDS[1]
			SMILES2CODE[SMILES] = CODE
	
fo = open("merged.smi", "w")
for SMILES, CODE in SMILES2CODE.items(): fo.write("%s\t%s\n" % (SMILES, CODE))
fo.close()
```

You can download these files by clicking the links, or using the following commands from within a Python script (exemplified for the Asinex library):

```python
import requests
import gzip
from io import BytesIO

url = "https://raw.githubusercontent.com/UAMCAntwerpen/2040FBDBIC/master/Databases/asinex.smi.gz"
response = requests.get(url)
response.raise_for_status()  # ensure download succeeded

with gzip.open(BytesIO(response.content), mode='rt', encoding='utf-8') as f:
    lines = f.read().splitlines()

print(lines[:5])  # preview first 5 lines
```

