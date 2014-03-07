------

Basics of SQLAlchemy
=====

------

SQLAlchemy in General
---

**Elements** :

- **engine** -- pool of connections to the DB
- **connection** -- connection to the DB, can execute queries
- **transaction** -- unit of work
- **session** -- scope of objects mapped by ORM
- **query** -- contain the symbolic representation of the request
- **result proxy** -- cursor

**Expression Language** -- python code that generates queries
**ORM** -- object wrapper of DB using expression language

------

Expression Language in General
---

**connection** :

- connection.execute
- connection.begin -- returns a new transaction

**transactions** :

- transaction.rollback
- transaction.commit

select.where.order_by

------

ORM in General
---

**implementation** : 
ORM uses EL to access the DB 
it performs **identity map** in the background, which maps each row to an **proxy object** by primary key. 
behavior of proxy objects is defined by the **declarative class**. 
the **scope** of proxy objects is the session.


**session** :
objects binded with session is watched, but not flushed immediately. (implicite operation)
direct operations on session will trigger session.flush

each session has an **identity map** data-structure

- session.add
- session.query
- session.flush
- session.commit
- session.close

**proxy objects** :

- transient -- no session backend
- pending -- not flushed
- persistent -- flushed
- detached -- detached from session

**queries** :
construct a query object

---
reference:
[Stackoverflow - difference of session.commit & session.flush ](http://stackoverflow.com/questions/4201455/sqlalchemy-whats-the-difference-between-flush-and-commit "")


