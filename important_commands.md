### Important commands.

1. To execute all commands from a sql file

```
\i F:/postgresql/person.sql;
```

2. Generate CSV with postgres

```
\copy (SELECT * FROM car LIMIT 5) TO 'F:/postgresql/result.csv' DELIMITER ',' CSV HEADER;
```

3. List of all db function we have depending on the installed extensions

```
\df
```

4. How to use extension(uuid example)

```
-- Normal way
CREATE TABLE person (
	id UUID NOT NULL PRIMARY KEY,
	person_name VARCHAR(50),
	gender VARCHAR(50)
);

INSERT INTO person (id,person_name, gender) values (uuid_generate_v4(),'Antons', 'M');
INSERT INTO person (id,person_name, gender) values (uuid_generate_v4(),'Dulcy', 'F');
INSERT INTO person (id,person_name, gender) values (uuid_generate_v4(),'Chic', 'M');
INSERT INTO person (id,person_name, gender) values (uuid_generate_v4(),'Valle', 'M');
INSERT INTO person (id,person_name, gender) values (uuid_generate_v4(),'Darin', 'M');
INSERT INTO person (id,person_name, gender) values (uuid_generate_v4(),'Tara', 'F');


-- Using default
CREATE TABLE person (
	id UUID NOT NULL PRIMARY KEY DEFAULT uuid_generate_v4(),
	person_name VARCHAR(50),
	gender VARCHAR(50)
);
INSERT INTO person (person_name, gender) values ('Antons', 'M');
INSERT INTO person (person_name, gender) values ('Dulcy', 'F');
INSERT INTO person (person_name, gender) values ('Chic', 'M');
INSERT INTO person (person_name, gender) values ('Valle', 'M');
INSERT INTO person (person_name, gender) values ('Darin', 'M');
INSERT INTO person (person_name, gender) values ('Tara', 'F');
```
