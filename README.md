## TABLE :

	- users 
	- services
	- files

### users :
	NOT NULL
	- id Primary Key CHAR(28)
	- mainpass VARCHAR(72)
	- bool BOOL

```sql
CREATE TABLE users (
id CHAR(28) NOT NULL PRIMARY KEY,
mainpass VARCHAR(72) NOT NULL,
bool BOOL NOT NULL);
```

```sql
INSERT INTO users (
	id,
	mainpass,
	bool)
VALUES ('y9SCkDIynPUw3CxzGPOL1PTtFvt1', 'TQwp&LwAciDR$2a$10$tUbQEfH7p6M41VWXhQrdeOH95vKbg/P3hj3EpZqzGkMd9rI2xCNTC', TRUE);
INSERT INTO users (
	id,
	mainpass,
	bool)
VALUES ('DMmuV5K8tRSbWy4O1fsszMnv4Fn1', 'Y�AIUJDphYJx$2a$10$H4rL/dOITPBHmcYuCK0S0uEvuhJ1Yw8PjieQpB4vc7F.SkcO7MW..', TRUE);
```

```sql

SELECT * FROM users WHERE id = '$ID'

DELETE FROM users WHERE id = '$ID'

UPDATE users SET $COLUMN WHERE id = '$ID'

INSERT INTO users (
	id,
	mainpass,
	bool)
VALUES ('DMmuV5K8tRSbWy4O1fsszMnv4Fn1', 'Y�AIUJDphYJx$2a$10$H4rL/dOITPBHmcYuCK0S0uEvuhJ1Yw8PjieQpB4vc7F.SkcO7MW..', TRUE)
ON CONFLICT (id) DO UPDATE SET $COLUMN = EXCLUDED.$COLUMN
```
### services : 
	NOT NULL
	- user_id CHAR(28) REFERENCES users (id)
	- password TEXT NOT NULL 
	- name VARCHAR(100) NOT NULL
	- username VARCHAR(150) NOT NULL

```sql
CREATE TABLE services (
	name VARCHAR(100) NOT NULL PRIMARY KEY,
	username VARCHAR(150) NOT NULL,
	password TEXT NOT NULL,
	user_id CHAR(28) REFERENCES users (id));
```
