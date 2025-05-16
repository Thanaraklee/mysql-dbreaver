# MySQL with DBeaver via Docker & Traefik

### 1. Rename and Configure Environment File

Rename the `.env.example` file to `.env` and update the environment variables according to your setup.

```bash
mv .env.example .env
```

Edit the **.env** file to configure:
- `MYSQL_ROOT_PASSWORD`
- `MYSQL_DATABASE`
- `MYSQL_USER`
- `MYSQL_PASSWORD`
- `TRAEFIK_EMAIL`

### 2. Start Docker Services
Run the following command to start all services in detached mode:
```bash
docker compose up -d
```
### 3. Access DBeaver
- Open your browser and go to: http://localhost

**Important** If it shows "Page not found", ensure Traefik and CloudBeaver services are running and properly configured.

### 4. Connect to MySQL via DBeaver
In DBeaver:
- Host: `mysql`
- Port: `3306`
- Username: `mysql`
- Password: `mysql` (or use the value from your .env)

If you see the error:
```vbnet
Public Key Retrieval is not allowed
```
Go to Driver Properties tab in the DBeaver connection settings, and set:
```ini
allowPublicKeyRetrieval=true
```