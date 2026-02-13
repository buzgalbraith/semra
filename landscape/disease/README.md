# SeMRA Disease Mappings Database

Supports the analysis of the landscape of disease nomenclature resources.
Created by:

<ul>
<li>
<a href="https://bioregistry.io/orcid:0000-0003-4423-4370">
Charles Tapley Hoyt (orcid:0000-0003-4423-4370)
</a>
</li>
</ul>

Artifacts from this resource can be downloaded from Zenodo at
[![](https://zenodo.org/badge/DOI/10.5281/zenodo.11091885.svg)](https://doi.org/10.5281/zenodo.11091885).

## Reproduction

The SeMRA Disease Mappings Database can be rebuilt with the following commands:

```console
$ git clone https://github.com/biopragmatics/semra.git
$ cd semra
$ uv pip install .[landscape]
$ python -m semra.landscape.disease
```

Note that downloading raw data resources can take on the order of hours to tens
of hours depending on your internet connection and the reliability of the
resources' respective servers.

Processing and analysis can be run overnight on commodity hardware (e.g., a 2023
MacBook Pro with 36GB RAM).

## Resource Summary

The following resources are represented in processed mappings generated. They
are summarized in the following table that includes their
[Bioregistry](https://bioregistry.io) prefix, license, current version, and
number of terms (i.e., named concepts) they contain.

4 resources were not available through
[PyOBO](https://github.com/biopragmatics/pyobo). Therefore, the number of terms
in that resource are estimated based on the ones that are observed in mappings
assembled by SeMRA. Note that these are typically an underestimate.

| prefix        | name                                                                             | license                                                                                                  | version    |  terms | status   |
| :------------ | :------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------- | :--------- | -----: | :------- |
| doid          | Human Disease Ontology                                                           | CC0-1.0                                                                                                  | 2026-02-02 |  14521 | full     |
| mondo         | Mondo Disease Ontology                                                           | CC-BY-4.0                                                                                                | 2026-01-06 |  30384 | full     |
| efo           | Experimental Factor Ontology                                                     | Apache-2.0                                                                                               | 3.86.0     |   2108 | subset   |
| mesh          | Medical Subject Headings                                                         | CC0-1.0                                                                                                  | 2026       |   3162 | subset   |
| ncit          | NCI Thesaurus                                                                    | CC-BY-4.0                                                                                                | 26.02b     |  21845 | subset   |
| orpha         | Orphanet                                                                         | CC-BY-4.0                                                                                                |            |  15288 | observed |
| orphanet      | Orphanet                                                                         | CC-BY-4.0                                                                                                |            |      0 | observed |
| orphanet.ordo | Orphanet Rare Disease Ontology                                                   | CC-BY-4.0                                                                                                | 4.7        |      0 | observed |
| umls          | Unified Medical Language System Concept Unique Identifier                        | https://www.nlm.nih.gov/research/umls/knowledge_sources/metathesaurus/release/license_agreement.html     | 2025AB     | 191213 | subset   |
| omim          | Online Mendelian Inheritance in Man                                              | https://www.omim.org/help/agreement                                                                      | 2026-02-12 |  15380 | observed |
| omim.ps       | OMIM Phenotypic Series                                                           | https://www.omim.org/help/agreement                                                                      | 2026-02-12 |    610 | full     |
| medgen        | Human Medical Genetics                                                           |                                                                                                          |            |  21440 | observed |
| gard          | Genetic and Rare Diseases Information Center                                     |                                                                                                          |            |   6097 | full     |
| icd10         | International Classification of Diseases, 10th Revision                          | https://cdn.who.int/media/docs/default-source/publishing-policies/copyright/who-faq-licensing-icd-10.pdf | 2019       |   6838 | observed |
| icd10cm       | International Classification of Diseases, 10th Revision, Clinical Modification   | CC BY-ND 3.0 IGO                                                                                         |            |  21979 | observed |
| icd10pcs      | International Classification of Diseases, 10th Revision, Procedure Coding System |                                                                                                          |            |      0 | observed |
| icd11         | International Classification of Diseases, 11th Revision (Foundation Component)   | CC-BY-ND-3.0-IGO                                                                                         | 2025-01    |   4636 | observed |
| icd11.code    | ICD 11 Codes                                                                     | http://www.who.int/about/licensing/copyright_form/en                                                     |            |      0 | observed |
| icd9          | International Classification of Diseases, 9th Revision                           | CC BY-ND 3.0 IGO                                                                                         |            |   3993 | observed |
| icd9cm        | International Classification of Diseases, 9th Revision, Clinical Modification    | CC BY-ND 3.0 IGO                                                                                         |            |   9132 | observed |
| icdo          | International Classification of Diseases for Oncology                            | CC BY-ND 3.0 IGO                                                                                         |            |    798 | observed |

There are a total of 369,424 terms across the 21 resources.

## Mapping Summary and Usage

### Raw Mappings

The raw mappings are the ones directly read from the 9 sources.

- This table is symmetric, i.e., taking into account mappings from both the
  source and target.
- Diagonals represent the number of entities in the resource (or the number that
  are observed in the mappings, in some cases)
- All predicate types are combined in this table.

| source_prefix |  doid | mondo |  efo | mesh |  ncit | orpha | orphanet | orphanet.ordo |   umls |  omim | omim.ps | medgen |  gard | icd10 | icd10cm | icd10pcs | icd11 | icd11.code | icd9 | icd9cm | icdo |
| :------------ | ----: | ----: | ---: | ---: | ----: | ----: | -------: | ------------: | -----: | ----: | ------: | -----: | ----: | ----: | ------: | -------: | ----: | ---------: | ---: | -----: | ---: |
| doid          | 14521 | 11940 | 1233 |  630 |  4633 |  2244 |        0 |             0 |   6807 |  5962 |       0 |      6 |  2143 |     1 |    3545 |        0 |     2 |          0 |   11 |   2225 |  492 |
| mondo         | 11940 | 30384 | 1447 |  864 |  7118 | 10344 |        0 |             0 |  19450 | 10093 |     606 |  21440 | 10730 |   209 |    2564 |        0 |  4636 |          0 | 4415 |      2 |  725 |
| efo           |  1233 |  1447 | 2108 |  435 |  1087 |   362 |        0 |             0 |   1336 |   311 |      23 |   1345 |   288 |   673 |     453 |        0 |   483 |          0 | 1209 |      5 |   61 |
| mesh          |   630 |   864 |  435 | 3162 |    27 |   171 |        0 |             0 |   2135 |     0 |       0 |      0 |     0 |     0 |       0 |        0 |     0 |          0 |    0 |      0 |    0 |
| ncit          |  4633 |  7118 | 1087 |   27 | 21845 |    37 |        0 |             0 |  20535 |     0 |       0 |      0 |     0 |     0 |       0 |        0 |     0 |          0 |    0 |      0 |    0 |
| orpha         |  2244 | 10344 |  362 |  171 |    37 | 15288 |        0 |             0 |   9028 | 11625 |       5 |      4 |    39 |  7879 |       0 |        0 |     1 |          0 |    6 |      0 |    1 |
| orphanet      |     0 |     0 |    0 |    0 |     0 |     0 |        0 |             0 |      0 |     0 |       0 |      0 |     0 |     0 |       0 |        0 |     0 |          0 |    0 |      0 |    0 |
| orphanet.ordo |     0 |     0 |    0 |    0 |     0 |     0 |        0 |             0 |      0 |     0 |       0 |      0 |     0 |     0 |       0 |        0 |     0 |          0 |    0 |      0 |    0 |
| umls          |  6807 | 19450 | 1336 | 2135 | 20535 |  9028 |        0 |             0 | 191213 | 13542 |       0 |      0 |     0 |  6082 |   25384 |        0 |     0 |          0 |    0 |   9006 |    0 |
| omim          |  5962 | 10093 |  311 |    0 |     0 | 11625 |        0 |             0 |  13542 | 15380 |       0 |      0 |     0 |     0 |       0 |        0 |     0 |          0 |    0 |      0 |    0 |
| omim.ps       |     0 |   606 |   23 |    0 |     0 |     5 |        0 |             0 |      0 |     0 |     610 |      0 |     0 |     0 |       0 |        0 |     0 |          0 |    0 |      0 |    0 |
| medgen        |     6 | 21440 | 1345 |    0 |     0 |     4 |        0 |             0 |      0 |     0 |       0 |  21440 |     0 |     0 |       0 |        0 |     0 |          0 |    0 |      0 |    0 |
| gard          |  2143 | 10730 |  288 |    0 |     0 |    39 |        0 |             0 |      0 |     0 |       0 |      0 |  6097 |     0 |       0 |        0 |     0 |          0 |    0 |      0 |    0 |
| icd10         |     1 |   209 |  673 |    0 |     0 |  7879 |        0 |             0 |   6082 |     0 |       0 |      0 |     0 |  6838 |       0 |        0 |     0 |          0 |    0 |      0 |    0 |
| icd10cm       |  3545 |  2564 |  453 |    0 |     0 |     0 |        0 |             0 |  25384 |     0 |       0 |      0 |     0 |     0 |   21979 |        0 |     0 |          0 |    0 |      0 |    0 |
| icd10pcs      |     0 |     0 |    0 |    0 |     0 |     0 |        0 |             0 |      0 |     0 |       0 |      0 |     0 |     0 |       0 |        0 |     0 |          0 |    0 |      0 |    0 |
| icd11         |     2 |  4636 |  483 |    0 |     0 |     1 |        0 |             0 |      0 |     0 |       0 |      0 |     0 |     0 |       0 |        0 |  4636 |          0 |    0 |      0 |    0 |
| icd11.code    |     0 |     0 |    0 |    0 |     0 |     0 |        0 |             0 |      0 |     0 |       0 |      0 |     0 |     0 |       0 |        0 |     0 |          0 |    0 |      0 |    0 |
| icd9          |    11 |  4415 | 1209 |    0 |     0 |     6 |        0 |             0 |      0 |     0 |       0 |      0 |     0 |     0 |       0 |        0 |     0 |          0 | 3993 |      0 |    0 |
| icd9cm        |  2225 |     2 |    5 |    0 |     0 |     0 |        0 |             0 |   9006 |     0 |       0 |      0 |     0 |     0 |       0 |        0 |     0 |          0 |    0 |   9132 |    0 |
| icdo          |   492 |   725 |   61 |    0 |     0 |     1 |        0 |             0 |      0 |     0 |       0 |      0 |     0 |     0 |       0 |        0 |     0 |          0 |    0 |      0 |  798 |

The raw mappings can be downloaded from
[![](https://zenodo.org/badge/DOI/10.5281/zenodo.11091885.svg)](https://doi.org/10.5281/zenodo.11091885).
then can be accessed via the [SeMRA](https://github.com/biopragmatics/semra)
Python Package using the following examples:

```python
import semra

# Load from JSONL
mappings_from_jsonl = semra.from_jsonl("raw.jsonl.gz")

# Load from SSSOM
mappings_from_sssom = semra.from_sssom("raw.sssom.tsv.gz")
```

<details>
<summary>Graph-based view of raw mappings</summary>

Note that this may contain many more prefixes than what's relevant for
processing. The configuration allows for specifying a prefix allowlist and
prefix blocklist.

![](raw_graph.svg)

</details>

### Processed Mappings

The processed mappings result from the application of inference, reasoning, and
confidence filtering. Before processing, only mappings with subjects and objects
whose references both use the following prefixes were retained:

<ul>
<li>doid</li>
<li>mondo</li>
<li>efo</li>
<li>mesh</li>
<li>ncit</li>
<li>orpha</li>
<li>orphanet</li>
<li>orphanet.ordo</li>
<li>umls</li>
<li>omim</li>
<li>omim.ps</li>
<li>medgen</li>
<li>gard</li>
<li>icd10</li>
<li>icd10cm</li>
<li>icd10pcs</li>
<li>icd11</li>
<li>icd11.code</li>
<li>icd9</li>
<li>icd9cm</li>
<li>icdo</li>
</ul>
The following prior knowledge was used during processing:

<table>
<thead>
<tr>
<th>Source Prefix</th>
<th>Target Prefix</th>
<th>Old Predicate</th>
<th>New Predicate</th>
<th align="right">Confidence</th>
</tr>
</thead>
<tbody>
<tr>
<td>doid</td>
<td>(all)</td>
<td>oboinowl:hasDbXref</td>
<td>skos:exactMatch</td>
<td align="right">0.95</td>
</tr>
<tr>
<td>mondo</td>
<td>(all)</td>
<td>oboinowl:hasDbXref</td>
<td>skos:exactMatch</td>
<td align="right">0.95</td>
</tr>
<tr>
<td>efo</td>
<td>(all)</td>
<td>oboinowl:hasDbXref</td>
<td>skos:exactMatch</td>
<td align="right">0.9</td>
</tr>
<tr>
<td>ncit</td>
<td>(all)</td>
<td>oboinowl:hasDbXref</td>
<td>skos:exactMatch</td>
<td align="right">0.7</td>
</tr>
<tr>
<td>umls</td>
<td>(all)</td>
<td>oboinowl:hasDbXref</td>
<td>skos:exactMatch</td>
<td align="right">0.7</td>
</tr>
<tr>
<td>orphanet.ordo</td>
<td>(all)</td>
<td>oboinowl:hasDbXref</td>
<td>skos:exactMatch</td>
<td align="right">0.7</td>
</tr>
<tr>
<td>orphanet</td>
<td>(all)</td>
<td>oboinowl:hasDbXref</td>
<td>skos:exactMatch</td>
<td align="right">0.7</td>
</tr>
</tbody>
</table>
After processing, only mappings with subjects and objects whose references both
use the following prefixes were retained:

<ul>
<li>doid</li>
<li>mondo</li>
<li>efo</li>
<li>mesh</li>
<li>ncit</li>
<li>orpha</li>
<li>orphanet</li>
<li>orphanet.ordo</li>
<li>umls</li>
<li>omim</li>
<li>omim.ps</li>
<li>medgen</li>
<li>gard</li>
<li>icd10</li>
<li>icd10cm</li>
<li>icd10pcs</li>
<li>icd11</li>
<li>icd11.code</li>
<li>icd9</li>
<li>icd9cm</li>
<li>icdo</li>
</ul>

The processed mappings table has the following qualities:

- This table is symmetric, i.e., taking into account mappings from the source,
  target, and inference
- Diagonals represent the number of entities in the resource (or the number that
  are observed in the mappings, in some cases)
- Only exact matches are retained

| source_prefix |  doid | mondo |  efo | mesh |  ncit | orpha | orphanet | orphanet.ordo |   umls |  omim | omim.ps | medgen |  gard | icd10 | icd10cm | icd10pcs | icd11 | icd11.code | icd9 | icd9cm | icdo |
| :------------ | ----: | ----: | ---: | ---: | ----: | ----: | -------: | ------------: | -----: | ----: | ------: | -----: | ----: | ----: | ------: | -------: | ----: | ---------: | ---: | -----: | ---: |
| doid          | 14521 | 12347 | 1409 |  772 |  5289 |  2826 |        0 |             0 |   9766 |  6350 |      72 |   5490 |  2541 |  1561 |    3870 |        0 |  1352 |          0 | 2448 |   2749 |  647 |
| mondo         | 12347 | 30384 | 1918 | 1099 |  7701 | 10563 |        0 |             0 |  22634 | 10859 |     634 |  21457 | 11042 |  1876 |    3707 |        0 |  4707 |          0 | 4548 |   2330 |  801 |
| efo           |  1409 |  1918 | 2108 |  456 |  1316 |   449 |        0 |             0 |   2597 |   371 |      28 |   1744 |   410 |  1119 |    1146 |        0 |   597 |          0 | 1343 |    766 |   96 |
| mesh          |   772 |  1099 |  456 | 3162 |   553 |   234 |        0 |             0 |   2563 |    75 |       4 |    804 |   197 |   537 |     738 |        0 |   330 |          0 |  637 |    597 |    4 |
| ncit          |  5289 |  7701 | 1316 |  553 | 21845 |   849 |        0 |             0 |  21963 |   380 |      36 |   4690 |   876 |  1406 |    2008 |        0 |  1180 |          0 | 1533 |   1523 |  532 |
| orpha         |  2826 | 10563 |  449 |  234 |   849 | 15288 |        0 |             0 |   9921 | 11722 |      56 |   2246 |  1840 |  7948 |     738 |        0 |  1020 |          0 |  506 |    442 |   87 |
| orphanet      |     0 |     0 |    0 |    0 |     0 |     0 |        0 |             0 |      0 |     0 |       0 |      0 |     0 |     0 |       0 |        0 |     0 |          0 |    0 |      0 |    0 |
| orphanet.ordo |     0 |     0 |    0 |    0 |     0 |     0 |        0 |             0 |      0 |     0 |       0 |      0 |     0 |     0 |       0 |        0 |     0 |          0 |    0 |      0 |    0 |
| umls          |  9766 | 22634 | 2597 | 2563 | 21963 |  9921 |        0 |             0 | 191213 | 13634 |     105 |  10848 |  2620 |  6188 |   26176 |        0 |  2937 |          0 | 3665 |   9562 |  597 |
| omim          |  6350 | 10859 |  371 |   75 |   380 | 11722 |        0 |             0 |  13634 | 15380 |      47 |   3306 |   549 |   217 |     327 |        0 |   322 |          0 |  266 |    224 |   23 |
| omim.ps       |    72 |   634 |   28 |    4 |    36 |    56 |        0 |             0 |    105 |    47 |     610 |    104 |    40 |    19 |      34 |        0 |    35 |          0 |   20 |     20 |    0 |
| medgen        |  5490 | 21457 | 1744 |  804 |  4690 |  2246 |        0 |             0 |  10848 |  3306 |     104 |  21440 |  2264 |  1733 |    2699 |        0 |  2077 |          0 | 2598 |   2279 |  483 |
| gard          |  2541 | 11042 |  410 |  197 |   876 |  1840 |        0 |             0 |   2620 |   549 |      40 |   2264 |  6097 |   546 |     815 |        0 |   936 |          0 |  621 |    526 |  107 |
| icd10         |  1561 |  1876 | 1119 |  537 |  1406 |  7948 |        0 |             0 |   6188 |   217 |      19 |   1733 |   546 |  6838 |    4270 |        0 |   977 |          0 | 1671 |   2249 |   43 |
| icd10cm       |  3870 |  3707 | 1146 |  738 |  2008 |   738 |        0 |             0 |  26176 |   327 |      34 |   2699 |   815 |  4270 |   21979 |        0 |  1476 |          0 | 2130 |   3529 |   88 |
| icd10pcs      |     0 |     0 |    0 |    0 |     0 |     0 |        0 |             0 |      0 |     0 |       0 |      0 |     0 |     0 |       0 |        0 |     0 |          0 |    0 |      0 |    0 |
| icd11         |  1352 |  4707 |  597 |  330 |  1180 |  1020 |        0 |             0 |   2937 |   322 |      35 |   2077 |   936 |   977 |    1476 |        0 |  4636 |          0 | 1228 |   1120 |   80 |
| icd11.code    |     0 |     0 |    0 |    0 |     0 |     0 |        0 |             0 |      0 |     0 |       0 |      0 |     0 |     0 |       0 |        0 |     0 |          0 |    0 |      0 |    0 |
| icd9          |  2448 |  4548 | 1343 |  637 |  1533 |   506 |        0 |             0 |   3665 |   266 |      20 |   2598 |   621 |  1671 |    2130 |        0 |  1228 |          0 | 3993 |   2370 |   44 |
| icd9cm        |  2749 |  2330 |  766 |  597 |  1523 |   442 |        0 |             0 |   9562 |   224 |      20 |   2279 |   526 |  2249 |    3529 |        0 |  1120 |          0 | 2370 |   9132 |   33 |
| icdo          |   647 |   801 |   96 |    4 |   532 |    87 |        0 |             0 |    597 |    23 |       0 |    483 |   107 |    43 |      88 |        0 |    80 |          0 |   44 |     33 |  798 |

The processed mappings can be downloaded from
[![](https://zenodo.org/badge/DOI/10.5281/zenodo.11091885.svg)](https://doi.org/10.5281/zenodo.11091885).
then can be accessed via the [SeMRA](https://github.com/biopragmatics/semra)
Python Package using the following examples:

```python
import semra

# Load from JSONL
mappings_from_jsonl = semra.from_jsonl("processed.jsonl.gz")

# Load from SSSOM
mappings_from_sssom = semra.from_sssom("processed.sssom.tsv.gz")
```

Below is a graph-based view on the processed mappings.

![](processed_graph.svg)

### Priority Mappings

A prioritization mapping is a special subset of processed mappings constructed
using the prefix priority list. This mapping has the feature that every entity
appears as a subject exactly once, with the object of its mapping being the
priority entity. This creates a "star graph" for each priority entity.

The prioritization for this output is:

<ol>
<li><a href="https://bioregistry.io/doid">Human Disease Ontology (<code>doid</code>)</a></li>
<li><a href="https://bioregistry.io/mondo">Mondo Disease Ontology (<code>mondo</code>)</a></li>
<li><a href="https://bioregistry.io/efo">Experimental Factor Ontology (<code>efo</code>)</a></li>
<li><a href="https://bioregistry.io/mesh">Medical Subject Headings (<code>mesh</code>)</a></li>
<li><a href="https://bioregistry.io/ncit">NCI Thesaurus (<code>ncit</code>)</a></li>
<li><a href="https://bioregistry.io/orpha">Orphanet (<code>orpha</code>)</a></li>
<li><a href="https://bioregistry.io/orphanet">Orphanet (<code>orphanet</code>)</a></li>
<li><a href="https://bioregistry.io/orphanet.ordo">Orphanet Rare Disease Ontology (<code>orphanet.ordo</code>)</a></li>
<li><a href="https://bioregistry.io/umls">Unified Medical Language System Concept Unique Identifier (<code>umls</code>)</a></li>
<li><a href="https://bioregistry.io/omim">Online Mendelian Inheritance in Man (<code>omim</code>)</a></li>
<li><a href="https://bioregistry.io/omim.ps">OMIM Phenotypic Series (<code>omim.ps</code>)</a></li>
<li><a href="https://bioregistry.io/medgen">Human Medical Genetics (<code>medgen</code>)</a></li>
<li><a href="https://bioregistry.io/gard">Genetic and Rare Diseases Information Center (<code>gard</code>)</a></li>
<li><a href="https://bioregistry.io/icd10">International Classification of Diseases, 10th Revision (<code>icd10</code>)</a></li>
<li><a href="https://bioregistry.io/icd10cm">International Classification of Diseases, 10th Revision, Clinical Modification (<code>icd10cm</code>)</a></li>
<li><a href="https://bioregistry.io/icd10pcs">International Classification of Diseases, 10th Revision, Procedure Coding System (<code>icd10pcs</code>)</a></li>
<li><a href="https://bioregistry.io/icd11">International Classification of Diseases, 11th Revision (Foundation Component) (<code>icd11</code>)</a></li>
<li><a href="https://bioregistry.io/icd11.code">ICD 11 Codes (<code>icd11.code</code>)</a></li>
<li><a href="https://bioregistry.io/icd9">International Classification of Diseases, 9th Revision (<code>icd9</code>)</a></li>
<li><a href="https://bioregistry.io/icd9cm">International Classification of Diseases, 9th Revision, Clinical Modification (<code>icd9cm</code>)</a></li>
<li><a href="https://bioregistry.io/icdo">International Classification of Diseases for Oncology (<code>icdo</code>)</a></li>
</ol>

The priority mappings can be downloaded from
[![](https://zenodo.org/badge/DOI/10.5281/zenodo.11091885.svg)](https://doi.org/10.5281/zenodo.11091885).
then can be accessed via the [SeMRA](https://github.com/biopragmatics/semra)
Python Package using the following examples:

```python
import semra
import semra.api

# Load from JSONL
mappings_from_jsonl = semra.from_jsonl("priority.jsonl.gz")

# Load from SSSOM
mappings_from_sssom = semra.from_sssom("priority.sssom.tsv.gz")

# Apply in a data science scenario
df = ...
semra.api.prioritize_df(mappings_from_jsonl, df, column="source_column_id", target_column="target_column_id")
```

## Web Application

1. Download all artifacts from
   [![](https://zenodo.org/badge/DOI/10.5281/zenodo.11091885.svg)](https://doi.org/10.5281/zenodo.11091885)
   into a folder and `cd` into it
2. Run `sh run_on_docker.sh` from the command line
3. Navigate to http://localhost:8773 to see the SeMRA dashboard or to
   http://localhost:7474 for direct access to the Neo4j graph database

## Analyses

### Comparison Analysis

The following comparison shows the absolute number of mappings added by
processing/inference. Across the board, this process adds large numbers of
mappings to most resources, especially ones that were previously only connected
to a small number of other resources.

| source_prefix | doid | mondo |  efo | mesh | ncit | orpha | orphanet | orphanet.ordo |  umls | omim | omim.ps | medgen | gard | icd10 | icd10cm | icd10pcs | icd11 | icd11.code | icd9 | icd9cm | icdo |
| :------------ | ---: | ----: | ---: | ---: | ---: | ----: | -------: | ------------: | ----: | ---: | ------: | -----: | ---: | ----: | ------: | -------: | ----: | ---------: | ---: | -----: | ---: |
| doid          |    0 |   407 |  176 |  142 |  656 |   582 |        0 |             0 |  2959 |  388 |      72 |   5484 |  398 |  1560 |     325 |        0 |  1350 |          0 | 2437 |    524 |  155 |
| mondo         |  407 |     0 |  471 |  235 |  583 |   219 |        0 |             0 |  3184 |  766 |      28 |     17 |  312 |  1667 |    1143 |        0 |    71 |          0 |  133 |   2328 |   76 |
| efo           |  176 |   471 |    0 |   21 |  229 |    87 |        0 |             0 |  1261 |   60 |       5 |    399 |  122 |   446 |     693 |        0 |   114 |          0 |  134 |    761 |   35 |
| mesh          |  142 |   235 |   21 |    0 |  526 |    63 |        0 |             0 |   428 |   75 |       4 |    804 |  197 |   537 |     738 |        0 |   330 |          0 |  637 |    597 |    4 |
| ncit          |  656 |   583 |  229 |  526 |    0 |   812 |        0 |             0 |  1428 |  380 |      36 |   4690 |  876 |  1406 |    2008 |        0 |  1180 |          0 | 1533 |   1523 |  532 |
| orpha         |  582 |   219 |   87 |   63 |  812 |     0 |        0 |             0 |   893 |   97 |      51 |   2242 | 1801 |    69 |     738 |        0 |  1019 |          0 |  500 |    442 |   86 |
| orphanet      |    0 |     0 |    0 |    0 |    0 |     0 |        0 |             0 |     0 |    0 |       0 |      0 |    0 |     0 |       0 |        0 |     0 |          0 |    0 |      0 |    0 |
| orphanet.ordo |    0 |     0 |    0 |    0 |    0 |     0 |        0 |             0 |     0 |    0 |       0 |      0 |    0 |     0 |       0 |        0 |     0 |          0 |    0 |      0 |    0 |
| umls          | 2959 |  3184 | 1261 |  428 | 1428 |   893 |        0 |             0 |     0 |   92 |     105 |  10848 | 2620 |   106 |     792 |        0 |  2937 |          0 | 3665 |    556 |  597 |
| omim          |  388 |   766 |   60 |   75 |  380 |    97 |        0 |             0 |    92 |    0 |      47 |   3306 |  549 |   217 |     327 |        0 |   322 |          0 |  266 |    224 |   23 |
| omim.ps       |   72 |    28 |    5 |    4 |   36 |    51 |        0 |             0 |   105 |   47 |       0 |    104 |   40 |    19 |      34 |        0 |    35 |          0 |   20 |     20 |    0 |
| medgen        | 5484 |    17 |  399 |  804 | 4690 |  2242 |        0 |             0 | 10848 | 3306 |     104 |      0 | 2264 |  1733 |    2699 |        0 |  2077 |          0 | 2598 |   2279 |  483 |
| gard          |  398 |   312 |  122 |  197 |  876 |  1801 |        0 |             0 |  2620 |  549 |      40 |   2264 |    0 |   546 |     815 |        0 |   936 |          0 |  621 |    526 |  107 |
| icd10         | 1560 |  1667 |  446 |  537 | 1406 |    69 |        0 |             0 |   106 |  217 |      19 |   1733 |  546 |     0 |    4270 |        0 |   977 |          0 | 1671 |   2249 |   43 |
| icd10cm       |  325 |  1143 |  693 |  738 | 2008 |   738 |        0 |             0 |   792 |  327 |      34 |   2699 |  815 |  4270 |       0 |        0 |  1476 |          0 | 2130 |   3529 |   88 |
| icd10pcs      |    0 |     0 |    0 |    0 |    0 |     0 |        0 |             0 |     0 |    0 |       0 |      0 |    0 |     0 |       0 |        0 |     0 |          0 |    0 |      0 |    0 |
| icd11         | 1350 |    71 |  114 |  330 | 1180 |  1019 |        0 |             0 |  2937 |  322 |      35 |   2077 |  936 |   977 |    1476 |        0 |     0 |          0 | 1228 |   1120 |   80 |
| icd11.code    |    0 |     0 |    0 |    0 |    0 |     0 |        0 |             0 |     0 |    0 |       0 |      0 |    0 |     0 |       0 |        0 |     0 |          0 |    0 |      0 |    0 |
| icd9          | 2437 |   133 |  134 |  637 | 1533 |   500 |        0 |             0 |  3665 |  266 |      20 |   2598 |  621 |  1671 |    2130 |        0 |  1228 |          0 |    0 |   2370 |   44 |
| icd9cm        |  524 |  2328 |  761 |  597 | 1523 |   442 |        0 |             0 |   556 |  224 |      20 |   2279 |  526 |  2249 |    3529 |        0 |  1120 |          0 | 2370 |      0 |   33 |
| icdo          |  155 |    76 |   35 |    4 |  532 |    86 |        0 |             0 |   597 |   23 |       0 |    483 |  107 |    43 |      88 |        0 |    80 |          0 |   44 |     33 |    0 |

Here's an alternative view on the number of mappings normalized to show
percentage gain. Note that:

- `inf` means that there were no mappings before and now there are a non-zero
  number of mappings
- `NaN` means there were no mappings before inference and continue to be no
  mappings after inference

| source_prefix |    doid |  mondo |   efo |   mesh |   ncit |  orpha | orphanet | orphanet.ordo | umls | omim | omim.ps | medgen |   gard |  icd10 | icd10cm | icd10pcs |  icd11 | icd11.code |    icd9 | icd9cm | icdo |
| :------------ | ------: | -----: | ----: | -----: | -----: | -----: | -------: | ------------: | ---: | ---: | ------: | -----: | -----: | -----: | ------: | -------: | -----: | ---------: | ------: | -----: | ---: |
| doid          |       0 |    3.4 |  14.3 |   22.5 |   14.2 |   25.9 |      nan |           nan | 43.5 |  6.5 |     inf |  91400 |   18.6 | 156000 |     9.2 |      nan |  67500 |        nan | 22154.5 |   23.6 | 31.5 |
| mondo         |     3.4 |      0 |  32.6 |   27.2 |    8.2 |    2.1 |      nan |           nan | 16.4 |  7.6 |     4.6 |    0.1 |    2.9 |  797.6 |    44.6 |      nan |    1.5 |        nan |       3 | 116400 | 10.5 |
| efo           |    14.3 |   32.6 |     0 |    4.8 |   21.1 |     24 |      nan |           nan | 94.4 | 19.3 |    21.7 |   29.7 |   42.4 |   66.3 |     153 |      nan |   23.6 |        nan |    11.1 |  15220 | 57.4 |
| mesh          |    22.5 |   27.2 |   4.8 |      0 | 1948.1 |   36.8 |      nan |           nan |   20 |  inf |     inf |    inf |    inf |    inf |     inf |      nan |    inf |        nan |     inf |    inf |  inf |
| ncit          |    14.2 |    8.2 |  21.1 | 1948.1 |      0 | 2194.6 |      nan |           nan |    7 |  inf |     inf |    inf |    inf |    inf |     inf |      nan |    inf |        nan |     inf |    inf |  inf |
| orpha         |    25.9 |    2.1 |    24 |   36.8 | 2194.6 |      0 |      nan |           nan |  9.9 |  0.8 |    1020 |  56050 | 4617.9 |    0.9 |     inf |      nan | 101900 |        nan |  8333.3 |    inf | 8600 |
| orphanet      |     nan |    nan |   nan |    nan |    nan |    nan |      nan |           nan |  nan |  nan |     nan |    nan |    nan |    nan |     nan |      nan |    nan |        nan |     nan |    nan |  nan |
| orphanet.ordo |     nan |    nan |   nan |    nan |    nan |    nan |      nan |           nan |  nan |  nan |     nan |    nan |    nan |    nan |     nan |      nan |    nan |        nan |     nan |    nan |  nan |
| umls          |    43.5 |   16.4 |  94.4 |     20 |      7 |    9.9 |      nan |           nan |    0 |  0.7 |     inf |    inf |    inf |    1.7 |     3.1 |      nan |    inf |        nan |     inf |    6.2 |  inf |
| omim          |     6.5 |    7.6 |  19.3 |    inf |    inf |    0.8 |      nan |           nan |  0.7 |    0 |     inf |    inf |    inf |    inf |     inf |      nan |    inf |        nan |     inf |    inf |  inf |
| omim.ps       |     inf |    4.6 |  21.7 |    inf |    inf |   1020 |      nan |           nan |  inf |  inf |       0 |    inf |    inf |    inf |     inf |      nan |    inf |        nan |     inf |    inf |  nan |
| medgen        |   91400 |    0.1 |  29.7 |    inf |    inf |  56050 |      nan |           nan |  inf |  inf |     inf |      0 |    inf |    inf |     inf |      nan |    inf |        nan |     inf |    inf |  inf |
| gard          |    18.6 |    2.9 |  42.4 |    inf |    inf | 4617.9 |      nan |           nan |  inf |  inf |     inf |    inf |      0 |    inf |     inf |      nan |    inf |        nan |     inf |    inf |  inf |
| icd10         |  156000 |  797.6 |  66.3 |    inf |    inf |    0.9 |      nan |           nan |  1.7 |  inf |     inf |    inf |    inf |      0 |     inf |      nan |    inf |        nan |     inf |    inf |  inf |
| icd10cm       |     9.2 |   44.6 |   153 |    inf |    inf |    inf |      nan |           nan |  3.1 |  inf |     inf |    inf |    inf |    inf |       0 |      nan |    inf |        nan |     inf |    inf |  inf |
| icd10pcs      |     nan |    nan |   nan |    nan |    nan |    nan |      nan |           nan |  nan |  nan |     nan |    nan |    nan |    nan |     nan |      nan |    nan |        nan |     nan |    nan |  nan |
| icd11         |   67500 |    1.5 |  23.6 |    inf |    inf | 101900 |      nan |           nan |  inf |  inf |     inf |    inf |    inf |    inf |     inf |      nan |      0 |        nan |     inf |    inf |  inf |
| icd11.code    |     nan |    nan |   nan |    nan |    nan |    nan |      nan |           nan |  nan |  nan |     nan |    nan |    nan |    nan |     nan |      nan |    nan |        nan |     nan |    nan |  nan |
| icd9          | 22154.5 |      3 |  11.1 |    inf |    inf | 8333.3 |      nan |           nan |  inf |  inf |     inf |    inf |    inf |    inf |     inf |      nan |    inf |        nan |       0 |    inf |  inf |
| icd9cm        |    23.6 | 116400 | 15220 |    inf |    inf |    inf |      nan |           nan |  6.2 |  inf |     inf |    inf |    inf |    inf |     inf |      nan |    inf |        nan |     inf |      0 |  inf |
| icdo          |    31.5 |   10.5 |  57.4 |    inf |    inf |   8600 |      nan |           nan |  inf |  inf |     nan |    inf |    inf |    inf |     inf |      nan |    inf |        nan |     inf |    inf |    0 |

### Landscape Analysis

Above, the comparison looked at the overlaps between each resource. Now, that
information is used to jointly estimate the number of terms in the landscape
itself, and estimate how much of the landscape each resource covers.

This estimates a total of 127,901 unique entities.

- 44,945 (35.1%) have at least one mapping.
- 82,956 (64.9%) are unique to a single resource.
- 0 (0.0%) appear in all 21 resources.

This estimate is susceptible to several caveats:

- Missing mappings inflates this measurement
- Generic resources like MeSH contain irrelevant entities that can't be mapped

Because there are 21 prefixes, there are 2,097,151 possible overlaps to
consider. Therefore, a Venn diagram is not possible, so an
[UpSet plot](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4720993) (Lex _et
al._, 2014) is used as a high-dimensional Venn diagram.

![](processed_landscape_upset.svg)

Next, the mappings are aggregated to estimate the number of unique entities and
number that appear in each group of resources.

![](processed_landscape_histogram.svg)

The landscape of 21 resources has 369,424 total terms. After merging redundant
nodes based on mappings, inference, and reasoning, there are 127,901 unique
concepts. Using the reduction formula
$\frac{{\text{{total terms}} - \text{{reduced terms}}}}{{\text{{total terms}}}}$,
this is a 65.38% reduction.

This is only an estimate and is susceptible to a few things:

1. It can be artificially high because there are entities that _should_ be
   mapped, but are not
1. It can be artificially low because there are entities that are incorrectly
   mapped, e.g., as a result of inference. The frontend curation interface can
   help identify and remove these
1. It can be artificially low because for some vocabularies like SNOMED-CT, it's
   not possible to load a terms list, and therefore it's not possible to account
   for terms that aren't mapped. Therefore, a lower bound estimate is made based
   on the terms that appear in mappings.
1. It can be artificially high if a vocabulary is used that covers many domains
   and is not properly subset'd. For example, EFO covers many different domains,
   so when doing disease landscape analysis, it should be subset to only terms
   in the disease hierarchy (i.e., appearing under `efo:0000408`).
1. It can be affected by terminology issues, such as the confusion between
   Orphanet and ORDO
1. It can be affected by the existence of many-to-many mappings, which are
   filtered out during processing, which makes the estimate artificially high
   since some subset of those entities could be mapped, but it's not clear which
   should.

## Licensing

Mappings are licensed according to their primary resources. These are explicitly
annotated in the SSSOM file on each row (when available) and on the mapping set
level in the Neo4j graph database artifacts. All original mappings produced by
SeMRA are licensed under CC0-1.0.
