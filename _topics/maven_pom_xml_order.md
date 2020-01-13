---
topic: "Maven: Pom.xml Order"
desc: "In what order should the elements of a pom.xml appear"
category_prefix: "Maven: "
indent: true
---

The `pom.xml` can have many elements inside.   The order likely doesn't matter, but for organization purposes, to be sure that you don't 
duplicate an element, it's helpful to have a *canonical order*.  Here *canonical order* just means a particular order that is agreed upon and always the same.  (If you insist on precision, a more rigorous definition can be found on the [Wikipedia article for Canonical form](https://en.wikipedia.org/wiki/Canonical_form).)

In the Maven documentation, the webpage [Maven Code Style And Code Conventions](https://maven.apache.org/developers/conventions/code.html) suggests the order below, so we'll adopt that order as *canonical* for Maven `pom.xml` files in CS56.    

In the code snippet below, you'll find each of the elements names, in the suggested order, formatted as an XML comment.

You can use this as a template to copy paste into your `pom.xml`, then move the sections
you have under the appropriate comment.   This can be particularly helpful when trying to merge together two different `pom.xml` files
from separate examples into one working product.
 
```xml
  <!-- (0) <modelVersion/> -->
  <!-- (1) <parent/> -->
  <!-- (2) <groupId/> -->
  <!-- (3) <artifactId/> -->
  <!-- (4) <version/> -->
  <!-- (5) <packaging/> -->
  <!-- (6) <name/> -->
  <!-- (7) <description/> -->
  <!-- (8) <url/> -->
  <!-- (9) <inceptionYear/> -->
  <!-- (10) <organization/> -->
  <!-- (11) <licenses/> -->
  <!-- (12) <developers/> -->
  <!-- (13) <contributors/> --> 
  <!-- (14) <mailingLists/> -->
  <!-- (15) <prerequisites/> -->
  <!-- (16) <modules/> -->
  <!-- (17) <scm/> -->
  <!-- (18) <issueManagement/> -->
  <!-- (19) <ciManagement/> -->
  <!-- (20) <distributionManagement/> -->
  <!-- (21) <properties/> -->
  <!-- (22) <dependencyManagement/> -->
  <!-- (23) <dependencies/> -->
  <!-- (24) <repositories/> -->
  <!-- (25) <pluginRepositories/> -->
  <!-- (26) <build/> -->
  <!-- (27) <reporting/> -->
  <!-- (28) <profiles/> -->
 ```
# Explanation of each section

Having this canonical order gives us an opportunity to write documentation explaining each section of the pom.xml.   Given that there are 28 of these, it may take some time for this documentation to be complete.     The CS56 staff will tackle this a little bit at a time, working towards an eventual goal of completeness.   We'll list these in the canonical order, but fill them as they come up in the context of CS56. 

```
 <!-- (0) <modelVersion/> -->
  <!-- (1) <parent/> -->
  <!-- (2) <groupId/> -->
  <!-- (3) <artifactId/> -->
  <!-- (4) <version/> -->
  <!-- (5) <packaging/> -->
  <!-- (6) <name/> -->
  <!-- (7) <description/> -->
  <!-- (8) <url/> -->
  <!-- (9) <inceptionYear/> -->
  <!-- (10) <organization/> -->
  <!-- (11) <licenses/> -->
  <!-- (12) <developers/> -->
  <!-- (13) <contributors/> --> 
  <!-- (14) <mailingLists/> -->
  <!-- (15) <prerequisites/> -->
  <!-- (16) <modules/> -->
  <!-- (17) <scm/> -->
  <!-- (18) <issueManagement/> -->
  <!-- (19) <ciManagement/> -->
  <!-- (20) <distributionManagement/> -->
  <!-- (21) <properties/> -->
  <!-- (22) <dependencyManagement/> -->
  <!-- (23) <dependencies/> -->
  <!-- (24) <repositories/> -->
  <!-- (25) <pluginRepositories/> -->
  <!-- (26) <build/> -->
  <!-- (27) <reporting/> -->
  <!-- (28) <profiles/> -->
```