Standardising Interest Declarations
===================================

## Contents

```eval_rst
.. toctree::
   :maxdepth: 2

   Background

```

## Background

(todo - brief overview of project, plus links, and how the idea of standardising declarations of interest related to the work.)

## Status of the data model

We present here an idea for standardising information declared by people about their interests. The structure of the data (the data model) is informed by:

* the experience of dealing with unstructured, variously formatted information in this domain,
* an understanding of how tightly the format of declarations can be tied to regulatory requirements and language,
* a recognition that an 'interest' may cover an extremely diverse range of activities, roles and engagements,
* an assumption that the added value of a structured format is in enabling patterns across declarations to be more easily identified,
* experience elsewhere in the transparency field which highlights the importance of historical data on declarations.

The data model is a first draft: it's an opener in a conversation. Publishing its details here, means that the ideas can feed into further work in this domain. We hope that it might provoke interest and criticism.

The [draft data model](https://docs.google.com/spreadsheets/d/1QCVkxi1B-i3xx1lVJXe1ihhQSrgtOEeAxj8CHoFgTVA/edit#gid=0) is documented in a spreadsheet for convenience. Ultimtaely it could be rendered in JSON schema.

## Overview of the data model

![Diagram of data model](_assets/UML-interests-data-model.png)

The data model encapsulates an Interest object, placing it within a Declaration. This allows processes of declaration and re-declaration (or confirmation) to be treated and understood separately from the lifecycle and nature of the interest itself. (For example, a person may be required to declare an interest which actually sits with a family member or business partner.)

The Interest object itself is only semi-structured. The model is built on the assumption that it is primarly **dates, people and organisations** associated with interests that people wish to link to other information. (We can imagine that there might be other notable information types - for instance, location. Beginning with the most obvious and widely applicable information types seemed wise.) We leave it up to data publishers to provide in their datasets the precise field names for dates, people and organisations. More information about this feature of the model can be found below under Key features > Flexibility.
    
[View the draft data format](https://docs.google.com/spreadsheets/d/1QCVkxi1B-i3xx1lVJXe1ihhQSrgtOEeAxj8CHoFgTVA/edit#gid=0)

## Key features

### Modelling declarations
As important as the details of politicians' and prominent figures' **interests** are, so are the details of how and when those interests were **declared*. The draft model captures information about both these things. It also allows a declaration that someone has no relevant interests to be represented.

### Flexibility
In order that as many types of interests as possible might be represented by the data model, we have maintained a high level of abstraction. In practice, that means identifying the components, common to all interests, which draw most attention from data users. These, we propose, are **dates, people and organisations**. The data model allows, though, for more detail to be added: for publishers to move to a lower level of abstraction. Data profiles can be created (external to the model) which define the specific roles of dates, people and organisations in relation to different types of interest. For example, a recommended data profile for interests in the category 'employment and earnings' might include:

```eval_rst
.. list-table::
    :header-rows: 1
    :widths: 1 1 1 3

    * - Object
      - Property
      - Value
      - Description
    * - OrganisationField
      - fieldName
      - Organisation benefitting
      - The employer or organisation benefitting from the work.
    * - OrganisationField
      - fieldName
      - Organisation paying
      - The organisation paying for the work if different from that benefitting from it.
    * - DateField
      - fieldName
      - Work completion date
      - The date on which the work was completed. 
    * - PersonField
      - fieldName
      - Person employed
      - The person whose employment or earnings make this a registrable interest. 
```

The values above would be published as part of a dataset, but their full meaning is provided by the 'desciption' in the data profile. Data profiles like this might be referenced from pubishers' Publication Policies. 


### Open codelists
To aid the flexibility and applicabilty of the model, we have opted for open codelists (codelists from which values can be chosen or which can be ignored in favour of custom values) where possible. For example an organisation, depending on the role it has in a particular interest, may be a 'Donor, Contracting organisation, Contracted organisation, Employer, Company, Organisation, Owner'. Or it may have another role entirely. 


## Outstanding issues

### Republishing & publisher metadata

### Change over time. Adding, updating or ending an interest is done as part of the declaration, by the declarer. Retraction is an action of the publisher. Relates to the above.

### Packaging

## About

(todo- more detail about who we are and what the project was)
