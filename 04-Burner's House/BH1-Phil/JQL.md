---
type: work
index: {{index}}
tags: work, {{tag}}
created_date: NaN
update_date: NaN
---
Related: 
- {{related to}}

Tickets: 
- {{ticket}}

----

1. Get all ticket status and current ticket using JQL 
```q
project = "FFE" AND (assignee=61cbb76368926d0068fd025c OR assignee =6215ad9cba649b006aac8e04 OR assignee=637354fff48fbd9b62d37285 ) AND sprint in openSprints () ORDER BY created DESC
```
```
Key
Summary
Assignee
Priority
Status
Created
Due date
Parent
Story Points
Reporter
```
