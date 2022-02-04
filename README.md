## TABLE :

	- users 
	- services
	- files

### users :
	NOT NULL
	- id Primary Key 28 length character
	- mainpass byte array
	- bool boolean

```sql
CREATE TABLE IF NOT EXISTS users (
    id CHAR(28) NOT NULL PRIMARY KEY,
    main_pass BYTEA NOT NULL,
    bool BOOLEAN NOT NULL
);
```

### services : 

	- user_id 28 length character REFERENCES users (id)
	- password byte array NOT NULL 
	- name variable character NOT NULL
	- username variable character NOT NULL

```sql
CREATE TABLE IF NOT EXISTS services (
	name VARCHAR(255) NOT NULL PRIMARY KEY,
	username VARCHAR(255) NOT NULL,
	password BYTEA NOT NULL,
	user_id CHAR(28) NOT NULL REFERENCES users (id));
```
