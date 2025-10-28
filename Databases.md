---
layout: default
title: Databases
---

# Databases

Here you can find a number of compound databases that you can download for use in your own project work. These are files that contain the ```SMILES``` and corresponding ```CODE``` of the compounds that can be purchased from the given vendors. Each line is composed of the following format:

```bash
$ gunzip -c asinex.smi.gz | head -1
COc1cc(N/N=C/c2ccccc2O)ncn1	BAS-00132206
```

- <a href="Databases/asinex.smi.gz" download>asinex.smi.gz</a> (575,299 compounds)
- <a href="Databases/chembridge.smi.gz" download>chembridge.smi.gz</a> (790,403 compounds)
- <a href="Databases/chemdiv.smi.gz" download>chemdiv.smi.gz</a> (1,133,904 compounds)
- <a href="Databases/chemspace.1.smi.gz" download>chemspace.1.smi.gz</a> (800,299 compounds)
- <a href="Databases/chemspace.2.smi.gz" download>chemspace.2.smi.gz</a> (800,299 compounds)
- <a href="Databases/chemspace.3.smi.gz" download>chemspace.3.smi.gz</a> (800,299 compounds)
- <a href="Databases/chemspace.4.smi.gz" download>chemspace.4.smi.gz</a> (800,299 compounds)
- <a href="Databases/chemspace.5.smi.gz" download>chemspace.5.smi.gz</a> (800,299 compounds)
- <a href="Databases/chemspace.6.smi.gz" download>chemspace.6.smi.gz</a> (800,299 compounds)
- <a href="Databases/chemspace.7.smi.gz" download>chemspace.7.smi.gz</a> (800,299 compounds)
- <a href="Databases/chemspace.8.smi.gz" download>chemspace.8.smi.gz</a> (800,299 compounds)
- <a href="Databases/chemspace.9.smi.gz" download>chemspace.9.smi.gz</a> (800,295 compounds)
- <a href="Databases/enamine.1.smi.gz" download>enamine.1.smi.gz</a> (457,757 compounds)
- <a href="Databases/enamine.2.smi.gz" download>enamine.2.smi.gz</a> (457,757 compounds)
- <a href="Databases/enamine.3.smi.gz" download>enamine.3.smi.gz</a> (457,757 compounds)
- <a href="Databases/enamine.4.smi.gz" download>enamine.4.smi.gz</a> (457,757 compounds)
- <a href="Databases/enamine.5.smi.gz" download>enamine.5.smi.gz</a> (457,757 compounds)
- <a href="Databases/enamine.6.smi.gz" download>enamine.6.smi.gz</a> (457,757 compounds)
- <a href="Databases/enamine.7.smi.gz" download>enamine.7.smi.gz</a> (457,757 compounds)
- <a href="Databases/enamine.8.smi.gz" download>enamine.8.smi.gz</a> (457,757 compounds)
- <a href="Databases/enamine.9.smi.gz" download>enamine.9.smi.gz</a> (457,752 compounds)
- <a href="Databases/lifechemicals.smi.gz" download>lifechemicals.smi.gz</a> (545,400 compounds)

You can download these files by clicking the links, or by using the following commands from within a ```python``` script (exemplified for the Asinex library):

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

It may be that identical compounds can be found across multiple databases, so before using a filtering step should be implemented to keep only the unique compounds. This can be done in multiple ways, but a common one is to read files into a Python script and keep only the unique ones using a dictionary in which the key is the ```SMILES``` and the value is the ```CODE``` of each compound:

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

