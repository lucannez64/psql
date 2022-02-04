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
```

