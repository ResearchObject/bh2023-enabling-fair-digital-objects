---
title: 'BioHackEU23 report: Enabling FAIR Digital Objects with RO-Crate, Signposting and Bioschemas'
title_short: 'BioHackEU23 #15: Enabling FAIR Digital Objects'
tags:
  - RO-Crate
  - Signposting
  - Bioschemas
authors:
  - name: Stian Soiland-Reyes
    affiliation: [1,2]
    orcid: 0000-0001-9842-9718
  - name: Leyla Jael Castro
    orcid: 0000-0003-3986-0510
    affiliation: 3
  - name: Rohitha Ravinder
    orcid: 0009-0004-4484-6283
    affiliation: 3
  - name: Claus Weiland
    affiliation: 4
    orcid: 0000-0003-0351-6523
  - name: Jonas Grieb
    affiliation: 4
    orcid: 0000-0002-8876-1722
  - name: Alexander Rogers
    affiliation: 6
    orcid: 0000-0002-4283-6135
  - name: Christophe Blanchi
    affiliation: 9
    orcid: 0000-0003-2277-5176
  - name: Herbert Van de Sompel
    orcid: 0000-0002-0715-6126
    affiliation: 10
affiliations:
  - name: Department of Computer Science, The University of Manchester, Manchester, UK
    index: 1
  - name: Informatics Institute, University of Amsterdam, Amsterdam, NL
    index: 2
  - name: ZBMED Information Centre for life sciences, Cologne, DE
    index: 3
  - name:  "Senckenberg – Leibniz Institution for Biodiversity and Earth System Research: Frankfurt/M, Hessen, DE"
    index: 4
  - name: EMBL-EBI, Hinxton, UK
    index: 6
  - name: DONA foundation, Geneva, CH
    index: 9
  - name: DANS, The Hague, NL
    index: 10
date: 3 November 2023
cito-bibliography: paper.bib
event: BH23EU
biohackathon_name: "BioHackathon Europe 2023"
biohackathon_url:   "https://biohackathon-europe.org/"
biohackathon_location: "Barcelona, Spain, 2022"
group: Project 15
# URL to project git repo --- should contain the actual paper.md:
git_url: https://github.com/ResearchObject/bh2023-enabling-fair-digital-objects
# This is the short authors description that is used at the
# bottom of the generated paper (typically the first two authors):
authors_short: Stian Soiland-Reyes \emph{et al.}
---


# Introduction

As part of the BioHackathon Europe 2023, we here report from the progress of the hackathon project #15: "Enabling FAIR Digital Objects with RO-Crate, Signposting and Bioschemas". 

# Background

