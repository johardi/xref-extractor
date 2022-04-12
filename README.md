# Ontology Cross-References API

The API provides the methods to find mappings (or cross-references) between terms from ontologies and coding standards. The API uses data extracted from a variety of biomedical ontologies that contain cross-references information.

## Data collection pipeline

### Prerequisite

The pipeline requires some third-party software programs that you will need to install them first:
1. ROBOT tool (http://robot.obolibrary.org/)
2. CSVJSON (https://csvjson.com/)
3. JQ (https://stedolan.github.io/jq/)

### Running the pipeline

Clone the repository:

```
$ git clone https://github.com/johardi/xref-extractor.git
$ cd xref-extractor
```

Type the command below:

```
$ make xref_all
```

## Client API

### Prerequisite

The client module requires Python 3.x

### Example code

```python
from backend import ConnectionManager

con_mngr = ConnectionManager.init("/path/to/xref-all.json")
con = con_mngr.get_connection()
service = con.get_service("XrefService")

# Find ICD10CM code for 'EFO:0000095'"
service.find_xref("EFO:0000095", "ICD10CM")

# Find DOID code for 'MONDO:0004948'"
service.find_xref("MONDO:0004948", "DOID")
```

