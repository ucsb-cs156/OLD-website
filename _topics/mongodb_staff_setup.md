---
topic: "MongoDB: Staff Setup"
desc: "Information for Course Staff on settig up the MongoDB instances for the project repos"
category_prefix	: "MongoDB: "
indent: true
---

Each of the three legacy code projects (proj-ucsb-courses-search, proj-ucsb-cs-las, and proj-mapache-search) uses MongoDB, but in different ways, and requires
different setup.

This page is intended for the course staff as documentation on how to do this setup.


# proj-ucsb-courses-search

For the courses search application, the MongoDB database is used as a data warehouse for historical data.  The same data can always be obtained through the UCSB Courses Search API, however the API limits searches to only a single quarter at a time.   Thus searches across multiple quarters are quite inefficient.

For now, proj-ucsb-courses-search app only requires read-only access to the MongoDB instance, and a single MongoDB instance can be persisted from course instance to course instance.  

Accordingly, the process for a new quarter is to just create read-only-credentials for each team, and distribute them to the teams working on proj-ucsb-courses-search.

For now, updating the database is a manual process done by staff, using scripts from this repo: 

In the future, it may be helpful to implement some new features that would require the app to have read/write access:
* a feature where query that obtains information from the UCSB API also stores that data in the MongoDB database (to keep it up to date on a rolling basis)
* a caching feature where the MongoDB database tables have a notion of the "current quarter" vs. past or future quarters, and always use the MongoDB database
  for any queries for past quarters.
* a "background jobs" feature built into the app that can obtain data (slowly) from the API and populate the MongoDB database (as the script does), but built
  into the app as an Admin only feature.
  
  
## Onboarding new teams and devs

There is a MongoDB Organization called "ucsb-cs156", which has under it, a project `ucsb-courses-search`.  The production database for `ucsb-courses-search` is shared by all instances of the repo (prod, qa, dev) since it is read only.    To onboard a new course instance:

* Navigate under [cloud.mongodb.com](https://cloud.mongodb.com) to Organization `ucsb-cs156`, Project `ucsb-courses-search`.
* Create a new database user for each team with names such as `team-s21-5pm-1`, `team-s21-5pm-2`, etc., each with the privilege level `readAnyDatabase`
* Distribute the MongoDB credentials to the teams' slack channels. 

# proj-ucsb-cs-las

In proj-ucsb-cs-las, the MongoDB database is used to track logins.   MongoDB is used because of the feature of a "capped collection", where the most recent
data is retained, and older data is automatically deleted.

For proj-ucsb-cs-las, we need to create new databases for each quarter, and for each team, since read/write access is required.


# proj-mapache-search

For mapache-search, the MongoDB database is used to store information from a Slack workspace.   MongoDB is chosen because the data originates as hierarchical data in JSON; flattening it into data suitable for a relational database (i.e. flat tables) would be quite cumbersome.

A new database instance should be created for each quarter, since the database contains data from the current slack workspace.

For proj-mapache-search, the app has read-only access to the data; the data is updated by a script run by the staff.   