---
title: Understanding Core Concepts
---

# Understanding Core Concepts

Like many other digital repository, archive, and library platforms, Kora is designed with a specific kind of architecture.  This architecture determines both how projects using Kora are structured as well as the workflow used by those working on the projects.  

In the case of Kora, this architecture is somewhat hierarchical, in which relevant components are nested within one another.  In order to get the most out of Kora, it is important to understand these components, what role they play, and how the interact with one another.  

## Kora Installation

A Kora installation can have any number of discreet projects (more on Projects below).  For the most part, each project in a Kora installation is its own silo.  The only exception to this is that from within the Kora installation, admins can search across multiple project (cross project searching).  In addition, the Kora API can be used to display (including searching and browsing) records from across multiple projects in one public website.  

While a Kora installation can contain any number of projects, you might also feel the need to install more than one instance of Kora on a server (to isolate one specific project in a container, for instance).  

To learn about what you need to install Kora on a server, check out [System Requirements](../getting-started/system_requirements.md).  If you are interested in installing Kora on Reclaim or Domain of One's Own, check out [Installing Kora on Domain of One's Own and Reclaim Hosting](../getting-started/installing_kora_domains.md)

There are some things that you can only do in Kora at the installation level (such as creating projects and managing Kora tokens and API requests).  In addition, you can add users to a Kora installation, but not assign them to a particular project. This creates a pool of users that can easily be added to a project (or projects). All installation level settings and the ability to add users at the installation level (and assigning them to specific projects) is the domain of a Kora Admin.  To learn more about Kora Admins (and all other user types), check out [Understanding Kora User Types and Permissions](../getting-started/understanding_kora_user_types_and_permissions.md).


## Project

In Kora, a project *is* a digital repository.  It has a particular theme or focus (a specific collection, for instance), and contains records (metadata + digital objects) related to that theme or focus, as well as forms for creating those records (more on that below). Each project has its own set of users (each of whom can have different privileges within that project).  

A Project Admin sits at the top of the user pyramid *within* a project. While they can't create new projects, they pretty much can do anything within the project for which they are an admin. This includes creating forms, editing forms, deleting forms, creating field value presets, importing and exporting forms, and managing user permissions.   


## Form

Forms are essentially the mechanism by which records are generated.  In this regard, forms in Kora are analogous to paper forms. A paper form is meaningless until you fill it out - which creates a record of some sort.  In Kora, forms (which live within a project) are filled out by a user, thereby generating a record. Forms are essentially data entry tools.  The important thing to note is that forms create structured data.  Each record created with a particular form will be structured in the exact same way. What a form looks like (the form's Field Types - more on that below) is determined by your project's metadata scheme.  Like all digital repository, library, and archive projects, the metadata scheme is built and tuned in advance of any technical work.  In the case of Kora, that metadata scheme would be used to create a project's forms.  

A project can have any number of different forms, each for a different type of record or object.  So, for instance, if your project contained both historic documents and archaeological artifacts, you could create a form for each.  When a user wanted to use generate a record for a document, they'd use the document form.  When they wanted to generate a record for an artifact, they'd use the artifact form.  In Kora, users can also connect two forms using an associator (which is a specific Field Type - more on those below).  

To learn more about Forms in Kora, start by reading [Creating a Form](../forms/creating_a_form.md).


## Field Types

In Kora, Field Types are what makes a Form something you can actually fill out to create a record.  Imagine a form that didn't have any text fields or checkboxes.  This is a Form without Field Types.  

Kora has a wide variety of Field Types, each of which are purpose built to allow users to enter certain types of data.  For instance the Geolocator Field type allows you to enter geospatial information (in the form of Lat/Long or an address), while a a Text Field (which is probably the most common Field Type) allows users to enter any plan text into a record.  

Kora also includes a variety of very specialized Field Types. One of the most powerful is the [Associator](../forms/understanding_field_types.md/#associator), which allows you to create connections between records.  

To learn more about Kora's various Field Types, check out [Understanding Field Types](../forms/understanding_field_types/).


## Records

Kora has a flexible approach to what it considers a record.  For many digital repository and archive platforms, a record centers on a digital object (which is most often a digitized version of a physical object - a book, a document, a wax cylinder, an archaeological artifact).  In the case of Kora, a record center a little more broadly on an entity - a person, a place, or a thing.  A record is a collection of metadata that describes that entity.  So, for instance, a Kora project could have place records, each of which is a collection of metadata that describes a specific place.  That place record could also include multiple digital objects relevant to that place (historic photos, maps, etc)  Similarly, a Kora project could have people records - each of which was a collection of metadata that described an individual.  Kora can, of course, also have records for digitized physical objects.  One of the interesting things about Kora is that you can associate (using the Associator field type) different relevant records.  So, instead of including relevant digital images of an individual in their person record, the images would have their own records (each with robust metadata) that were then associated with the relevant person record.  

 Records are generated by Forms, whose structure in determined by the project's metadata scheme for that type of entity (historic document, archaeological artifact, person, place, etc).  To learn more about working with Records in Kora, start by reading [Creating a Record](../records/creating_a_record.md).
