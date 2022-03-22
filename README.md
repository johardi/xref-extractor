# Database Cross-References Extractor

This make script will allow you to download biomedical ontologies and extract the database cross-references presented by the `oboInOwl:dbXRef` property.

## Prerequisite

The script is using some third-party software programs that you will need to install them first:
1. ROBOT tool (http://robot.obolibrary.org/)
2. CSVJSON (https://csvjson.com/)
3. JQ (https://stedolan.github.io/jq/)

## Usage

Clone the repository:

```
$ git clone https://github.com/johardi/xref-extractor.git
$ cd xref-extractor
```

Type the command below:

```
$ make xref_all
```

Additionally, you can generate a specific cross-reference (xref) mapping that covers a particular ontology. For example, the command below will generate the xref mapping for the Human Phenotype (HP) ontology only:

```
$ make ONT=HP xref-hp-only
```

To skip downloading the ontology over-and-over again, use the parameter `MIR=false`, as follows:

```
$ make MIR=false ONT=HP xref-hp-only -B
```
