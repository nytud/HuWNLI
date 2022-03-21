# HuWNLI
Anaphora resolution datasets for Hungarian formulated as an inference task

This is the repository for the Hungarian datasets of anaphora resolution, designed as a sentence pair classification task of natural language inference.
As a first version, the repo contains the translation of the Winograd schemata formatted as an inference task. A Winograd schema is a pair of sentences that differ in only one or two words and that contain an ambiguity that is resolved in opposite ways in the two sentences and requires the use of world knowledge and reasoning for its resolution (Levesque et al. 2012). This dataset is also part of the Hungarian Language Understanding Evaluation Benchmark Kit [HuLU](hulu.nlp.nytud.hu). 

The [HuWS corpus](github.com/nytud/HuWSC) was created by translating and manually curating the original English Winograd schemata. The NLI format published here was created by replacing the ambiguous pronoun with each possible referent in the schemata (the method is described in GLUE's paper, Wang et al. 2019). 

## Dataset Structure

### Data Instances

For each instance, there is a schema, an id, two sentences and a label. 

An example:

```
{"schema": "1",
 "id": "0",
 "sentence1": "A városi tanácstagok nem adtak engedélyt a tüntetőknek, mert kerülték az erőszakot.",
 "sentence2": "A városi tanácstagok kerülték az erőszakot.",
 "Label": "1"
}
```

### Data Fields
- schema: the number of the original schema this sentence pair was derived from;

- id: unique id of the instances;

- sentence1: the original sentence of the schema with one of the two alternate words;

- sentence2: a manually formed question;  

- Label: "1" if sentence2 is entailed by sentence1, and "0" otherwise.

The data is distributed without any predefined splits.


### Licensing Information

HuWSC is released under the BSD 2-Clause License.


### Citation Information

If you use this resource or any part of its documentation, please refer to:

Ligeti-Nagy, N., Ferenczi, G., Héja, E., Jelencsik-Mátyus, K., Laki, L. J., Vadász, N., Yang, Z. Gy. and Váradi, T. (2022) HuLU: magyar nyelvű benchmark adatbázis kiépítése a neurális nyelvmodellek kiértékelése céljából [HuLU: Hungarian benchmark dataset to evaluate neural language models]. In: Berend, Gábor and Gosztolya, Gábor and Vincze, Veronika (eds), XVIII. Magyar Számítógépes Nyelvészeti Konferencia. JATEPress, Szeged. 431–446.

```
@inproceedings{ligetinagy2022hulu,
  title={HuLU: magyar nyelvű benchmark adatbázis kiépítése a neurális nyelvmodellek kiértékelése céljából},
  author={Ligeti-Nagy, N. and Ferenczi, G. and Héja, E. and Jelencsik-Mátyus, K. and Laki, L. J. and Vadász, N. and Yang, Z. Gy. and Váradi, T.},
  booktitle={XVIII. Magyar Számítógépes Nyelvészeti Konferencia},
  year={2022},
  editors = {Berend, Gábor and Gosztolya, Gábor and Vincze, Veronika},
  address = {Szeged},
  publisher = {JATEPress},
  pages = {431–446}
}
```

and to:

Levesque, Hector, Davis, Ernest, Morgenstern, Leora (2012) he winograd schema challenge. In: Thirteenth International Conference on the Principles of Knowledge Representation and Reasoning.

```
@inproceedings{levesque2012winograd,
  title={The Winograd Schema Challenge},
  author={Levesque, Hector and Davis, Ernest and Morgenstern, Leora},
  booktitle={Thirteenth International Conference on the Principles of Knowledge Representation and Reasoning},
  year={2012},
  organization={Citeseer}
}
```
