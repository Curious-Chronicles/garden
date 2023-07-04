---
index: BC924
tags: sql,data-model-design,workshop
status: Started
created: <%+ tp.file.creation_date("dddd Do MMMM YYYY") %>
updated: <%+ tp.file.last_modified_date("dddd Do MMMM YYYY") %>
---
Related: {{related}}
URL: {{resourc url}}

---

# Introduction


1. Business requirement should be clear
2. Higher level draft to include all the listed entity. 

Stages:
1. Conceptual - Business requirement and its entity. 
2. Logical - Breakdown and add constraints. 
3. Physical - Develop DB.

Surrogate - Unique identify to auto-generate key. No business meaning 
Natural key - Business meaning if present, we call them. 

```sql
// Use DBML to define your database structure
// Docs: https://dbml.dbdiagram.io/docs

Table properities {
  property_id integer [primary key]
}

Table jobs {
  job_id integer [primary key]
  staff_id integrer
  design_id integer
}

Table design {
  design_id integer [primary key]
}

Table parts {
  part_id integer [primary key]
}

Table jobParts {
  id integer [primary key]
  job_id integer
  part_id integrer
}

Table staff {
  staff_id integer [primary key]
}


Ref: "properities"."property_id" < "jobs"."job_id"


Ref: "jobs"."job_id" < "jobParts"."job_id"

Ref: "parts"."part_id" < "jobParts"."part_id"

Ref: "jobs"."staff_id" <> "staff"."staff_id"

Ref: "jobs"."design_id" < "design"."design_id"
```