[RO-Crate](https://www.researchobject.org/ro-crate/) [@citesAsAuthority:10.3233/ds-210053] is a lightweight method to package research outputs along with their metadata. [Bioschemas](https://bioschemas.org/) [@citesAsAuthority:Bioschemas] provides metadata schemas to add structured metadata to webpages on Life Science. [Signposting](https://signposting.org/FAIR/) [@citesAsAuthority:vandesompelFAIRSignpostingProfile2022] [@extends:vandesompel2015]  provides a lightweight yet powerful approach to increase the FAIRness of scholarly objects.

The combination of RO-Crates, Bioschemas and Signposting make resources easy to navigate by machines, provide an unambiguous way for machines to access FAIR metadata and content in a single request, and reduce content-negotiation hassle that can give unpredictable results [@citesAsAuthority:10.3897/rio.8.e93937].

This tripartite combination is of benefit for repositories and publishers as they can non-disruptively add FAIR Signposting headers for machine navigation, support RO-Crate imports and align with Bioschemas specifications, making FAIR Digital Objects achievable with existing technologies over HTTP [@citesAsAuthority:10.3897/rio.8.e94501].

FAIR tooling implementers can also benefit as they could create, improve or integrate Signposting clients combined with RO-Crate libraries implementing Bioschemas specifications. On its side, FAIR data implementers could support consumption of FAIR Signposting and create Knowledge Graphs from RO-Crates.

While Bioschemas has been adapted by many repositories, the methods for its consumption have largely been focused on discoverability. Now we focus on integrations, such as building scholarly knowledge graphs from multiple Bioschemas sources.

Finally, FAIR outreach practitioners showcase uses of FAIR Signposting to navigate and consume RO-Crates making FAIR closer to the community. This project will continue the effort started as part of FDO2022 [@discusses:looFirstInternationalConference2022] and FAIR-IMPACT to enable FAIR Signposting and RO-Crate for content/metadata discovery and consumption.


# Initial plan

* Add metadata markup/headers to landing pages of at least one website
  - Drop-in for anyone to add FAIR Signposting for existing persistent identifiers and metadata resources
  - Drop-in for adding Bioschemas metadata to website
  - Drop-in for RO-Crate support  
* Improve at least one Signposting client
  - https://signposting.readthedocs.io/ (Python)
  - https://github.com/markwilkinson/linkheader-processor (Ruby)
  - Javascript?
  - Java/Jena?
  - Your language!
* Improve Bioschemas/RO-Crate validation for at least one profile (working with [#7](../17/))
* Prototype FAIR Digital Object (FDO) implementation using Signposting, PIDs and RO-Crate
* Conceptualise and draft FDO "configuration type" profile for Signposting-based FDO implementation
* Write up a BioHackrXiv preprint!
* Other ideas
  -  Prototype a knowledge graph from pages using any of the technologies (working with [#7](../17/))
  -  Build a validator for FAIR Signposting level 1, then level 2 - may be based on https://github.com/stain/signposting/ 

<!-- Markdown tips below:

# Formatting

This document use Markdown and you can look at [this tutorial](https://www.markdowntutorial.com/).

## Subsection level 2

Please keep sections to a maximum of only two levels.

## Tables and figures

Tables can be added in the following way, though alternatives are possible:

| Header 1 | Header 2 |
| -------- | -------- |
| item 1 | item 2 |
| item 3 | item 4 |

Table: Note that table caption is automatically numbered.

A figure is added with:

![Caption for BioHackrXiv logo figure](./biohackrxiv.png)

# Other main section on your manuscript level 1

Lists can be added with:

1. Item 1
2. Item 2

# Citation Typing Ontology annotation

You can use CiTO annotations, as explained in [this BioHackathon Europe 2021 write up](https://raw.githubusercontent.com/biohackrxiv/bhxiv-metadata/main/doc/elixir_biohackathon2021/paper.md) and [this CiTO Pilot](https://www.biomedcentral.com/collections/cito).
Using this template, you can cite an article and indicate why you cite that article, for instance DisGeNET-RDF [@citesAsAuthority:Queralt2016].

Possible CiTO typing annotation include:

* citesAsDataSource: when you point the reader to a source of data which may explain a claim
* usesDataFrom: when you reuse somehow (and elaborate on) the data in the cited entity
* usesMethodIn
* citesAsAuthority
* discusses
* extends
* agreesWith
* disagreesWith
-->

# Results

## Visualising Signposting
Signposting is explicitly designed to add machine-readable links to the metadata associated with a human-readable scholarly object.
Taking the canonical example of a web landing page for a dataset, which humans parse as rendered HTML, Signposting adds invisible links to remote resources like an ORCID profile of the author, a DOI the resource can be cited as, and downloadable items of the dataset like images and data tables.
These are implemented as HTTP headers (`Link: <https://orcid.org/0000>; rel="author"`) or HTML header link tags (`<link href="https://doi.org/10.5281/zenodo..." rel="item" type="application/zip"/>`).

Typically, these implementations do not render anything that a user of the landing page will see (without using developer tools to inspect the source of the material they're viewing).
This means that resource authors and developers need to use debugging tools to develop and test their implementations of Signposting: for example browser developer tools, or bespoke parsers for the Signposting headers [@citesAsPotentialSolution:Signposting_link_parser].
It also means that users discovering data resources with a view to then accessing them programatically, for example in a new pipeline or data ingestion process, will need to find the links to programmatic access options by browsing the web pages and documentation, rather than following the same shortcuts that robot agents can see.

During BioHackathon Europe 2023 we developed a browser extension, initially targetting Chromium-based browsers, to render Signposting links as a visible bar on landing pages.
This helps resource developers to quickly verify their Signposting implementations and notifies resource users to the possible citation, contact, and programmatic access options they might use.


# Discussion

...

## Acknowledgements



## References
<!-- see paper.bib -->

