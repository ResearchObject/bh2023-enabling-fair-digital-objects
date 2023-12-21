---
title: 'BioHackEU23 report: Enabling FAIR Digital Objects with RO-Crate, Signposting and Bioschemas'
title_short: 'BioHackEU23 #15: Enabling FAIR Digital Objects'
tags:
  - RO-Crate
  - Signposting
  - Bioschemas
  - FAIR Digital Object
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
  - name: ZB MED Information Centre for life sciences, Cologne, DE
    index: 3
  - name:  Senckenberg – Leibniz Institution for Biodiversity and Earth System Research, Frankfurt/M, DE
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

[RO-Crate](https://www.researchobject.org/ro-crate/) [@citesAsAuthority:10.3233/ds-210053] is a lightweight method to package research outputs along with their metadata. [Bioschemas](https://bioschemas.org/) [@citesAsAuthority:Bioschemas] provides metadata schemas to add structured metadata to webpages on Life Science. [Signposting](https://signposting.org/FAIR/) [@citesAsAuthority:vandesompelFAIRSignpostingProfile2022] [@extends:vandesompel2015]  provides a lightweight yet powerful approach to increase the FAIRness of scholarly objects.

The combination of RO-Crates, Bioschemas and Signposting make resources easy to navigate by machines, provide an unambiguous way for machines to access FAIR metadata and content in a single request, and reduce content-negotiation hassle that can give unpredictable results [@citesAsAuthority:10.3897/rio.8.e93937].

This tripartite combination is of benefit for repositories and publishers as they can non-disruptively add FAIR Signposting headers for machine navigation, support RO-Crate imports and align with Bioschemas specifications, making FAIR Digital Objects achievable with existing technologies over HTTP [@citesAsAuthority:10.3897/rio.8.e94501].

FAIR tooling implementers can also benefit as they could create, improve or integrate Signposting clients combined with RO-Crate libraries implementing Bioschemas specifications. On its side, FAIR data implementers could support consumption of FAIR Signposting and create Knowledge Graphs from RO-Crates.

While Bioschemas has been adopted by many repositories, the methods for its consumption have largely been focused on discoverability. Now we focus on integrations, such as building scholarly knowledge graphs from multiple Bioschemas sources.

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

![The HoloFood Data Portal (www.holofooddata.org) now includes machine-readable Signposting links directing clients to the API for a JSON description of the each Sample as well as the collection to which the Sample belongs. The browser extension is shown here rendering these Signposts to the user.](./figures/signposting-browser-extension.jpg)


## Indexing RO Crates in backend databases
In their JSON-LD schema form, RO-Crates are a document rendered to describe the metadata (and possibly some summary data, like a measured [`PropertyValue`](https://schema.org/PropertyValue)).
In their compressed form (e.g. a `.zip` file), they can also contain one or more files – typically HTML renderings of the schema, other HTML reports like those generated by computational workflow runs, and data files like `.tsv` tables or image files.
In both cases, these crates are usually **derived** products: either rendered on demand when a client visits a URL (e.g. `http://my.data/dataset/1?format=ro_crate`), or created in advance and stored on an object store potentially with a new identifier/URI unrelated to the dataset's natural identifier.

However RO-Crates have the potential to be used more holistically than this, with the schema profile acting as a glue between the self-describing crates and the business logic or database schema of a data repository.

Given a profile that describes some mandatory parameters:


| Property | Required? | Description                                |
| -------- | --------- | ------------------------------------------ |
| name     | MUST      | String representation of the dataset name  |
| pipeline | MUST      | URI of the `ComputationalWorkflow` used    |
| ...      | ...       | ...                                        |

RO-Crates conforming to this profile will include `name` and `pipeline` fields in the root data context (i.e. JSON paths like `crate.@graph[?].name` and `crate.@graph[?].pipeline.@id`).

If a data repository needed to index this dataset, for listing, searching and cross-referencing purposes, a database might be constructed with a schema:

| id† | dataset_name†   | pipeline_uri†  | data_uri                 | crate_uri                                |
| --- | --------------- | -------------- | ------------------------ | ---------------------------------------- |
| 1   | My Dataset      | http://my.code | http://my.data/dataset/1 | http://my.data/dataset/1?format=ro_crate |

where † = columns indexed by the database engine, to allow lookups with scanning the entire table.
In most relational database engines, this kind of indexing is required for realtime lookups of "all the datasets created by a certain pipeline".

During BioHackathon Europe 2023, we explored the possibility of using relational database's JSON fields (which are now a stable feature of engines such as [PostgreSQL](https://www.postgresql.org/docs/current/functions-json.html)) to create an equivalent database schema working directly on the RO-Crate JSON-LD.

In a production setting, data repositories often use an Object Relational Mapper (ORM) to manage their database rather than executing queries directly.
Therefore we developed a Prototype using [Django](https://code.djangoproject.com), a popular Python-based ORM, with a Postgres backend.

The table schema was:

| id   | crate_schema                  | crate_name    |
| ---- | ----------------------------- | ------------- |
| int  | jsonb                         | varchar       |
| ---- | ----------------------------- | ------------- |
| 1    | `{"@graph": [{"@id": "./"...` | My Dataset    |

We used this schema to explore two approaches to querying this table of crates.
Firstly, we used a feature of the fortchoming [Django 5.0 release](https://docs.djangoproject.com/en/dev/releases/5.0/#database-generated-model-field): `GeneratedField`s.
Generated Fields allow the ORM model to have a schema like:

```python
class Crate(Model):
    crate_schema = models.JSONField(default=dict, null=True, blank=True)
    crate_name = models.GeneratedField(
        expression=F('crate_schema__@graph__0__name'),
        db_persist=True,
        output_field=models.CharField(max_length=100)
    )
```

This approach ensures that any create or update operations on a Crate instance in the database, for example when a new crate conforming to the supported profile is deposited, result it some of the crate's properties being correctly indexed.
Likewise if the database schema needs to change, for example to add the `pipeline_uri` column a schema migration will automatically populate the new column with the correct metadata from each crate instance.

Secondly, we used a Generalized Inverted Index (GIN index) to create a database index over the crate schema.
GIN indices are useful for cases where queries across a composite data type are needed; for our crate database this might be to query for crates where an additional profile is conformed to, or where the crate references a certain `FundingAgency`.
This was only partially successful: whilst we could trivially create a GIN index on the entire JSON-LD `crate_schema`, a more realistic implementation would be to selectively (and therefore performantly) index only part of the crate graph using a query to create the index. We did not achieve this step.


## Implementing Signposting on a Single Page Application

Senckenberg has brought their [Wildlive data portal](https://wildlive.senckenberg.de/), a work-in-progress repository and analysis platform for biodiversity monitoring, as a use case into this Biohackathon project. Wildlive provides data models to describe i.a. observational data from camera traps, our aim was to enable the representation of those data employing both RO-Crates and Signposting to increase interoperability and machine actionability of data provided by the platform. RO-Crates were implemented in the form of an additional API endpoint which serializes the metadata from the data portal's internal metadata schema to a `ro-crate-metadata.json`. This headless RO-Crate describes a "package" of camera trap observations which were all recorded caused by the trigger event that triggered the camera sensor, where each observation contains an image (possibly with one or many species occurrences). The implementation of this RO-Crate layer on top of the existing data portal was rather straightforward. In contrast, the implementation of Signposting required more work and shall be explained in more detail here.

The difficulty in adding Signposting to the Wildlive data portal was in that the portal was built as a [Single Page Application](https://en.wikipedia.org/wiki/Single-page_application)(SPA), based on [VueJS](https://vuejs.org/). This means that upon a request from a client (usually a web browser), the server returns a generic, static HTML file and JavaScript code. Afterwards, the code is executed in the browser and the content-specific data is loaded asynchronously via API calls to the backend of the application. To implement Signposting, links to related web resources of a website can either be added to the HTML header or to the header of the HTTP response of the server. However, to add these links, content-specific metadata is required which is not yet available when the server initially answers the client's request.
This problem is comparable to the problem that many SPA-based websites have which seek to add specific metadata markup to their websites HTML to achieve search engine optimization. Typical solutions to this problem are the implementation of a server-side rendering or pre-rendering step based on an additional NodeJS-based webserver in the backend of the application. During this step, some parts or all of the HTML are being rendered on the side of the server (which allows to add metadata markup e.g. for search engine crawlers but also for Signposting), before the SPA is delivered to the client.

However, typical solutions like adding server-side rendering were not feasible to add to the existing Wildlive data portal because they require a lot of changes on the application's code structure itself. Instead, we came up with a lightweight method to add Signposting to the landing pages of the camera trap observations. For this, we made use of the fact that Signposting links must not necessarily be included in the HTML header, but are also allowed to be only transported via the HTTP `Link` header (unlike for search engine optimization where the content-specific markup must be in the HTML that a client receives). The Wildlive data portal, like many other SPA-based websites, is based on a lightweight webserver, in this case [NGINX](https://nginx.org/), which serves the static files of the website. NGINX with the addional `nginx-module-njs` allows to add custom scripting based on JavaScript code to the webserver configuration. Therefore, we added a custom script which upon a request to the frontend landing page of a certain observation dataset, makes an internal request to the API to retrieve the content-specific metadata. Based on this metadata, the correct Signposting links are generated and added to the HTTP response which returns the static HTML to the client (see Fig. 2).

With this, we managed to add Signposting HTTP headers to an existing SPA-based data portal, without having to change any application code of the data portal. A drawback is that in this setup the API receives two requests, one to build the Signposting headers before responding the client's request, and one later when the application is loaded asynchronously in the client browser (in the case that the request has not been made by a machine-agent without a browser).

![Schematic overview of how Signposting headers are added to the HTTP response in NGINX](./figures/signposting-nginx-architecture.png)

Figure 2: Schematic overview of how Signposting headers are added to the HTTP response in NGINX

## Implementing RO Crates and Sigposting in GitHub pages
The [Semantic Technologies (SemTec) team](https://zbmed-semtec.github.io/) in [ZB MED](https://www.zbmed.de/en/) uses GitHub pages to share research projects and corresponding research artefacts/outcomes (e.g., datasets, software, metadata schemas/ontologies, posters, reports, preprints, scholarly publications). The pages embed Bioschemas and [schema.org](https://schema.org/) markup to facilitate findability and connectivity of the research outcomes. The goal behind implementing RO-Crates and Signposting is supporting a lightweight approach to FAIR Digital Objects (FDOs) [@citesAsPotentialSolution:Soiland_FDO_2022] [@citesAsPotentialSolution:Castro_FDO_2023]. The FDO approach [@citesAsAuthority:Smedt_FDO_2020] corresponds to a series of recommendations to increase and extend FAIRness to cover typed operations, allowing implementation via different compliant configurations [@citesAsAuthority:Lannon_FDOConfig_2022]. This work was initiated as part of a FAIR-Impact Support Action and advanced to an initial implementation during the BioHackathon. As a result, the SemTec team now supports RO-crates for research projects and theses with Signposting level 2.

# Conclusion and Future Work
He have presented here various approaches to implement RO-Crates and Signposting, some of them also supporting Bioschemas markup. This combination aims at improving interoperability and reusability. The ZB MED SemTec team will get permanent, unique and global identifiers for the RO-Crates and the corresponding GitHub pages to improve FDO compliance, it will also add software to the research artefacts implementing RO-crate. 

## Acknowledgements
The work corresponding to the ZB MED SemTec team pages has been partially supported by the NFDI4DataScience project funded by the German Research Foundation (DFG) (no. 460234259), and the FAIR-Impact GA 101057344 Support Action #2: Enabling FAIR Signposting and RO-Crate for content/metadata discovery and consumption. Work corresponding to the Senckenberg team has been partially supported by Biodiversity Digital Twin for Advanced Modelling, Simulation and Prediction Capabilities ([BioDT](https://biodt.eu)) (Horizon Europe, GA no. 101057437), and [NFDI4Earth](https://www.nfdi4earth.de/) - NFDI Consortium Earth System Sciences (DFG, no. 460036893).

We also acknowledge the ELIXIR BioHackathon Europe 2023



## References
<!-- see paper.bib -->

