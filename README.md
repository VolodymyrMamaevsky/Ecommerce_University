# Ecommerce_University

To bring up the services and databases for local development, run the following command:

```
make up
```

To initialize migrations, if the alembic.ini file does not yet exist, run the following command in the terminal:

```
alembic init migrations
```

After that, a folder with migrations and a configuration file for Alembic will be created.

In alembic.ini, specify the address of the database where migrations will be applied.
Next, go to the migrations folder and open env.py, then make changes in the block where it says:

```
from myapp import mymodel
```

- Then enter: ```alembic revision --autogenerate -m "comment"``` - this is done whenever there are changes to the models.
- A migration will be created.
- Then enter: alembic upgrade heads ```alembic upgrade heads```

To ensure that migrations are generated properly during tests:

First, try running the tests as usual. Everything should fail the first time.
If after the failure Alembic files are created in the tests folder, you need to manually add migration data to them.
If they are not created, go to the tests folder from the console and manually run the migration commands to generate the necessary files.
