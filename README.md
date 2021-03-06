## GPCA

This is the official Greg Points API.

## Documentation

### Endpoints spec
<details>
    <summary>Click to expand</summary>
    <br/>

| Endpoint                   | Method | Values                             | Description                                                                                                                 |
|----------------------------|--------|------------------------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `/`                        | `GET`  |                                    | Return a greeting message.                                                                                                  |
| `/status`                  | `GET`  |                                    | Get the status of the whole team's points; the leaderboard.                                                                 |
| `/status`                  | `POST` | `name`                             | Get the status of the `name` value's entry.                                                                                 |
| `/verify`                  | `POST` | `code`                             | Check if the `code` is a valid hash; if so, return a response code of 200. Else, diagnose and return a GPCA. response.\*    |
| `/new`                     | `POST` | `name`, `points`, `cryptocurrency` | Create a new entry with the `name`, `points`, and `cryptocurrency` values. \*                                               |
| `/update`                  | `POST` | `name`, `points`, `cryptocurrency` | Update a given entry.                                                                                                       |
| `/status/cryptocurrency`   | `GET`  |                                    | Responds with the status of the cryptocurrency.                                                                             |
| `/cryptocurrency/status`   | `GET`  |                                    | Responds with the status of the cryptocurrency.                                                                             |
| `/cryptocurrency/claim`    | `POST` | `name`, `hash`                     | Claim cryptocurrency to a user.                                                                                             |

\* Refer to [GPCA. responses](#gpca-responses) for more details.

</details>

### GPCA. Responses

<details>
    <summary>Click to expand</summary>
    <br/>

| ID | Description                                                                |
|----|----------------------------------------------------------------------------|
| 1  | The value is invalid, not correctly formatted, or not of the correct type. |
| 2  | The value is not a hashed block.                                           |

</details>


## Installation

### Dependencies

Make sure you install these (`go get <link>`)! Witout them, Go will get mad at you and you will be incapable of Greg Pointing.

 - [ ] `github.com/gorilla/mux`
 - [ ] `github.com/mattn/sqlite3`

### Run

Download the tarball, extract it, and in it run:

```shell
go run .
```

This will open up the server. It will also created necessary files, like sqlite's `.db` file. In the future, it will also created a backups directory for smaller errors - but it's up to you to back up your drive, and hence your databases.

### Build

You can also build a binary file. Binary files are provided in the releases already, but it's recommended that you build from source, to have a better structure in which to store your sqlite database file. On the other hand, using a built binary will give the look of a "faster" startup, because the `go` program is slow to build then run. Whichever the case, the option is there to build this project, because modularity!

```shell
go build .
```

### Running the unit tests

You'll find that the package is equipped with a handful of unit tests, at your service. One may run them with a simple:

```shell
go test -v
```

Furthermore, to enable benchmarking capabilities, one may run:

```shell
go test -v -bench=.
```

Considering the API is already running (defaulted to `localhost:10000`).

### Notes & Credits

 - All Mentors, Teachers, or Professors for the encouragment and ideation of Greg Points.
