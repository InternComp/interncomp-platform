## Running manually (Deprecated, for archivial purpose only)

### Frontend

**Setup (One Time Only)**

Assuming Node 20 LTS is installed

1. Go to frontend repo in terminal. For eg: `cd interncomp-frontend`.
2. Do `git pull` just in case.
3. Run `npm install`

**Running frontend**
To run, use `npm run dev`


### Backend

Firstly, we need to setup database.
Assuming Postgresql is installed, and make sure service is running.

Run in terminal: `sudo -u postgres psql -U postgres`

Then in postgres:
```bash
postgres=# CREATE USER test WITH PASSWORD 'password';
CREATE ROLE
postgres=# GRANT ALL PRIVILEGES ON DATABASE "interncomp-database" TO test;
GRANT
postgres=# ALTER USER test WITH SUPERUSER;
ALTER ROLE
postgres=# exit
```

Continue with backend setup

**Backend Setup (One Time Only)**

Assuming Node 20 LTS and Postgresql is installed

```bash
npx prisma generate
npm install
npx prisma migrate dev --name init
```

**Running backend**
To run, use `npm run dev`