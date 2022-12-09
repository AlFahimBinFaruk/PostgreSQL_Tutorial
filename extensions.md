### Extensions in PostgreSQL
1. To see installed extensions
```
\dx
```

2. to see all available extensions
```
SELECT * FROM pg_available_extensions;
```

* extension name have to be inside double quotes("").

3. Install extension
```
CREATE EXTENSION IF NOT EXISTS "uuid-ossp";
```

4. Uninstalll extension
```
DROP EXTENSION "uuid-ossp";
```