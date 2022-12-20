---
title: 'unfold: UNpacking For scenariO-based Lca Databases'
tags:
  - Python
  - life cycle assessment
  - prospective
  - database
  - premise
  - scenario

authors:
  - name: Romain Sacchi
    orcid: 0000-0003-1440-0905
    equal-contrib: true
    affiliation: 1

affiliations:
 - name: Paul Scherrer Institute, Villigen, Switzerland
   index: 1

date: 21 December 2022
bibliography: paper.bib

---

# Summary

`unfold` is a Python package that allows sharing life-cycle databases based on
licensed data (e.g., ecoinvent) without exposing it. 
It relies on the exchange of data packages that contain the differences between
the databases to replicate and a source database (e.g., ecoinvent), as well as 
a metadata file that describes the databases and their content. 
Hence, `unfold` allows to unpack any number of databases and to fold them back 
into a single data package, to easing the sharing and reproducibility of
life-cycle assessment databases.


# Statement of need

Life-cycle assessment (LCA) consists in the quantification of the environmental
impacts of a product or a process. It is a powerful tool to assess the
environmental performance of products and processes, and to identify
environmental hotspots. However, it is difficult to share LCA databases, 
as they are often based on licensed data (e.g., ecoinvent [@Wernet:2016]). 
`unfold` allows to share databases without exposing the source
data, by sharing instead data packages that allows other users to reproduce the
LCA database (provided they have the source database registered locally).

`unfold` is initially conceived to share LCA databases that have been heavily
modified, such as those generated with the `premise` package [@Sacchi:2022], 
or those regularly produced within the field of prospective LCA (where the need to
modify extensively the source database is often required), such as those produced
by Mendoza et al. [@Mendoza:2018]

![Workflow for database sharing using `unfold` data packages.\label{fig:workflow}](assets/flow_diagram.png)

Scaling factors between the exchanges of the databases to replicate 
and the exchanges of the source database are
calculated and stored in a data package, along with any extra datasets, as
well as a metadata file that describes the databases and their content 
(see \autoref{fig:workflow}).

`unfold` is based on the `brightway2` framework [@Mutel:2017], which means that 
it can only be used to "fold" and "unfold" databases registered in a `brightway2` project.
The data packages generated by `unfold` can be shared freely among users, 
as they do not contain any licensed data. 
However, the end user must have the source database registered locally to be 
able to use the data package and reproduce the LCA database(s).
`unfold` can also produce superstructure databases [@Steubing:2021], which can integrate several
scenarios into a single database, to be further used with the LCA software
`activity-browser` [@Steubing:2020].


# References