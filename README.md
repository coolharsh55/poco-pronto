# pronto
An open replica of prOnto from the H2020 MIREL project based on publicly available resources.

## Introduction

**PrOnto** is the Privacy Ontology developed by the MIREL H2020 project (https://mirelproject.eu/), and its collaboration with the Luxembourgish DAPRECO project (https://www.fnr.lu/projects/data-protection-regulation-compliance) and described in the following publications:


*MIREL Deliverables*

1. MIREL D2.4 "Ontology population: connecting legal text to ontology concepts and instances" (2018) https://mirelproject.eu/publications/D2.4.pdf

*Peer-reviewed Publications*

2. Palmirani, M., Martoni, M., Rossi, A., Bartolini, C., & Robaldo, L. (2018). PrOnto: Privacy Ontology for Legal Compliance. Proceedings of the 18th European Conference on Digital Government (ECDG), 10. https://cris.unibo.it/bitstream/11585/648220/1/Palmirani%20et%20al%20050.pdf
3. Palmirani, M., Martoni, M., Rossi, A., Bartolini, C., & Robaldo, L. (2018). PrOnto: Privacy Ontology for Legal Reasoning. In A. Kő & E. Francesconi (Eds.), Electronic Government and the Information Systems Perspective (pp. 139–152). Springer International Publishing. https://cris.unibo.it/retrieve/handle/11585/648022/519515/POST%20PRINT%20PrOntoPrivacyOntologyForLegalReasoning.pdf
4. Leone, V., Caro, L. D., & Villata, S. (2018). Legal Ontologies and How to Choose Them: The InvestigatiOnt Tool. Proceedings of the ISWC 2018 Posters & Demonstrations, Industry and Blue Sky Ideas Tracks Co-Located with 17th International Semantic Web Conference (ISWC 2018), Monterey, USA, October 8th - to - 12th, 2018. http://ceur-ws.org/Vol-2180/paper-36.pdf
5. Palmirani, M., Bincoletto, G., Leone, V., Sapienza, S., & Sovrano, F. (2019). PrOnto Ontology Refinement Through Open Knowledge Extraction. Legal Knowledge and Information Systems, 205–210. https://doi.org/10.3233/FAIA190326

## Extraction Process

### PrOnto in MIREL Publication [5]

- The publication [5] (see above list) in footnote 7 provides the link https://gitlab.com/palmirani/pronto.
- This is a git repository with HTML documentation.
- The documentation contains only an empty template for the PrOnto ontology, with no information actually within it.

### PrOnto in MIREL D2.4 [1]

- D2.4 [1] mentions a GraphML diagram of PrOnto to be accessible at https://github.com/guerret/lu.uni.dapreco.parser/blob/master/resources/pronto-v8.graphml - which returns a 404. 
- The Wayback Machine url provides a snapshot from 2021 at https://github.com/guerret/lu.uni.dapreco.parser/blob/master/resources/pronto-v8.graphml. 
- The web archive also shows existence of other (potential) resources (https://web.archive.org/web/20200914045532/https://github.com/guerret/lu.uni.dapreco.parser) which have not been mirrored and are not online anymore (see https://web.archive.org/web/*/https://github.com/guerret/lu.uni.dapreco.parser/blob/master/*).
- Downloaded the diagram file (`pronto_mirel_v8.graphml`) and confirm it contains usable information by opening it in yEd (https://www.yworks.com/yed-live/).



### PrOnto in DAPRECO KB 

1. The DAPRECO KB is available online (https://github.com/dapreco/daprecokb/blob/master/gdpr/rioKB_GDPR.xml), and contains a knowledge base of rules written in LegalRuleML, and uses PrOnto to represent some concepts.
2. Download the XML rules as `dapreco_rioKB_GDPR.xml`.
3. Run a regex pattern match to extract PrOnto concepts (`perl -ne 'print n while /prOnto:(\w+)/gi' rioKB_GDPR.xml | sort | uniq > pronto_dapreco.txt`).

## ToDo

1. Interpret the MIREL v8 diagram for ontology, and manually create the PrOnto ontology as a replica.
2. Check for consistency with concepts extracted from DAPRECO KB.
3. Check for consistency with publications describing PrOnto.
4. Produce a comparison table between DPV and PrOnto.
5. Identify improvements to DPV based on comparison with PrOnto.

## Outputs

1. `pronto.ttl` - the PrOnto ontology
2. `dpv-pronto.csv` - comparison table between DPV and PrOnto
3. `dpv-improvements.csv` - improvements to DPV from PrOnto

## Why I'm doing this?

- Studying PrOnto (as part of MIREL and DAPRECO) is an important aspect of understanding the State of the Art in the domain of GDPR, legal reasoning, and semantics (or semantic web) because of the size and scope of this work (H2020 and national projects respectively) as well as the eminence of people involved in it.
- Understanding the strengths, novelties, ideas, and gaps within such work is part of understanding the domain - and as such was part of my PhD Thesis "Representing Activities associated with Processing of Personal Data and Consent using Semantic Web for GDPR Compliance" (https://harshp.com/research/phd-thesis/).
- More specifically, I'm focusing on understanding how PrOnto relates to Data Privacy Vocabulary (DPV) https://w3id.org/dpv/, trying to compare its concepts, and identifying areas of improvements within DPV.
- Despite being a publicly funded project, MIREL's outputs (vis. PrOnto) are not accessible. This severely limits my understanding of what work has already been produced, how effective it is, and how I should use its ideas to improve DPV.
- I have tried contacting the researchers involved, and received either no replies or indications that I should ask someone else.
- Therefore as a last resort, I have taken to "reverse engineering" this work to overcome what should have been available in the first place.
