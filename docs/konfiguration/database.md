## Structure of `database.yml`

```yaml
database:
  type: sqlite    # Options: mysql, sqlite
  host: localhost
  port: 3306
  username: root
  password: password
  database_name: amusement_core
````

| Key             | Description                                                                                    | Example          |
| --------------- | ---------------------------------------------------------------------------------------------- | ---------------- |
| `type`          | Database type to use. Supported values: `mysql` or `sqlite`.                                   | `mysql`          |
| `host`          | Hostname or IP address of the database server. Use `localhost` for local instances.            | `localhost`      |
| `port`          | Port number the database server listens on. Usually `3306` for MySQL. Not required for SQLite. | `3306`           |
| `username`      | Username for authenticating with the database server.                                          | `root`           |
| `password`      | Password for the database user.                                                                | `password`       |
| `database_name` | The specific database or file to connect to.                                                   | `amusement_core` |

---

## Usage Guide

* **SQLite**:
  When `type` is set to `sqlite`, the application connects to a local file-based SQLite database.
  You may need to specify the exact file path depending on your setup.

* **MySQL**:
  When `type` is `mysql`, the application connects to a MySQL server using the specified host, port, username, and password.

---

## Important Notes

* **Correct Type Selection**:
  Always specify the database type matching your environment (`mysql` or `sqlite`). This determines which database client the app uses.

* **Port Configuration**:
  The `port` field is necessary for networked databases like MySQL, but can be omitted for SQLite since it uses a local file.

* **Security Best Practices**:
  Avoid storing plaintext passwords in configuration files that may be publicly accessible. Consider using environment variables or secret management tools.

* **Database Existence**:
  Ensure that the named database exists and is accessible by the specified user.

* **Customization**:
  The example uses default placeholders (`localhost`, `root`, `password`). Adjust these values to suit your production or development environment.