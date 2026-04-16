# spring-demo

Small Spring Boot 3.5 demo with a Task REST API backed by H2.

## Run

```
./mvnw spring-boot:run
```

Server listens on `http://localhost:8080`.

## Endpoints

| Method | Path             | Description                                       |
| ------ | ---------------- | ------------------------------------------------- |
| GET    | `/tasks`         | List all tasks                                    |
| POST   | `/tasks`         | Create a task (JSON body with `title`, etc.)      |
| GET    | `/tasks/search`  | Search tasks by title fragment (`?q=<fragment>`)  |

### Search endpoint

`GET /tasks/search?q=<fragment>` returns tasks whose `title` contains the given
fragment, case-insensitively.

Example:

```
curl 'http://localhost:8080/tasks/search?q=buy'
```

Backed by Spring Data JPA's derived query `findByTitleContainingIgnoreCase`.

## H2 console

Available at `http://localhost:8080/h2-console` (JDBC URL
`jdbc:h2:mem:tasksdb`, user `sa`, no password).
